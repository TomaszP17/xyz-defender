# Model scenariusza

Status: propozycja dla pierwszej grupy 13–15 lat. Powiązania: FR-15–19, FR-23–25.

## Pola redakcyjne

| Sekcja | Pola | Walidacja |
| --- | --- | --- |
| Podstawy | Tytuł, opis, kampania, grupa wieku, czas orientacyjny | Wymagane; pierwsze demo obejmuje 13–15 lat |
| Fikcyjny kontekst | Imię postaci, sytuacja, wiadomość startowa | Brak rzeczywistych kontaktów i sekretów |
| Rozmowa | Cel dialogu, ograniczone warianty nacisku, maksymalna liczba tur | Limit nie przekracza maksimum aplikacji; bez nowych narzędzi modelu |
| Decyzje | Wybór akcji z obsługiwanej listy, skutek i warunek zakończenia | Tylko akcje znane silnikowi treningu |
| Kryteria | Nazwa umiejętności, działania stanowiące dowód, tekst wskazówki | Co najmniej jedno bezpieczne i jedno ryzykowne zachowanie |
| Zakończenie | Feedback dla wariantów, neutralna treść przerwania i braku obserwacji | Brak automatycznej porażki za niepełne dane |

Redaktor wypełnia formularz. Nie edytuje bazowego promptu systemowego i nie musi pisać JSON. Nowy scenariusz istniejącego typu nie wymaga kodu; nowy typ interakcji może go wymagać.

## Przykład roboczy SC-01 — pilna wiadomość od znajomego

Kontekst: fikcyjny znajomy z komunikatora prosi o pomoc przy zakupie i naciska na szybkie przekazanie danych płatniczych. Trening nie zakłada posiadania przez uczestnika konta bankowego.

Start: „Hej, możesz mi pomóc z zakupem? Zaraz stracę rezerwację”. Dalsza presja jest krótka i nie obejmuje gróźb ani upokarzania.

| Decyzja | Fikcyjny rezultat | Obserwacja |
| --- | --- | --- |
| Zweryfikuj innym kanałem | Scenariusz ujawnia, że znajomy niczego nie wysyłał | Weryfikacja zamiast polegania na profilu |
| Poproś zaufanego dorosłego o pomoc | Rozmowa zostaje zatrzymana na czas sprawdzenia sytuacji | Szukanie wsparcia |
| Przekaż fikcyjne dane w ćwiczeniu | Pokazanie ryzyka bez podania kodu i bez transakcji | Działanie pod presją |
| Zakończ kontakt | Brak dalszego dialogu, neutralne wyjaśnienie | Zatrzymanie rozmowy; nie zakładamy wykonania weryfikacji |

Informacja zwrotna odnosi się do konkretnego działania. Brak obserwacji kryterium nie jest negatywną oceną dziecka. Swobodny tekst służy rozmowie; rekomendujemy jawne potwierdzenia decyzji zamiast automatycznego punktowania wypowiedzi przez model.

To scenariusz roboczy do redakcji i akceptacji, nie gotowy materiał kampanii ani wykazana metoda edukacyjna. Pełna mechanika: [silnik treningu](../03-architecture/training-engine.md).
