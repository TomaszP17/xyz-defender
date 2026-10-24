# Architektura — propozycja

## Ustalone

Python po stronie backendu. Klient mobilny. Panel administratora. Konteneryzacja i możliwość uruchomienia backendu na Kubernetes.

## Rekomendacja

Jedna aplikacja Django z API, panelem administracyjnym i modułami domenowymi, jedna baza PostgreSQL oraz mobilny klient Expo. Model AI jest zewnętrzną zależnością backendu; klucz nigdy nie trafia do klienta.

Przepływ: klient mobilny → API → silnik treningu → adapter AI → walidacja odpowiedzi → klient. Ocena korzysta z decyzji i reguł przypisanych do wersji scenariusza.

Panel administracyjny korzysta z tej samej domeny i bazy. Nie omija walidacji publikacji.

## Podział przyszłego kodu — jeszcze nie tworzyć

- `apps/mobile/` — aplikacja mobilna.
- `services/backend/` — backend i panel.
- `contracts/` — kontrakt API i schematy scenariuszy.
- `deploy/` — kontener i manifesty wdrożeniowe.
- `wiki/` i `agents/` — dokumentacja i instrukcje.

W backendzie moduły: content, training, evaluation, ai i campaigns. Granice mają ułatwiać zadania agentów, nie mnożyć abstrakcje.

Bez kolejki, Redis, mikroserwisów i frameworka wieloagentowego, dopóki nie pojawi się konkretna potrzeba.
