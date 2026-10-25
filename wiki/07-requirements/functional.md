# Wymagania funkcjonalne

Status: projekt specyfikacji produktu proponowanej trzeciej odsłony „Metody na Podszywacza”. Demo: 13–15 lat; docelowo różne grupy przez pakiety treści. P0/P1 zgodnie z [definicją priorytetów](README.md). Identyfikatory ekranów: [plan UX](../01-product/experience.md). Kryteria odbieramy ręcznie; nie planujemy teraz automatycznych testów.

## Uczestnik

| ID | Priorytet | Wymaganie | Kryterium ręcznego odbioru |
| --- | --- | --- | --- |
| FR-01 | P0 | Rozpoczęcie bez zakładania konta | Uczestnik dociera do katalogu bez nazwiska, e-maila, daty urodzenia i danych finansowych. |
| FR-02 | P0 | Wyjaśnienie fikcyjnego treningu | Przed startem widać zasady; w całej rozmowie widnieje „Symulacja z AI”. |
| FR-03 | P0 | Katalog dostępnych scenariuszy | M02 pokazuje opublikowane i niewycofane wersje; szkic nie jest widoczny. Pusta lista i błąd mają różne komunikaty. |
| FR-04 | P0 | Rozpoczęcie konkretnej sesji | M03 uruchamia jedną sesję przypisaną do wersji treści i kampanii; ponowienie tego samego żądania nie tworzy drugiej sesji. |
| FR-05 | P0 | Rozmowa tekstowa | Wiadomość uczestnika i odpowiedź postaci pojawiają się w kolejności; podczas generowania nie wysyłamy drugiej tury. |
| FR-06 | P0 | Jawne działania edukacyjne | Weryfikacja, pomoc dorosłego i zakończenie są rejestrowane jako decyzje. Żadna akcja nie dzwoni ani nie wysyła wiadomości poza aplikacją. |
| FR-07 | P0 | Fikcyjna decyzja ryzykowna | Scenariusz umożliwia pokazanie skutku ryzykownego wyboru bez wpisywania prawdziwych danych; wynik różni się od bezpiecznej decyzji. |
| FR-08 | P0 | Przerwanie i zakończenie | Uczestnik może zakończyć także podczas oczekiwania na AI. Po zakończeniu nie można kontynuować tej sesji. |
| FR-09 | P0 | Limit długości ćwiczenia | Po osiągnięciu limitu tur backend kończy rozmowę i udostępnia podsumowanie. Limit obejmuje ukończone tury, nie nieudane żądania. |
| FR-10 | P0 | Wyjaśnienie decyzji | M05 wskazuje zaobserwowane działania, nieobserwowane kryteria i wskazówki. Nie obniża oceny za styl pisania ani samą niejednoznaczność wypowiedzi. |
| FR-11 | P0 | Ponowne ćwiczenie | Powtórzenie tworzy nową sesję z aktualnie dostępną wersją; nie nadpisuje starej. |
| FR-12 | P0 | Błąd sieci i modelu | Uczestnik widzi problem i może bezpiecznie ponowić tę samą operację albo zakończyć. Nie powstają podwójne wiadomości i wyniki. |
| FR-13 | P1 | Powrót do aktywnej sesji | Po przejściu aplikacji w tło można pobrać stan sesji. Utrata tokenu oznacza rozpoczęcie nowego treningu, bez wyszukiwania osoby. |

## Redaktor i administracja

| ID | Priorytet | Wymaganie | Kryterium ręcznego odbioru |
| --- | --- | --- | --- |
| FR-14 | P0 | Logowanie redaktora | Niezalogowana osoba nie odczytuje szkiców ani nie wykonuje publikacji; wylogowanie zamyka dostęp. |
| FR-15 | P0 | Tworzenie i edycja szkicu | Redaktor zmienia teksty, postać, cele, limit i feedback przez formularz, bez edycji plików lub kodu. |
| FR-16 | P0 | Podgląd scenariusza | Redaktor widzi treść, działania i podsumowanie przed publikacją. Podgląd nie podnosi liczników uczestników. |
| FR-17 | P0 | Walidacja i publikacja | Brak wymaganej treści lub limit ponad dozwolone maksimum blokuje publikację z opisem błędu. Poprawny scenariusz pojawia się po odświeżeniu katalogu. |
| FR-18 | P0 | Wersjonowanie | Edycja opublikowanej treści tworzy szkic kolejnej wersji. Trwająca sesja nadal używa starej wersji i tych samych reguł oceny. |
| FR-19 | P0 | Wycofanie treści | Wycofanie blokuje nowe sesje i kończy aktywne sesje tej wersji komunikatem o niedostępności, bez oceny porażki. |
| FR-20 | P0 | Przypisanie do kampanii | Demo ma jedną proponowaną trzecią odsłonę kampanii XYZ. Redaktor przypisuje scenariusz do niej bez wdrożenia nowej aplikacji. |
| FR-21 | P0 | Zagregowane statystyki | Panel pokazuje rozpoczęcia, ukończenia, przerwania, błędy i wycofania oraz częstość jawnych decyzji według wersji scenariusza, z wyłączeniem podglądów. Powtórzenie treningu liczy się jako nowa sesja. |
| FR-22 | P1 | Kopiowanie i wyszukiwanie | Redaktor kopiuje scenariusz do szkicu i filtruje listę według statusu oraz tytułu. |

## Logika wspólna

| ID | Priorytet | Wymaganie | Kryterium ręcznego odbioru |
| --- | --- | --- | --- |
| FR-23 | P0 | Backend kontroluje przebieg | Model zwraca tekst postaci; nie publikuje treści, nie ustawia punktów ani stanu końcowego. Żądanie wyjścia poza scenariusz nie daje dostępu do funkcji administracyjnych. |
| FR-24 | P0 | Częściowy wynik | Przerwanie, błąd i wycofanie mają osobne powody zakończenia. Brak obserwacji nie jest automatycznie ryzykowną decyzją. |
| FR-25 | P0 | Stałe granice treści | Redaktor nie wyłącza etykiety symulacji i ograniczeń aplikacji; interfejs nie prosi o autentyczne sekrety. |
| FR-26 | P0 | Rozdzielenie sesji i uprawnień | Token jednej sesji nie otwiera innej sesji ani panelu. API uczestnika nie udostępnia instrukcji modelu i wewnętrznych ustawień. |

## Program kampanii

| ID | Priorytet | Wymaganie | Kryterium ręcznego odbioru |
| --- | --- | --- | --- |
| FR-27 | P0 | Cel i pochodzenie treści | Redaktor przypisuje scenariuszowi cel C01–C06, referencję materiału i datę przeglądu. Bez celu lub referencji publikacja jest zablokowana. |
| FR-28 | P0 | Przygotowanie i ochrona bliskich | Uczestnik widzi redagowaną kartę przygotowania oraz po ćwiczeniu wskazówkę ochrony innych. AI nie improwizuje tych treści; samo odczytanie nie daje zaliczenia umiejętności. |
| FR-29 | P1 | Pakiety odbiorców | Uczestnik wybiera opublikowany pakiet bez daty urodzenia i konta. Zmieniają się konteksty i język; szkice innych grup nie są reklamowane jako dostępne. |
| FR-30 | P1 | Wejście z materiału kampanii | Dla zainstalowanej aplikacji link może wskazać pakiet lub scenariusz. Niepoprawny lub wycofany cel prowadzi do katalogu. Opcjonalny kod kanału nie identyfikuje osoby. |
| FR-31 | P1 | Różnicowanie sytuacji | Katalog może zawierać inny pretekst Podszywacza i zwyczajną prośbę do weryfikacji, z właściwym fikcyjnym wynikiem. Każda opublikowana treść nadal spełnia granice symulacji. |

## Planowany kanał strony kampanii

| ID | Priorytet | Wymaganie | Kryterium ręcznego odbioru |
| --- | --- | --- | --- |
| FR-32 | P1 / pilotaż kampanii | Trening w przeglądarce | Uczestnik może ukończyć przygotowanie, rozmowę i wynik bez instalowania aplikacji. Oba kanały korzystają z tych samych wersji scenariuszy i reguł. |
| FR-33 | P1 / pilotaż kampanii | Wejście z sekcji „Metoda na Podszywacza” | Po uzgodnieniu z właścicielem strony przycisk w sekcji prowadzi do treningu w serwisie, zatwierdzonym module lub pod uzgodnionym adresem. Wybieramy jeden sposób integracji, nie wszystkie naraz. |
| FR-34 | P1 / pilotaż kampanii | Pomiar kanałów | Panel rozróżnia sesje web/mobile i opcjonalny kod materiału, bez sugerowania liczby unikalnych osób lub łączenia ich między urządzeniami. |

Termin FR-32–34 zależy od decyzji o zakresie hackathonu i współpracy z organizatorem. To wymagania proponowanego wariantu, nie polecenie wdrożenia na rzeczywistej stronie.

Po hackathonie: historia między urządzeniami, role zatwierdzającego, import scenariuszy, eksport analityki, osobny moduł realnych incydentów i inne mechaniki ćwiczeń.
