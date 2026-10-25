# Architektura aplikacji

Status: projekt do zatwierdzenia, 2026-10-25. Ustalone: Python, mobile, panel scenariuszy i konteneryzacja z możliwością wdrożenia na Kubernetes. Proponowane: Django, DRF, PostgreSQL i React Native z Expo.

## Granice systemu

| Element | Odpowiedzialność | Komunikacja |
| --- | --- | --- |
| Aplikacja mobilna | Ekrany M01–M06, tekst uczestnika, jawne działania, prezentacja wyniku | HTTPS/JSON do API |
| Backend Python | Reguły treningu, publikacja, ocena, uprawnienia i adapter AI | Jedna baza i wywołania HTTPS dostawcy modelu |
| Panel redakcyjny | Formularze i statystyki organizatora, proponowany Django Admin | Ten sam backend; uwierzytelniona sesja przeglądarki |
| PostgreSQL | Scenariusze, wersje, sesje, decyzje i wyniki | Dostęp tylko z backendu |
| Dostawca AI | Generowanie wypowiedzi fikcyjnej postaci | Tylko przez adapter backendu |

Jeden backend i jedna baza. Panel nie jest drugim serwisem ani frontendem SPA. Aplikacja mobilna nie kontaktuje się bezpośrednio z bazą lub modelem. Klucz dostawcy nigdy nie trafia na telefon.

## Moduły wewnątrz backendu

| Moduł | Właściciel danych | Udostępniane operacje | Główne FR |
| --- | --- | --- | --- |
| content | Scenariusze, wersje, reguły i teksty feedbacku | Pobierz dostępną wersję, zapisz szkic, opublikuj, wycofaj | FR-03, FR-15–19 |
| training | Sesje, tury i decyzje | Rozpocznij, odpowiedz, wykonaj działanie, zakończ | FR-04–09, FR-12 |
| evaluation | Wynik i obserwacje kryteriów | Oceń zakończoną sesję na podstawie jej wersji | FR-10, FR-24 |
| ai | Konfiguracja adaptera i metadane wywołań | Wygeneruj ograniczoną wypowiedź albo zwróć błąd | FR-05, FR-23, FR-25 |
| campaigns | Kampania i zapytania agregujące | Przypisz scenariusze, policz wykorzystanie | FR-20–21 |
| administration | Konta redaktorów i widoki panelu | Dostęp do operacji domenowych po sprawdzeniu uprawnień | FR-14–22 |

Kierunek zależności: panel/API → operacje domenowe; training → content, ai i evaluation; campaigns odczytuje metadane sesji do agregatów. Moduł AI nie zna panelu i nie wykonuje operacji w bazie. Wszystkie wejścia do publikacji korzystają z tej samej walidacji.

## Obsługa jednej odpowiedzi

1. API sprawdza token sesji, status, limit i identyfikator żądania.
2. Backend rezerwuje turę krótką transakcją; odrzuca równoległą turę tej samej sesji.
3. Adapter otrzymuje wersję scenariusza i minimalny kontekst, bez tokenu uczestnika i danych redaktora.
4. Wywołanie modelu odbywa się poza transakcją bazy.
5. Backend waliduje wypowiedź, sprawdza ponownie status sesji i zapisuje turę, jeśli nadal jest aktywna.
6. Odpowiedź zawiera publiczną wiadomość, dozwolone działania i stan sesji. Nie ujawnia wewnętrznych instrukcji.

Po przerwaniu lub wycofaniu spóźniona odpowiedź modelu jest odrzucana. Jedna trwająca tura na sesję, zwykłe żądania HTTP, bez WebSocket i streamingu w pierwszym demo.

## Ocena

Jawne działania dają obserwowalne dowody. Swobodny tekst prowadzi dialog; w pierwszej rekomendowanej wersji sam nie przyznaje punktów. Jeśli użytkownik napisał o bezpiecznym działaniu, aplikacja może poprosić o potwierdzenie przyciskiem. Brak potwierdzenia oznacza „nie zaobserwowano”, bez kary.

Feedback opiera się na zatwierdzonych tekstach scenariusza. Nie potrzebujemy drugiego generatywnego agenta oceniającego. [Szczegóły silnika](training-engine.md).

## Przyszła struktura kodu — jeszcze jej nie tworzymy

- `apps/mobile/` — klient, ekrany i adapter API.
- `services/backend/` — backend, panel i opisane moduły.
- `contracts/` — późniejszy kontrakt API, po autoryzacji implementacji.
- `deploy/` — późniejsze pliki kontenera i Kubernetes.
- `wiki/` i `agents/` — aktualna dokumentacja i instrukcje.

Podział ma ułatwiać ograniczone zadania agentów. Kod, manifesty i zależności nie są częścią obecnego zlecenia.
