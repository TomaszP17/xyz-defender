# Technologie

| Obszar | Status | Wybór |
| --- | --- | --- |
| Backend | Ustalone przez właściciela | Python |
| Framework backendu | Rekomendacja | Django + Django REST Framework |
| Panel | Rekomendacja | Dostosowany Django Admin |
| Mobile | Rekomendacja; frontend elastyczny | React Native + Expo + TypeScript |
| Baza | Rekomendacja | PostgreSQL |
| Lokalne uruchomienie | Rekomendacja | Docker Compose |
| Wdrożenie | Ustalony kierunek | Kontenery i Kubernetes |
| AI | Otwarte | Jeden dostawca przez prosty adapter |

Django proponujemy ze względu na wbudowaną administrację, użytkowników i uprawnienia. Panel redakcyjny nie wymaga osobnego SPA. Jeśli jego ergonomia okaże się niewystarczająca, najpierw dostosowujemy formularze i widoki.

Expo proponujemy dla wspólnego klienta Android/iOS. Współdzielenie kodu z przyszłym webem jest możliwością, nie wymaganiem bieżącego etapu.

Wariant treningu na stronie kampanii opisuje [web/mobile](web-and-mobile.md). Expo Web jest kandydatem do współdzielenia części UI; osobna cienka warstwa React pozostaje alternatywą przy tym samym backendzie. Nie tworzymy teraz nowych klientów.

Wersje zależności i wybór modelu ustalimy przed implementacją na podstawie aktualnej dokumentacji. Nie instalujemy teraz narzędzi i nie zamrażamy numerów wersji.
