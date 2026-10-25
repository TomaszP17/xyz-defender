# Makiety graficzne XYZ Defender

Data: 2026-10-25. Status: propozycja do omówienia. Właściciel zlecił wykonanie makiet; nie oznacza to rozpoczęcia implementacji produktu ani zatwierdzenia projektu graficznego.

## Gdzie oglądać

[Plansza mobilna i komplet 12 ekranów](../../design/mockups/v2/README.md) obejmują sześć ekranów aplikacji oraz sześć widoków panelu. Klikalne podglądy są dostępne w rozmowie, a ich lokalne źródła w katalogu `Desktop/xyz-defender-mockups`.

## Co pokazujemy

- Powitanie osadzone w propozycji trzeciej odsłony kampanii.
- Jeden dostępny trening pakietu 13–15 lat, bez pustych funkcji „wkrótce”.
- Przygotowanie, fikcyjną rozmowę, jawne działania i podsumowanie obserwacji.
- Osobny panel organizatora: edycję treści, celów i kart, podgląd, publikację i statystyki.

W klikalnej makiecie można przejść przez trening, wybrać różne decyzje i zobaczyć ich podsumowania. Pole tekstowe służy wyłącznie demonstracji układu; odpowiedź nie jest generowana przez AI. Panel pozwala przejść z edycji do podglądu i symulowanej publikacji. Nie ma rzeczywistego logowania i zapisu do bazy; zmiany są tymczasowe.

## Propozycja stylu

Wersja v2 stosuje czerń `#000000`, biel `#FFFFFF` i czerwień `#E80000` odczytane z CSS oficjalnej strony organizatora. Neutralne szarości porządkują tła; bezpieczne obserwacje mają opis i ikonę. [Źródło palety](../../design/mockups/v2/palette.md). Proste ikony, spójne karty i krótkie komunikaty. Zachowujemy neutralną nazwę XYZ. Podgląd klikalny ma też wariant kolorów odpowiadający ciemnemu wyglądowi otoczenia; pliki PNG pokazują wariant jasny.

Makiety nie deklarują spełnienia wszystkich parametrów NFR. Dokładne rozmiary tekstu, obszary dotykowe i dostępność zostaną dopracowane po akceptacji kierunku. Również układ panelu jest propozycją ergonomii, a nie gotową konfiguracją Django Admin.

[Poprzednia wersja v1](../../design/mockups/v1/README.md) pozostaje dostępna do porównania. Klikalne źródła bieżącej wersji mają nazwy `xyz-mobile-v2.html` i `xyz-admin-v2.html`.

## Do omówienia

Czy ton i wygląd pasują do 13–15 lat? Czy rozmowa powinna pokazywać wszystkie działania od razu? Czy redaktorowi odpowiada układ formularza z podglądem? Czy przygotowanie przed ćwiczeniem ma być krótsze?

Źródło zachowań: [plan ekranów](experience.md) i [proces redakcyjny](../04-content/editorial-workflow.md). Makiety nie zmieniają priorytetów P0/P1 zapisanych w wymaganiach.
