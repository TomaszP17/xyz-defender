# Plan omówienia projektu

Celem jest wspólne doprecyzowanie doświadczenia, architektury i wymagań przed kodowaniem. Czytaj w kolejności:

1. [Plan ekranów i ścieżek](../01-product/experience.md): czy tak ma wyglądać trening dla wieku 13–15 lat?
2. [Proces redakcyjny](../04-content/editorial-workflow.md): czy organizator potrafi samodzielnie opublikować treść?
3. [Architektura](../03-architecture/overview.md) i [silnik treningu](../03-architecture/training-engine.md): kto steruje rozmową i jak powstaje wynik?
4. [Wymagania funkcjonalne](../07-requirements/functional.md): co jest niezbędne w demo?
5. [Wymagania niefunkcjonalne](../07-requirements/non-functional.md): czy proponowane ograniczenia i cele są odpowiednie?
6. [Ręczny odbiór](../07-requirements/demo-acceptance.md): co będzie można pokazać działającego?

## Decyzje w pierwszej kolejności

- Zatwierdzenie lub zmiana Django, panelu Admin, DRF, PostgreSQL i Expo.
- Akceptacja rozmowy swobodnej z oceną opartą na jawnych działaniach zamiast interpretacji AI.
- Jeden pełny scenariusz P0 jako pionowa ścieżka demo; liczba kolejnych zależna od czasu.
- Start bez konta, platforma pierwszego telefonu i zakres zapisu rozmów.

Zatwierdzony przedział pierwszego prototypu: 13–15 lat. Pozostałe szczegóły nie stają się zatwierdzone wskutek zapisania dokumentacji.

## Przekładanie na zadania agentów

Zadanie wskazuje cel, FR/NFR, powiązany ekran, granicę modułu, dozwolone pliki oraz ręczny odbiór. Kolejność: panel i katalog → sesja i działania → wynik → adapter AI i błędy → statystyki → kontener i wdrożenie.

Przykład przyszłego zadania: „Dodaj publikację scenariusza FR-15/17/18 w module content i panelu A03/A05; odbiór: szkic niewidoczny w M02, po publikacji widoczna nowa wersja, stara sesja zachowuje wersję”. To opis zadania, nie polecenie implementacji teraz.
