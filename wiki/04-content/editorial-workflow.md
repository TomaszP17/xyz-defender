# Panel i proces redakcyjny

## Ustalone

Administratorzy muszą móc wygodnie zarządzać scenariuszami i wprowadzać nowe teksty.

## Proponowany minimalny panel

- Lista scenariuszy z wyszukiwaniem i filtrem statusu oraz wieku.
- Polski, uporządkowany formularz z opisami pól.
- Kopiowanie istniejącego scenariusza jako szkicu.
- Podgląd treści przed publikacją.
- Publikacja i wycofanie.
- Proste zagregowane statystyki rozpoczęć i ukończeń.

Cykl: szkic → podgląd → publikacja → wycofanie. Walidacja wymaganych pól poprzedza publikację. Wersje użyte przez sesje pozostają niezmienne.

Django Admin jest rekomendacją początkową, nie zaakceptowanym finalnym projektem UX. Nie planujemy edytora grafowego ani przeciągania bloków.

Na hackathon wystarczy jedna rola redaktora. Rozdzielenie autora i zatwierdzającego pozostaje późniejszą możliwością. Podgląd powinien jasno oddzielać sesje redakcyjne od statystyk uczestników.
