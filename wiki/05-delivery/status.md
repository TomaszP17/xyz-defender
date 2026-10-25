# Status projektu

Data: 2026-10-25. Etap: planowanie, dokumentacja, makiety graficzne i prezentacja, bez implementacji produktu.

## Potwierdzone

Kierunek: propozycja produktu trzeciej odsłony „Metody na Podszywacza” organizatora XYZ. Docelowo dzieci, młodzież, dorośli, rodziny i seniorzy przez odpowiednie pakiety. Pierwszy prototyp dla wieku 13–15 lat. Aplikacja mobilna oraz uzgodniona możliwość pełnego krótkiego treningu na stronie XYZ w sekcji „Metoda na Podszywacza”, bez instalacji. Termin web pozostaje otwarty. Python jako backend. Panel scenariuszy. Projekt hackathonowy, prosta architektura. Konteneryzacja i Kubernetes. Bez automatycznych testów na tym etapie. Prywatne repozytorium, neutralna nazwa XYZ. Na polecenie właściciela do Markdown dołączono makiety PNG.

## Przygotowane do omówienia

Plan sześciu ekranów mobilnych i sześciu widoków panelu, granice modułów, przepływ tury AI, stany sesji, wersjonowanie treści, propozycja danych i operacji API, wdrożenie, 34 wymagania funkcjonalne i 21 niefunkcjonalnych oraz ścieżki ręcznego odbioru. Uzupełniono brief proponowanej trzeciej odsłony, pakiety odbiorców i program C01–C06. To specyfikacja robocza, nie działająca aplikacja; współpraca z organizatorem nie jest potwierdzona.

Przygotowano [makiety graficzne v2](../01-product/mockups.md): sześć ekranów mobile i sześć widoków panelu oraz lokalne podglądy klikalne. Właściciel wybrał czerń, biel i czerwień ze strony organizatora; v2 stosuje tę paletę. Układ pozostaje do omówienia.

Przygotowano [prezentację produktu v2](../../presentations/v2/README.md): 15 slajdów w PowerPoint i PDF. Prezentacja podkreśla trening na stronie w sekcji „Metoda na Podszywacza”, kanały web/mobile i priorytety rozwoju oraz zawiera makiety v2.

Dodano [katalog 22 możliwości](../01-product/opportunity-catalog.md) i [wariant web/mobile](../03-architecture/web-and-mobile.md). Katalog nie jest automatycznym zakresem MVP. Wariant web rekomendujemy przed szerszą kampanią; sposób integracji wymaga uzgodnienia z właścicielem strony.

## Propozycje do zatwierdzenia

Django i Django Admin, DRF, Expo, PostgreSQL, modularny monolit, start bez konta, ocena jawnych działań, zakres P0/P1, limity techniczne i retencja. Wycofanie wersji proponujemy jako zatrzymanie jej aktywnych treningów.

## Najbliższy krok

Omówić [koncepcję kampanii](../01-product/campaign-third-edition.md) i ustalić kanał rozmowy z organizatorem. Następnie przejść [plan omówienia](review-guide.md), zatwierdzić stos i mechanikę treningu oraz dopracować pierwszy scenariusz. Ustalić czas wydarzenia i liczbę osób. Nie rozpoczynać kodowania na podstawie samego istnienia specyfikacji.
