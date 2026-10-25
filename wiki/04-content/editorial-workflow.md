# Panel i proces redakcyjny

Status: plan P0 do omówienia. Django Admin jest rekomendacją. Szczegółowe FR-14–22: [wymagania](../07-requirements/functional.md).

## Ekrany panelu

| Ekran | Układ i działanie |
| --- | --- |
| A01 Logowanie | Nazwa użytkownika, hasło, komunikat błędu; bez publicznej rejestracji |
| A02 Scenariusze | Tytuł, wersja, status, odsłona kampanii, pakiet odbiorców, cel, data zmiany; przycisk „Dodaj scenariusz” |
| A03 Edytor | Sekcje: odbiorcy i cel kampanii, karta przygotowania, postać i rozmowa, działania, feedback i ochrona bliskich, referencja materiału; polskie etykiety i podpowiedzi |
| A04 Podgląd | Karty edukacyjne, wiadomość startowa, dostępne działania i przykładowe podsumowanie; wyraźne oznaczenie trybu redakcyjnego |
| A05 Publikacja | Lista braków lub potwierdzenie nowej wersji; bez edycji aktywnej wersji w miejscu |
| A06 Statystyki | Liczniki sesji i jawnych decyzji według scenariusza, wersji i powodu zakończenia; pakiet, jeśli obsługiwany; brak listy dzieci i domyślnego wglądu w czaty |

## Cykl treści

Szkic → podgląd → publikacja → wycofanie. Edycja opublikowanej treści tworzy szkic kolejnej wersji. Publikacja sprawdza wymagane pola, dozwolone akcje, obecność feedbacku i limity. Nie zamienia arbitralnego tekstu redaktora w nowe funkcje aplikacji.

Nowa wersja trafia do katalogu po odświeżeniu. Istniejąca sesja zachowuje poprzednią wersję. Wycofanie konkretnej wersji kończy jej aktywne treningi i blokuje nowe uruchomienia; szczegóły w [silniku treningu](../03-architecture/training-engine.md).

Treści domyślnie należą do pakietu 13–15 lat. Dodatkowe pakiety i filtrowanie według odbiorców są P1; nie dokładamy systemu profili użytkowników.

Podgląd P0 jest prezentacją treści i reguł. Interaktywny trening próbny redaktora to P1; jeśli go dodamy, sesje mają preview=true i nie wpływają na statystyki.

## Ergonomia i zakres

W demo jedna uprawniona rola redaktora, bez osobnego obiegu akceptacji. Administrator techniczny tworzy konto; redaktor zarządza treściami. Panel nie oferuje edycji bazowych instrukcji bezpieczeństwa modelu. Nie wymaga pisania JSON, promptów ani kodu. Kopiowanie, wyszukiwanie i filtry są P1.

Django Admin ma służyć wewnętrznej administracji. Gdy podstawowe formularze nie wystarczą do procesu redakcyjnego, można dodać prosty widok Django bez budowania osobnego SPA. [Oficjalna dokumentacja Django](https://docs.djangoproject.com/en/6.1/ref/contrib/admin/) opisuje administracyjny charakter tego narzędzia. Wersja Django pozostaje do wyboru.
