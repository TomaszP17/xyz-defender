# Trening na stronie kampanii i w aplikacji mobilnej

Data: 2026-10-25. Ustalony kierunek: produkt ma być możliwy do zastosowania również na stronie XYZ, w sekcji „Metoda na Podszywacza”. Architektura i harmonogram poniżej są propozycją. Nie mamy dostępu ani zgody na edycję serwisu organizatora.

## Główne zastosowanie web

Użytkownik czyta materiał kampanii i uruchamia trening bezpośrednio w przeglądarce, bez pobierania aplikacji. Wariant działa na telefonie i komputerze. Jest pełnym krótkim ćwiczeniem z rozmową i feedbackiem, a nie wyłącznie linkiem do sklepu z aplikacjami.

Proponowany tekst wejścia w sekcji kampanii: „Przećwicz swoją metodę na Podszywacza” oraz przycisk „Rozpocznij trening”. To projekt komunikacji do uzgodnienia z organizatorem, nie opis istniejącej funkcji jego strony.

Aplikacja mobilna umożliwia te same treningi i może służyć kolejnym podejściom oraz dobrowolnym powtórkom. Wybór priorytetu wdrożenia web wymaga decyzji, ale do szerszej kampanii rekomendujemy dostęp bez instalacji.

## Wspólna architektura

| Element | Wspólne dla kanałów | Odrębne |
| --- | --- | --- |
| Scenariusze i publikacja | Katalog, wersje, pakiety i panel redakcyjny | Sposób wejścia do ćwiczenia |
| Trening | API Python, stany sesji, limity i reguły | Renderowanie UI i obsługa nawigacji |
| AI i ocena | Jeden adapter, ograniczenia i reguły feedbacku | Prezentacja wyniku w danym kliencie |
| Pomiar | Definicje rozpoczęcia, ukończenia i decyzji | Kanał web/mobile i opcjonalny kod materiału |

Jeden backend i jedna baza pozostają aktualną rekomendacją. Web jest dodatkowym klientem tego samego API. Nie tworzymy osobnego silnika AI lub kopii scenariuszy na stronie.

React Native z Expo może wspierać web, ale zakres współdzielenia ekranów trzeba sprawdzić. Na pierwszy wariant wystarczy prosty responsywny widok treningu. Kontrakt API i logika domeny pozostają wspólne również wtedy, gdy warstwa web wymaga osobnego React UI. [Dokumentacja Expo dotycząca web](https://docs.expo.dev/workflow/web/).

## Sposoby udostępnienia

| Wariant | Kiedy ma sens | Co trzeba uzgodnić |
| --- | --- | --- |
| Widok treningu w serwisie organizatora | Docelowy trening w sekcji „Metoda na Podszywacza” | Dostęp do wdrożenia, routing, style i polityka bezpieczeństwa |
| Link do treningu pod zatwierdzonym adresem | Wczesny pilotaż z mniejszą ingerencją w istniejący CMS | Widoczny link w sekcji kampanii, domena, zaufanie i konfiguracja połączeń |
| Osadzenie iframe | Gdy CMS i wymagania UX pozwalają na niezależny moduł | CSP, dozwolone domeny osadzania, wysokość, fokus, klawiatura i zachowanie na telefonie |

Nie przesądzamy obecnej technologii serwisu organizatora. Osadzenie nie jest automatycznie dostępne i wymaga uzgodnień z właścicielem strony. Dla iframe potrzebujemy dozwolonej listy hostów i osobnego dostępu uczestnika bez zależności od cookies zewnętrznego panelu administratora.

## Dostęp i dane

Do ćwiczenia nie jest potrzebna sesja bankowa, konto uczestnika ani dane finansowe. Sesja treningu i jej token są niezależne od logowania redaktora. Token przechowujemy po stronie klienta tylko w zakresie potrzebnym do sesji; nie umieszczamy go w linku kampanii i nie wysyłamy do analityki.

Dostęp API z web wymaga odpowiedniej konfiguracji origin i ochrony przed nadużyciami. CORS nie zastępuje autoryzacji. Panel zachowuje własne logowanie i zabezpieczenia CSRF. Przekierowania oraz dozwolone cele linków kontroluje aplikacja.

Globalny limit kosztu AI obejmuje oba kanały. Publiczne wejście ze strony może zwiększyć liczbę sesji, więc przed kampanią potrzebujemy limitów, czytelnego stanu wyczerpania budżetu i możliwości wyłączenia treningu bez wyłączania materiału edukacyjnego.

## Pomiar

Proponowane metadane sesji: delivery_channel = web/mobile oraz opcjonalny entry_code identyfikujący materiał, nie osobę. Panel porównuje rozpoczęcia, zakończenia i decyzje według kanału oraz wersji. Nie łączymy automatycznie osoby między telefonem i przeglądarką.

Pomiar obejrzenia materiału i kliknięcia wymaga osobnego uzgodnienia z serwisem kampanii. Sam backend sesji nie zna liczby wszystkich odwiedzających stronę. Rozpoczęcie i ukończenie treningu nie dowodzą poprawy bezpieczeństwa w życiu codziennym.

## Zakres i kolejność

W hackathonie zachowujemy jeden scenariusz dla 13–15 lat i ograniczony rdzeń. Decyzja, czy lekki klient web powstanie jeszcze na wydarzeniu czy przed pilotażem, pozostaje otwarta. Zapisanie wariantu web nie jest zleceniem implementacji strony ani publikacji produktu.
