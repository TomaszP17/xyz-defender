# Konteneryzacja i Kubernetes

## Cel

Backend i panel możliwe do wdrożenia na Kubernetes. Aplikacja mobilna jest budowana i instalowana na telefonie; nie działa w podzie.

## Minimalny plan

- Jeden obraz backendu obejmujący API i panel.
- Deployment i Service backendu, Ingress dla HTTPS.
- ConfigMap dla konfiguracji i Secret dla danych dostępowych.
- Migracje bazy jako osobny Job przed uruchomieniem nowej wersji.
- PostgreSQL z trwałym wolumenem na demonstrację albo zewnętrzna baza.
- Proste sprawdzanie gotowości i działania procesu.

Stan sesji wymagany pomiędzy żądaniami znajduje się w bazie. Nie polegamy na pamięci pojedynczego poda. Nie dodajemy uploadu plików do pierwszej wersji; ewentualny późniejszy upload wymaga trwałego magazynu.

Lokalnie Docker Compose odtwarza backend i bazę. Dostawca klastra, domena, magazyn sekretów i koszty pozostają otwarte. Manifesty i Dockerfile powstaną dopiero po autoryzacji implementacji.
