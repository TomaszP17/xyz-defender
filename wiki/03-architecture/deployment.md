# Konteneryzacja i Kubernetes

Status: projekt infrastruktury demo. Manifesty, Dockerfile i konfiguracja nie powstają na obecnym etapie.

## Co wdrażamy

Jeden obraz backendu obejmuje API, panel i pliki statyczne panelu. Aplikacja mobilna jest osobnym buildem instalowanym na telefonie; nie uruchamiamy jej w podzie. Pierwsza rekomendacja: jedna replika backendu, bez HA i autoskalowania.

| Element | Rola |
| --- | --- |
| Deployment backendu | Proces aplikacji bez stanu zapisywanego na dysku kontenera |
| Service | Wewnętrzny dostęp do backendu |
| Ingress z HTTPS | API i panel, np. /api oraz /admin; wymaga dostępnego kontrolera w klastrze |
| ConfigMap / Secret | Konfiguracja oraz dane dostępowe poza obrazem i repozytorium |
| Job migracji | Jednorazowe migracje bazy przed uruchomieniem nowej wersji |
| PostgreSQL | Preferencyjnie istniejąca baza; alternatywnie jedna instancja w StatefulSet z PVC i właściwymi Service |
| CronJob porządkowania | Usuwanie wygasłych danych zgodnie z zatwierdzoną retencją, bez Celery |

Przy bazie w klastrze wymagany jest dostępny StorageClass i trwały wolumen. Demo nie obejmuje replikacji PostgreSQL, operatora bazy ani planu odtwarzania po katastrofie. Zmiana poda nie może usuwać wolumenu.

Deployment pasuje do wymienialnych instancji backendu, a StatefulSet jest opcją dla stanu wymagającego trwałego magazynu. [Dokumentacja workloadów Kubernetes](https://kubernetes.io/docs/concepts/workloads/controllers/) i [StatefulSet](https://kubernetes.io/docs/concepts/workloads/controllers/statefulset/).

## Zdrowie i restart

Liveness sprawdza proces; readiness gotowość obsługi API i dostęp do bazy. Żaden z nich nie wywołuje płatnego modelu. Awaria AI nie powinna wywoływać restartów. Stan sesji i operacji znajduje się w bazie, co umożliwia rozpoznanie przerwanej tury po restarcie.

Timeout ingressu musi przekraczać limit API; roboczo 30 s wobec limitu modelu 15 s i limitu oczekiwania klienta 20 s. Liczba workerów oraz CPU/RAM zostaną dobrane podczas demonstracji. Nie deklarujemy jeszcze wydajności klastra.

## Lokalnie

Docker Compose uruchamia backend i PostgreSQL. Mobilny klient łączy się z adresem osiągalnym z telefonu, nie z localhost komputera. Czyszczenie danych lokalnych musi być opisane i uruchamiane oddzielnie od zwykłego startu.

## Otwarte

Klaster, domena i certyfikat, rejestr obrazów, baza, przechowywanie sekretów i akceptacja okresów retencji. Ich wybór nie wymaga zmiany granic modułów.
