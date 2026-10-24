# Dane i kontrakt API — zarys

## Proponowane pojęcia

- Scenariusz: tożsamość i metadane.
- Wersja scenariusza: treść, cele, granice dialogu, reguły oceny, status publikacji.
- Sesja: konkretna wersja scenariusza i aktualny etap.
- Wiadomość: uczestnik i treść; trwałe przechowywanie pozostaje otwarte.
- Decyzja: jawna akcja użytkownika i kontekst.
- Wynik: kryteria oraz wyjaśnienie.
- Kampania: grupa dostępnych scenariuszy i agregaty wykorzystania.

Opublikowana wersja użyta przez sesję nie zmienia się po edycji. Publikacja zmian tworzy kolejną wersję. Wycofanie blokuje nowe sesje; zachowanie istniejących wymaga decyzji.

## Operacje API

Lista dostępnych scenariuszy, rozpoczęcie sesji, wysłanie odpowiedzi lub decyzji, zakończenie sesji i pobranie wyniku. Szczegółowy kontrakt OpenAPI powstanie dopiero na etapie implementacji.

Token sesji nie powinien umożliwiać dostępu do cudzych rozmów. Redaktor loguje się niezależnie od anonimowego uczestnika.

## Otwarte

Retencja, przechowywanie czatu, odtwarzanie sesji, limity wykorzystania, konta uczestników i sposób powiązania wejścia z kampanią. Statystyki nie powinny wymagać identyfikowania dziecka.
