# Dane i operacje API

Status: projekt kontraktu w Markdown; bez generowania OpenAPI i kodu na obecnym etapie.

## Model danych

| Pojęcie | Minimalne dane | Reguła |
| --- | --- | --- |
| Campaign | Identyfikator, nazwa, aktywność | Jedna kampania XYZ wystarcza do demo |
| Scenario | Identyfikator, powiązanie z kampanią | Stała tożsamość niezależna od wersji |
| ScenarioVersion | Numer, status, treści, cele, działania, limity, feedback | Opublikowana wersja nie jest edytowana w miejscu |
| TrainingSession | Losowy identyfikator, skrót tokenu, wersja, kampania, status, terminy, tryb preview | Jedna sesja to jedno podejście, nie unikalny człowiek |
| Turn | Sesja, numer, wiadomości, stan operacji | Krótkotrwały zapis do prowadzenia rozmowy; retencja do decyzji |
| Decision | Sesja, typ działania, czas | Bez kopiowania całej wypowiedzi uczestnika do dowodu |
| Evaluation | Sesja, obserwacje kryteriów, powód zakończenia | Jeden wynik na sesję, wyliczany z przypisanej wersji |
| Operation | Identyfikator, sesja, stan, czas i wynik techniczny | Deduplikacja i obsługa operacji przerwanej restartem |

Django zapewni osobne konta i sesje redaktorów, jeśli zatwierdzimy tę technologię. Brak tabeli profilu dziecka w proponowanym P0.

## Dostęp uczestnika

Publiczny jest katalog i start sesji. Start wydaje losowy token o wysokiej entropii; backend przechowuje jego skrót. Token przesyłamy w nagłówku autoryzacji, nie w URL i nie w logach. Identyfikator sesji sam nie daje dostępu. Klient nie odczytuje szkiców, reguł wewnętrznych ani promptów.

Minimalny wariant demo przechowuje token tylko na czas bieżącego uruchomienia aplikacji. Trwałe wznowienie po jej zamknięciu jest P1. Zakończona sesja przestaje przyjmować zmiany, ale wynik można odczytać do wygaśnięcia tokenu lub retencji.

## Proponowane API uczestnika

| Operacja | Ścieżka | Zachowanie |
| --- | --- | --- |
| Lista | GET /api/v1/scenarios | Wyłącznie bieżące dostępne treści publiczne |
| Szczegóły | GET /api/v1/scenarios/{id} | Opis do ekranu M03, bez ustawień wewnętrznych |
| Start | POST /api/v1/sessions | Scenariusz i identyfikator operacji; wynik zawiera token i początek rozmowy |
| Stan | GET /api/v1/sessions/{id} | Status i publiczny zapis sesji dostępny właścicielowi tokenu |
| Tura | POST /api/v1/sessions/{id}/turns | Tekst albo identyfikator dozwolonej akcji, identyfikator operacji i rewizja |
| Zakończenie | POST /api/v1/sessions/{id}/finish | Przerwanie, także podczas trwającego wywołania AI |
| Wynik | GET /api/v1/sessions/{id}/feedback | Obserwacje, wskazówki i powód zakończenia |

Start wykorzystuje dodatkowy losowy sekret idempotencji klienta, niezależny od publicznego ID operacji, aby bezpiecznie zwrócić tę samą sesję po utracie odpowiedzi. Szczegółowy format i czas ważności ustalamy w kontrakcie przed implementacją.

## Błędy i ponowienia

Błędy mają stabilny kod, polski komunikat, identyfikator żądania i informację, czy można ponowić. Kategorie: nieprawidłowe wejście, brak dostępu, brak lub wycofanie scenariusza, konflikt rewizji, limit, timeout i niedostępność dostawcy. Nie ujawniamy wyjątków technicznych ani szczegółów cudzej sesji.

Identyfikator operacji deduplikuje zapis; nie gwarantuje jednokrotnego naliczenia kosztu przez zewnętrznego dostawcę. [Silnik treningu](training-engine.md) opisuje rezerwacje i późne odpowiedzi.

## Dane do pomiaru

Liczniki bazują na sesjach z bazy, nie na osobnym systemie zdarzeń. Ukończenie oznacza COMPLETED; STOPPED, ERROR, WITHDRAWN i EXPIRED liczymy osobno. Wskaźnik ukończeń to COMPLETED / wszystkie rozpoczęte sesje, bez preview. Nie nazywamy liczby sesji liczbą unikalnych użytkowników. Małe agregaty demo dostępne są wyłącznie redaktorowi.
