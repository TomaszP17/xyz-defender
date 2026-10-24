# ADR 0001 — ramy projektu

Data: 2026-10-24. Status: zaakceptowana na podstawie instrukcji właściciela.

## Kontekst

Projekt edukacyjny rozwijany na hackathon, z możliwym wykorzystaniem w kampanii XYZ dotyczącej podszywania się.

## Decyzja

- Pierwsi odbiorcy: dzieci i młodzież; dokładny wiek pozostaje otwarty.
- Podstawowy klient: aplikacja mobilna.
- Backend: Python.
- Panel zarządzania scenariuszami stanowi kluczową funkcję.
- Prosta architektura, konteneryzacja i możliwość wdrożenia na Kubernetes.
- Na obecnym etapie wyłącznie pliki Markdown z planem, wizją i instrukcjami agentów.
- Bez automatycznych testów na tym etapie.
- Prywatne repozytorium, nazwa XYZ, kopia lokalna na pulpicie.

## Konsekwencje

Nie tworzymy kodu ani konfiguracji wdrożenia. Konkretne frameworki pozostają rekomendacjami. Dokumentacja ma umożliwiać dalsze uzgadnianie wymagań i późniejszy podział implementacji na małe zadania.
