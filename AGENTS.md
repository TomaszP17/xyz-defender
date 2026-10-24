# Instrukcje dla agentów

## Kolejność czytania

Przeczytaj README.md, agents/working-agreement.md, wiki/05-delivery/status.md i dokumenty związane z zadaniem. Otwarte kwestie sprawdzaj w wiki/05-delivery/open-decisions.md.

## Obowiązujące ustalenia

- Pracujemy po polsku. Nazwa projektu i partnera: wyłącznie XYZ.
- Obecny etap to dokumentacja. Twórz i edytuj wyłącznie pliki `.md`; nie generuj kodu, scaffoldingu, manifestów ani zależności.
- Odbiorcami są dzieci i młodzież. Dokładny wiek nie jest ustalony.
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
