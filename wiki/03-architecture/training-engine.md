# Silnik treningu

Status: proponowana mechanika hackathonu. Powiązania: FR-04–12, FR-18–19, FR-23–25.

## Stany

| Stan | Znaczenie | Przejście |
| --- | --- | --- |
| ACTIVE | Trening trwa, można podjąć działanie | Wiadomość, decyzja albo zakończenie |
| COMPLETED | Osiągnięto warunek końcowy lub limit tur | Wynik; bez nowych wiadomości |
| STOPPED | Uczestnik przerwał | Częściowy wynik, bez kary |
| ERROR | Błąd uniemożliwił dalszy trening i użytkownik zakończył | Częściowy wynik |
| WITHDRAWN | Wycofano używaną wersję | Neutralne zakończenie, bez oceny porażki |
| EXPIRED | Przekroczono czas życia sesji | Informacja o wygaśnięciu i nowy trening |

Oczekiwanie na model to status pojedynczej operacji, nie osobny stan całej sesji. Limit i planowany czas życia pochodzą z ustawień serwera; propozycja: 6 ukończonych tur i 30 minut na aktywną sesję. Wygaśnięcie ustalamy podczas dostępu do sesji i podczas zadania porządkującego, bez osobnego serwisu.

## Etapy treści

Wprowadzenie, próba wywarcia presji, decyzja i podsumowanie. Scenariusz konfiguruje teksty, dopuszczone działania i warunki zakończenia w ramach tej jednej mechaniki. Nie budujemy dowolnego grafu zdarzeń na hackathon.

Bezpieczny wybór weryfikacji lub pomocy dorosłego może kończyć trening z przygotowanym fikcyjnym rezultatem. Ryzykowny wybór to zdarzenie w symulacji, nigdy rzeczywisty sekret. Nie wymagamy prawdziwej czynności poza telefonem jako warunku zaliczenia.

## Wynik

Każde kryterium ma identyfikator, opis, zestaw jawnych działań stanowiących dowód oraz tekst wyjaśnienia. Obserwacja przyjmuje wartość: bezpieczne zachowanie, ryzykowne zachowanie lub nie zaobserwowano. Sesja niepełna nie otrzymuje fikcyjnego pełnego wyniku. W demo wystarcza lista obserwacji bez procentowej oceny człowieka.

Zmiana oceny nie wymaga wywołania modelu. Reguły i feedback pochodzą z wersji przypisanej przy starcie. Tekst uczestnika nie jest interpretowany automatycznie jako pewny dowód działania w pierwszym wariancie.

## Współbieżność i błędy

Każda zmiana ma identyfikator operacji i numer oczekiwanej rewizji sesji. Powtórzenie tej samej zakończonej operacji zwraca zapisany rezultat. Operacja o innym identyfikatorze, gdy tura trwa, zwraca konflikt. Pomyślna tura zwiększa licznik raz.

Timeout modelu zwalnia rezerwację z błędem; powtórzenie błędnej operacji nie wykonuje automatycznie nowego płatnego wywołania. Świadome „Spróbuj ponownie” tworzy nową próbę powiązaną z tą samą turą. Po restarcie backendu przeterminowana rezerwacja przechodzi w błąd, a użytkownik decyduje o ponowieniu.

Zakończenie przez użytkownika oraz wycofanie mają pierwszeństwo przed zapisem odpowiedzi AI. Backend sprawdza status po powrocie dostawcy i odrzuca nieaktualną odpowiedź. Nie trzymamy blokady bazy podczas wywołania sieciowego.

## Wycofanie

Publikacja kolejnej wersji nie zmienia istniejących sesji. Wycofanie konkretnej wersji blokuje nowe starty i zamyka jej aktywne sesje. Usuwa też tę wersję z oferty. Zatwierdzone wyniki już zakończonych sesji pozostają historyczne, z oznaczeniem wersji; nie prezentujemy dalej wycofanych treści dialogu.
