# Możliwości produktu i ich sens dla XYZ

Data: 2026-10-25. Status: analiza i rekomendacje, nie zatwierdzony backlog implementacji. Produkt proponujemy jako trzecią odsłonę „Metody na Podszywacza”. Zachowujemy pierwsze demo dla 13–15 lat i wizję innych grup odbiorców.

## Główna rekomendacja

Jeden program treningowy, wspólny katalog scenariuszy i panel, dostępne w aplikacji mobilnej oraz przez przeglądarkę. **Trening może działać bezpośrednio na stronie XYZ w sekcji „Metoda na Podszywacza”, bez instalowania aplikacji.** Wariant webowy warto przygotować przed szerszym kierowaniem ruchu z kampanii. To rekomendacja kolejności, nie rozpoczęcie implementacji obu klientów na hackathon.

Strona może obsługiwać pierwsze, krótkie ćwiczenie po kontakcie z kampanią. Aplikacja mobilna może ułatwiać kolejne treningi i dobrowolne powtórki. Wpływ instalacji na ukończenia i rzeczywiste powroty wymagają pomiaru.

## Jak oceniamy pomysły

Sens oznacza związek z metodą podszywania, konkretne zachowanie użytkownika, użytek dla organizatora i możliwość oceny rezultatu. Złożoność jest względną oceną projektową, bez szacunku dni i kosztu. „Rdzeń” nie oznacza, że wszystkie pozycje trzeba wykonać równocześnie.

## Największa wartość: rdzeń i wczesny pilotaż

| ID | Możliwość | Konkretny użytek | Jak sprawdzić wartość | Złożoność i zależność |
| --- | --- | --- | --- | --- |
| O01 | Trening w sekcji kampanii na stronie XYZ | Odbiorca uruchamia ćwiczenie podczas czytania materiału, bez instalacji | Rozpoczęcia i ukończenia treningu w tym kanale | Średnia: klient web i uzgodnienie publikacji |
| O02 | Rozmowa z kontrolowanym AI | Uczestnik ćwiczy reakcję na nacisk zamiast jedynie czytać ostrzeżenie | Decyzja w nowej sytuacji po treningu | Rdzeń silnika i adapter AI |
| O03 | Wyjaśnienie decyzji i ponowne podejście | Uczestnik rozumie, dlaczego warto sprawdzić rozmówcę | Zrozumienie feedbacku i inna reakcja przy powtórce | Mała po wdrożeniu rdzenia |
| O04 | Panel redakcyjny i wersje | Zespół kampanii aktualizuje preteksty i teksty bez nowego wydania klienta | Publikacja treści przez redaktora i wykorzystanie nowej wersji | Rdzeń zarządzania treściami |
| O05 | Pakiety dla odbiorców | Ten sam program trafia do młodzieży, dorosłych, rodzin i seniorów w odpowiednim języku | Zrozumiałość i ukończenia dla danej grupy | Średnia: redakcja i osobne sprawdzenie UX |
| O06 | Krótkie przygotowanie i ochrona bliskich | Program wiąże ochronę konta, 2FA i weryfikację prośby z bezpieczeństwem kontaktów | Odpowiedzi na zadanie i wywiad po ćwiczeniu | Mała: redagowane karty, bez połączenia z kontami |
| O07 | Różne preteksty i zwyczajne wiadomości | Trening uczy weryfikacji także wtedy, gdy prośba okaże się prawdziwa | Rozróżnienie nowej próby i legalnej prośby | Mała/średnia: treści i fikcyjne rezultaty |
| O08 | Link lub QR do konkretnego ćwiczenia | Materiał kampanii kończy się konkretną aktywnością, także na wydarzeniu | Ukończenia według kodu materiału, bez identyfikacji osoby | Mała po uruchomieniu web; deep link mobile osobno |
| O09 | Zagregowane statystyki programu | Organizator widzi, gdzie uczestnicy kończą, przerywają lub podejmują ryzykowne decyzje | Przydatność raportu do zmiany treści | Mała po wdrożeniu sesji, zasady małych grup |
| O10 | Sprawdzenie przed i po treningu | Organizator ocenia przyrost umiejętności wobec samego materiału kampanii | Nowe zadanie, grupa porównawcza i ponowny pomiar po czasie | Średnia: metodyka, treści i warunki pilotażu |

## Wartościowy rozwój po potwierdzeniu rdzenia

| ID | Możliwość | Konkretny użytek | Jak sprawdzić wartość | Złożoność i zależność |
| --- | --- | --- | --- | --- |
| O11 | Fikcyjne podsumowanie operacji | Uczestnik uczy się czytać kwotę, odbiorcę i rodzaj operacji przed decyzją | Wskazanie niezgodności w nowym przykładzie | Średnia: nowa mechanika, neutralny ekran bez bankowego API |
| O12 | Konteksty odbioru pieniędzy i prośby o kod | Rozróżnienie obietnicy pieniędzy od żądania autoryzowania działania | Rozpoznanie konkretnego żądania w zadaniu | Średnia: treść zatwierdzona przez eksperta ds. płatności |
| O13 | Trening rodzinny na jednym urządzeniu | Rodzina omawia prośbę i uzgadnia niezależny sposób sprawdzenia tożsamości | Ocena przydatności rozmowy i kolejny scenariusz | Mała/średnia: wspólna instrukcja, bez czatu między dziećmi |
| O14 | Zajęcia szkolne i warsztatowe | Prowadzący udostępnia kod ćwiczenia i omawia fikcyjne decyzje z grupą | Ukończenia i ocena prowadzącego | Średnia: materiały prowadzącego; brak rankingów dzieci |
| O15 | Zweryfikowane wskazówki po realnym incydencie | Odbiorca dociera do oficjalnych kanałów pomocy | Czytelność i trafność wskazanego kanału | Średnia: przegląd treści i utrzymanie odnośników; bez generatywnej diagnozy |
| O16 | Powtórki i sytuacje sezonowe | Produkt przypomina umiejętność w innym kontekście, np. zakupów lub konkursu | Dobrowolne powroty i poprawna reakcja po czasie | Średnia: treści i opcjonalne przypomnienia |
| O17 | Dostępność i prostszy tryb | Osoby mniej pewne cyfrowo łatwiej kończą ćwiczenie | Czytelność i samodzielne wykonanie przez odbiorców | Mała dla typografii, większa dla nowych sposobów interakcji |
| O18 | Asystent redaktora tworzący szkice | Zespół szybciej opracowuje warianty pretekstu i stylu | Czas pracy oraz liczba poprawek do publikacji | Średnia: wyłącznie szkice, redaktor akceptuje każdą wersję |
| O19 | Materiały do podzielenia się treningiem | Odbiorca udostępnia publiczny link do ćwiczenia lub przygotowaną poradę | Wejścia i ukończenia z linku | Mała: bez eksportu prywatnej rozmowy i bez wysyłania w imieniu aplikacji |
| O20 | Języki i lokalizacja | Kampania może objąć odbiorców korzystających z innych języków | Zrozumienie po tłumaczeniu i ocena redaktora | Średnia: redakcja, terminologia i scenariusze kulturowe |

## Warunkowo: sens zależy od partnera i danych

| ID | Możliwość | Użytek | Warunek |
| --- | --- | --- | --- |
| O21 | Dystrybucja przez banki i innych partnerów | Partner odsyła do uzgodnionego treningu edukacyjnego | Najpierw link i wspólna kampania; SDK lub osadzenie dopiero po decyzji partnera |
| O22 | Porównanie formatów i raport edukacyjny kampanii | Organizator wybiera lepsze materiały i dokumentuje rezultaty programu | Rzetelna metodyka, odpowiednia liczebność i ochrona małych grup; nie raport z samych punktów gry |

## Czego obecnie nie rekomenduję

- Automatycznego czytania prywatnych wiadomości oraz blokowania płatności: wymaga innych uprawnień i nie służy obecnemu produktowi treningowemu.
- Gwarancji „wiadomość jest bezpieczna”, oceniania prawdziwej transakcji i certyfikatu odporności: wynik symulacji tego nie uzasadnia.
- Publicznego rankingu dzieci, reklamowych profili i obowiązkowego konta na start: brak potwierdzonej wartości dla kampanii i wzrost bariery wejścia.
- Otwartych scenariuszy tworzonych przez uczestników i automatycznej publikacji AI: zespół traci kontrolę redakcyjną.
- Samodzielnych symulowanych połączeń do osób trzecich, klonowania głosu i kopiowania bankowości: to nowa, znacznie bardziej złożona forma produktu.
- Modułu „Sprawdź prawdziwą wiadomość” w pierwszej wersji: wymaga osobnej walidacji jakości i danych, a jego wartość dla tej kampanii nie jest jeszcze wykazana.

## Rekomendowana kolejność

1. Jeden pełny scenariusz, panel i zrozumiały feedback dla 13–15 lat.
2. Lekki trening web przed kierowaniem większego ruchu z kampanii; aplikacja mobilna nadal pozostaje częścią produktu.
3. Kilka wariantów, legalna prośba, linki kampanii i pomiar efektu.
4. Kolejne grupy, rodzina/warsztaty, ćwiczenie potwierdzenia operacji i rozwój zależny od wyników.
5. Dystrybucja partnerska po potwierdzeniu zainteresowania i warunków współpracy.

Nie dokładamy 22 funkcji do MVP. Koszt AI, utrzymanie redakcji i koszt dystrybucji trzeba zestawić z ukończeniami i efektem edukacyjnym. Ograniczenie rzeczywistych strat wymagałoby osobnego badania i współpracy z odpowiednimi instytucjami.

## Podstawa analizy

Publiczna [strona kampanii](https://podszywacze.pl/) i materiały „Dobre nawyki” organizatora omawiają ochronę kont i weryfikację. Są podstawą tematyczną, a nie potwierdzeniem popytu na naszą aplikację. Możliwości O01–O22 oraz priorytety to nasza analiza. Szczegóły wariantu na stronie: [web i mobile](../03-architecture/web-and-mobile.md).
