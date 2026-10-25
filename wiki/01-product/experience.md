# Plan doświadczenia aplikacji

Status: propozycja do omówienia, 2026-10-25. Potwierdzona grupa pierwszego prototypu: 13–15 lat. Wymagania źródłowe: [funkcjonalne](../07-requirements/functional.md) i [niefunkcjonalne](../07-requirements/non-functional.md).

## Kierunek

Aplikacja jest proponowanym produktem trzeciej odsłony „Metody na Podszywacza”. Publiczny kontekst i naszą propozycję odróżnia [brief kampanii](campaign-third-edition.md). Pierwsza treść dla 13–15 lat to początek programu dla [różnych odbiorców](audiences.md).

Krótki trening w fikcyjnym komunikatorze: wejście z kampanii → przygotowanie → wybór sytuacji → rozmowa → decyzja → wyjaśnienie i wskazówka ochrony bliskich. Zakładamy ćwiczenie około 2–4 minut; to cel projektowy, nie wynik pomiaru. Proponujemy start bez konta. Język prosty, bez infantylizacji, oceniania charakteru i zawstydzania.

Dwa główne miejsca w aplikacji: Trenuj oraz Przygotuj się. Zasady i informacja o AI pozostają dostępne w obu miejscach. Nie pokazujemy pustych modułów „wkrótce”. Historia, rankingi, odznaki, powiadomienia i osobny asystent analizujący prawdziwe wiadomości pozostają poza pierwszym demo.

## Mapa ekranów

| Ekran | Co widać | Najważniejsze działanie | Gdy coś nie działa |
| --- | --- | --- | --- |
| M01 Powitanie | XYZ Defender, „Przećwicz swoją metodę na Podszywacza”, cel treningu i zasady fikcyjnych rozmów | Rozpocznij trening | Nie wymaga AI; można przeczytać zasady bez sieci |
| M02 Trenuj | Karty opublikowanych scenariuszy: tytuł, kontekst, cel kampanii i czas; w demo pakiet 13–15 lat | Wybierz scenariusz | Brak treści: neutralny komunikat; błąd sieci: spróbuj ponownie |
| M03 Przed rozmową | Fikcyjny kontekst, cel, krótka karta przygotowania i informacja „Symulacja z AI” | Zaczynam | Wycofany scenariusz: powrót do listy |
| M04 Rozmowa | Stała etykieta symulacji, fikcyjna postać, wiadomości, pole odpowiedzi, pasek działań | Odpowiedz lub podejmij decyzję | Oczekiwanie, brak sieci i błąd AI opisane osobno; wyjście zawsze dostępne |
| M05 Wynik | Co zrobiłeś, czego nie zaobserwowaliśmy, związek z metodą Podszywacza, wskazówka ochrony bliskich i powód zakończenia | Spróbuj ponownie lub wróć do listy | Gdy sesja niepełna: podsumowanie częściowe, bez udawania pełnej oceny |
| M06 Przygotuj się | Redagowane karty: ochrona konta i bliskich; zasady symulacji, informacja o AI i wsparciu dorosłego | Wróć do treningu | Treść statyczna; brak improwizowanych porad kryzysowych |

Pierwsze powitanie można zapamiętać lokalnie, ale oznaczenie symulacji i możliwość odczytania zasad pozostają dostępne. Ekran M06 nie jest modułem reagowania na rzeczywisty incydent.

## Układ ekranu rozmowy

Od góry: powrót i nazwa scenariusza; widoczna etykieta „Symulacja z AI”; przewijany obszar wiadomości; dostęp do działań; pole odpowiedzi i przycisk Wyślij. Klawiatura nie zasłania pola ani przycisku zakończenia.

Działania: „Zweryfikuj innym kanałem”, „Poproś zaufanego dorosłego o pomoc”, „Zakończ kontakt”. W scenariuszu może być także ryzykowny wybór „Przekaż fikcyjne dane w ćwiczeniu” — jako jawna decyzja symulacyjna, bez pola na prawdziwy kod. Uzasadnienie i skutki pokazujemy w podsumowaniu.

Wybranie weryfikacji uruchamia fikcyjny wynik opisany przez scenariusz. Aplikacja nie dzwoni i nie otwiera kontaktów. Wybranie pomocy dorosłego jest jedynie działaniem edukacyjnym.

## Przebiegi

- Podstawowy: M01 → M02 → M03 → M04 → M05 → M02.
- Przerwanie: M04 → „Zakończ ćwiczenie” → M05 z oznaczeniem przerwania i bez kary.
- Niedostępne AI: M04 → komunikat → ponowienie tej samej tury albo zakończenie z częściowym wynikiem.
- Powrót z tła: odczyt stanu aktywnej sesji, jeśli lokalny token nadal istnieje; po wygaśnięciu powrót do katalogu z wyjaśnieniem.

## Rozwój pakietów i wejście z kampanii

W demo domyślny pakiet dla 13–15 lat, bez pytania o datę urodzenia. W P1 użytkownik może wybrać kontekst pakietu lub wejść do niego z linku kampanii. Link działa dla zainstalowanej aplikacji; odtworzenie wyboru po instalacji pozostaje osobną decyzją. Treści dla dorosłych i seniorów nie pojawiają się jako gotowe, dopóki nie zostaną opracowane i opublikowane.

## Wariant na stronie kampanii

Na stronie XYZ w sekcji „Metoda na Podszywacza” można zaproponować rozpoczęcie krótkiego ćwiczenia bez instalacji. W przeglądarce użytkownik przechodzi przygotowanie, rozmowę i wynik z tych samych wersji treści. Docelowy układ musi działać na telefonie i komputerze; nie kopiujemy całego panelu na stronę uczestnika. Ekrany web i forma osadzenia pozostają do opracowania.

[Trening web i mobile](../03-architecture/web-and-mobile.md) opisuje warianty publikacji. To zastosowanie produktu, a nie gotowa funkcja rzeczywistego serwisu organizatora.

## Styl wizualny

Jasne tło, ciemny tekst, jeden główny kolor akcentu oraz spójne karty. Bez kopiowania popularnych komunikatorów i bankowości. Neutralne fikcyjne awatary, krótkie komunikaty i opisy tekstowe obok ikon. Kolor nie jest jedynym nośnikiem oceny. Przygotowano [makiety graficzne v2](mockups.md): czerń, biel i czerwony akcent `#E80000` odczytany z oficjalnej strony organizatora, zgodnie z decyzją właściciela. Szczegółowy układ pozostaje do akceptacji.

## Panel redakcyjny

Osobny widok w przeglądarce dla organizatora, przeznaczony przede wszystkim na komputer. Ekrany i publikację opisuje [proces redakcyjny](../04-content/editorial-workflow.md). Dziecko nie widzi panelu ani danych administratora.
