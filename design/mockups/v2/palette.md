# Paleta makiet v2

Data odczytu: 2026-10-25. Właściciel zlecił zastosowanie czerni, bieli i czerwieni odczytanych z oficjalnej strony organizatora XYZ. Nazewnictwo produktu pozostaje XYZ.

## Źródło wartości

Sprawdzono HTML strony głównej i wskazany przez nią arkusz `/layout/default/dist/css/home.bundle.css?1792739116`.

| Kolor | Wartość | Obserwacja w CSS | Zastosowanie w makiecie |
| --- | --- | --- | --- |
| Czarny | `#000000` | Wartość `#000` w kolorach tekstu i elementach strony | Typografia, hero, ramki, wiadomość uczestnika |
| Biały | `#FFFFFF` | Wartość `#fff` w tłach i tekście | Powierzchnie, tekst na czerwonych przyciskach |
| Czerwony | `#E80000` | Składowa gradientu w `.content-img-top-2__btn-scroll-down` i `.content-title-list-video__item-number` | Jednolite wypełnienie przycisków, znaku XYZ i akcentów |

To wybór trzech kolorów występujących na stronie do potrzeb makiety. CSS zawiera także czerwień `#E52F08` w `.button--red` i wielobarwne gradienty. W v2 używamy `#E80000`, aby uzyskać czytelny biały tekst i zachować wskazaną przez właściciela paletę.

SHA-256 pobranego CSS: `e1c4916481b87235cbe76eb89b009b323448ca72c75986db21b64da98b748070`.

## Zastosowanie i kontrast

Biały tekst na `#E80000` ma obliczony kontrast około 4,74:1. Neutralne szarości są pomocniczą decyzją projektu UI. Bezpieczne obserwacje rozróżniamy opisem i ikoną, a czerwieni używamy jako akcentu marki. Dotychczasowa zielona i pomarańczowa kolorystyka pozostaje wyłącznie w historycznej wersji v1.

Wygląd makiet v2 jest propozycją do omówienia. Nie stanowi zatwierdzonego systemu identyfikacji organizatora. Zakres aplikacji i scenariusze pozostają opisane w wiki.
