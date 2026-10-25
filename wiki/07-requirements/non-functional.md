# Wymagania niefunkcjonalne

Status: proponowane cele demo, bez gwarancji produkcyjnych i bez automatycznych testów. Liczby wymagają akceptacji oraz ręcznego sprawdzenia w wybranym środowisku. Nie są wynikami benchmarku.

| ID | Obszar | Priorytet | Proponowane wymaganie i ręczne sprawdzenie |
| --- | --- | --- | --- |
| NFR-01 | Prostota | P0 | Jeden backend, jedna baza i jeden dostawca AI. Brak kolejki, Redis i mikroserwisów w rdzeniu. Przegląd elementów uruchomienia. |
| NFR-02 | Platforma | P0 | Pełna ścieżka na jednym fizycznym telefonie; Android proponowany jako pierwszy. Dokładny system i urządzenie zapisać przed pokazem. iOS nie jest jeszcze zobowiązaniem demo. |
| NFR-03 | Czytelność | P0 | Brak obciętych elementów na ekranie szerokości 360 jednostek logicznych i przy powiększeniu tekstu 130%; klawiatura nie zasłania wysyłania i wyjścia. |
| NFR-04 | Dostępność | P0 | Przyciski dotykowe co najmniej 44 × 44 jednostki logiczne, etykiety dostępności, informacja niezależna od koloru. Docelowy kontrast zwykłego tekstu co najmniej 4,5:1. Ręczny przegląd ekranów; nie deklarujemy pełnej zgodności z normą. |
| NFR-05 | Odpowiedź UI | P0 | Potwierdzenie wysłania i stan oczekiwania widoczne w ciągu 0,5 s; użytkownik nie czeka bez komunikatu. |
| NFR-06 | Czas odpowiedzi | P0 | Cel: katalog i wynik do 2 s przy stabilnej sieci demo; typowa odpowiedź AI do 8 s. Twardy timeout wywołania modelu 15 s, komunikat klienta najpóźniej po 20 s. Pomiar kilku sesji zapisany jako obserwacja, bez SLA. |
| NFR-07 | Obciążenie | P1 | Cel orientacyjny: 5 równoległych sesji w środowisku demonstracyjnym. Limit czasu i budżetu działa także przy współbieżności; większą skalę odkładamy. |
| NFR-08 | Odporność | P0 | Ponowienie tego samego żądania nie dubluje decyzji. Ukończona sesja i opublikowana treść przetrwają restart backendu; operacja w toku może skończyć się błędem, bez gwarancji braku ponownego kosztu u dostawcy AI. |
| NFR-09 | Dostęp | P0 | HTTPS poza lokalnym środowiskiem, oddzielne logowanie panelu, uprawnienia backendowe. Klucz AI i hasło bazy poza aplikacją mobilną, plikami repozytorium i logami. |
| NFR-10 | Prywatność | P0 | Bez nazwiska, e-maila, kontaktów i dokładnej daty urodzenia uczestnika; bez reklamowych SDK. Logi techniczne bez treści czatu i tokenów. Token sesji oznacza pseudonimowy dostęp, nie gwarancję pełnej anonimowości. |
| NFR-11 | Retencja | P0 | Propozycja demo: czat potrzebny do sesji przechowywany maksymalnie 24 h, następnie usuwany; agregaty bez identyfikacji osoby. Okres dla decyzji i wyników wymaga zatwierdzenia przed użyciem przez dzieci. Usuwanie danych w aplikacji nie usuwa automatycznie kopii dostawcy AI. |
| NFR-12 | Koszt i nadużycia | P0 | Propozycja: maks. 6 ukończonych tur, 500 znaków wejścia i 240 tokenów odpowiedzi modelu na turę. Serwer egzekwuje limit; ponowienia modelu wyłącznie jawne. Wspólny limit wywołań ustalamy po wyborze dostawcy, żeby ograniczyć koszt demo. |
| NFR-13 | Bezpieczeństwo AI | P0 | Dane uczestnika są treścią rozmowy, nie instrukcją systemową. Model bez narzędzi, przeglądarki i dostępu do bazy. Walidacja odpowiedzi przed pokazaniem; przy odrzuceniu komunikat i bezpieczne zakończenie. Nie deklarujemy całkowitej odporności na manipulację. |
| NFR-14 | Wdrożenie | P0 | Ten sam obraz backendu dla lokalnego Compose i Kubernetes; stan w bazie, gotowość i liveness, konfiguracja z otoczenia. Migracja bazy osobno. Restart poda nie usuwa danych. |
| NFR-15 | Obsługa błędów | P0 | Polski komunikat dla uczestnika, identyfikator żądania i kategoria błędu dla operatora. Niedostępność modelu nie oznacza restartu całej aplikacji. |
| NFR-16 | Edytowalność | P0 | Nowy scenariusz istniejącego typu widoczny po publikacji i odświeżeniu listy, bez budowania mobile ani wdrażania backendu. Nowa mechanika może wymagać kodu. |
| NFR-17 | Praca agentowa | P0 | Każde zadanie wskazuje FR/NFR, źródłowy dokument, dozwolone pliki i ręczny odbiór. Wersje treści i kontrakt API mają jedno źródło prawdy. |

## Jakość programu kampanii

| ID | Obszar | Priorytet | Proponowane wymaganie i ręczne sprawdzenie |
| --- | --- | --- | --- |
| NFR-18 | Dopasowanie treści | P0 | Teksty i stopień presji są przypisane do pakietu; pierwsze demo sprawdzamy dla kontekstu 13–15 lat. Inna grupa wymaga redakcyjnego przeglądu. Nie twierdzimy, że opublikowanie wariantu tekstowego dowodzi dostępności dla każdego wieku. |
| NFR-19 | Wiarygodność edukacji | P0 | Wynik opisuje wyłącznie obserwacje z ćwiczenia. Brak deklaracji pełnej odporności, certyfikacji użytkownika i redukcji strat bez badań. Wskazówki mają referencję redakcyjną i nie wynikają z dowolnej wypowiedzi AI. |

## Granice hackathonu

Brak zobowiązań do wysokiej dostępności, autoskalowania, disaster recovery, pełnego audytu prawnego i publikacji w sklepach. Przed rzeczywistym pilotażem osobno uzgadniamy dostawcę AI, retencję, zasady pracy z niepełnoletnimi i proces bezpieczeństwa. Obecnie demonstrujemy rozwiązanie na syntetycznych danych.
