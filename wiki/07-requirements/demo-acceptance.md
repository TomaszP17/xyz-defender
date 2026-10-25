# Ręczny odbiór demonstracji

Nie jest to plan automatycznych testów. Po implementacji wystarczy zapisać datę, urządzenie, środowisko i obserwowany wynik poniższych przebiegów. Teraz żaden punkt nie jest wykonany.

| Przebieg | Działanie | Oczekiwany rezultat | Powiązanie |
| --- | --- | --- | --- |
| Publikacja → trening | Redaktor tworzy szkic z celem kampanii, kartami i referencją, ogląda podgląd, publikuje; uczestnik odświeża katalog i rozpoczyna trening | Nowa treść i karty widoczne bez wdrożenia; podgląd nie zwiększa statystyk | FR-03, FR-15–17, FR-27–28, NFR-16 |
| Bezpieczna decyzja | Uczestnik wybiera weryfikację innym kanałem | Fikcyjny rezultat weryfikacji i wyjaśnienie zachowania; brak realnego połączenia | FR-06, FR-10 |
| Ryzykowna decyzja | W nowej sesji wybiera przekazanie fikcyjnych danych | Inne podsumowanie; brak prośby o prawdziwy kod | FR-07, FR-25 |
| Zmiana treści | Redaktor publikuje nową wersję podczas aktywnego treningu | Stara sesja zachowuje stare reguły; nowe używają nowej wersji | FR-18 |
| Wycofanie | Redaktor wycofuje wersję używaną w sesji | Nowy start zablokowany, aktywna sesja zakończona neutralnym komunikatem | FR-19, FR-24 |
| Błąd i przerwanie | Wyłączyć dostęp do modelu, ponowić żądanie, zakończyć ćwiczenie | Brak duplikatów, czytelny błąd i częściowy wynik; UI pozostaje dostępne | FR-08, FR-12, NFR-06, NFR-08 |
| Granice dostępu | Spróbować wejść bez logowania do panelu i odczytać inną sesję | Odmowa dostępu, brak ujawnienia treści i sekretów | FR-14, FR-26, NFR-09 |
| Wdrożenie i podsumowanie | Zrestartować backend; otworzyć panel statystyk i katalog | Treści i zapisane wyniki zachowane; liczniki rozróżniają powody zakończenia | FR-21, NFR-14 |

Przekrojowo sprawdzamy widoczne oznaczenie symulacji, działanie klawiatury, czytelność powiększonego tekstu oraz brak prawdziwych danych w logach. Wynik demo nie jest dowodem skuteczności edukacyjnej produktu.
