# Instrukcje dla agentów

## Kolejność czytania

Przeczytaj README.md, agents/working-agreement.md, wiki/05-delivery/status.md i dokumenty związane z zadaniem. Otwarte kwestie sprawdzaj w wiki/05-delivery/open-decisions.md. Plan omawiania specyfikacji: wiki/05-delivery/review-guide.md. Identyfikatory FR i NFR mają źródło w wiki/07-requirements/.

## Obowiązujące ustalenia

- Pracujemy po polsku. Nazwa projektu i partnera: wyłącznie XYZ.
- Obecny etap to dokumentacja i makiety. Domyślnie pracuj w `.md`; właściciel 2026-10-25 zlecił także makiety graficzne, zapisane w `design/mockups/`. To nie jest zgoda na kod aplikacji, scaffolding, manifesty i instalację zależności projektu. Klikalne źródła makiet są poza repozytorium w `Desktop/xyz-defender-mockups`.
- Pierwszy prototyp kierujemy do wieku 13–15 lat, zgodnie z decyzją właściciela z 2026-10-25. Szersza wizja obejmuje dzieci, młodzież, dorosłych, rodziny i seniorów przez odpowiednio opracowane pakiety.
- Produkt proponujemy jako trzecią odsłonę „Metody na Podszywacza” organizatora XYZ: przygotowanie, trening reakcji i ochrona bliskich. To kierunek produktu, nie ogłoszony plan organizatora. Przeczytaj wiki/01-product/campaign-third-edition.md.
- Produkt ma być aplikacją mobilną; panel administracyjny jest kluczowym modułem.
- Backend ma być w Pythonie. Nie proponuj Javy ani Springa.
- Zakres hackathonowy; bez planowania kompletnego systemu produkcyjnego i bez automatycznych testów na tym etapie.
- Docelowy backend ma nadawać się do konteneryzacji i wdrożenia na Kubernetes.
- Odróżniaj ustalenia użytkownika, rekomendacje i otwarte decyzje.
- Nie używaj diagramów Mermaid.

## Praca nad zmianą

Wybierz jeden ograniczony temat. Przeczytaj jego źródłowy dokument. Aktualizuj powiązane odnośniki i status decyzji. Nie powielaj pełnych wymagań w kilku miejscach. Nie zmieniaj rekomendacji w zatwierdzone wymaganie bez decyzji właściciela.

Nie dodawaj funkcji tylko dlatego, że są łatwe do wygenerowania. Zachowuj bezpieczeństwo symulacji: bez rzeczywistych sekretów, transakcji, kontaktowania osób trzecich i nieoznaczonego podszywania się.

## Zakończenie pracy

Podaj zmienione dokumenty, decyzje wymagające właściciela i następny konkretny krok. Uaktualnij status, jeśli etap lub zakres się zmienił. Zasady przekazania: agents/handoff.md.
