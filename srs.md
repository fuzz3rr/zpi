# Specyfikacja Wymagań Oprogramowania (SRS)

## System HRflow - Zarządzanie Cyklem Życia Pracownika

**Zespół projektowy:** Adrian Jabłoński, Paweł Gorgolewski, Kamil Pierzchała, Łukasz Bartoszek,  Bartosz Balawender

---

## 1. Wstęp

### 1.1. Cel dokumentu

Ten dokument opisuje wymagania dla systemu **HRflow** w wersji 1.0 - kompleksowej platformy do zarządzania cyklem życia pracownika, od rekrutacji przez rozwój aż po offboarding.

**Dla kogo jest ten dokument:**

- Zespół deweloperski - jako podstawa do implementacji
- Product Owner - do weryfikacji zgodności z wizją produktu
- Testerzy - jako źródło scenariuszy testowych
- Interesariusze biznesowi - do akceptacji zakresu projektu

**Jak używać tego dokumentu:**

- Rozdział 4 (Wymagania Funkcjonalne) zawiera szczegółowe kryteria akceptacji w formacie Given-When-Then - to główne źródło dla deweloperów i testerów
- Rozdział 5 (Atrybuty Jakościowe) definiuje mierzalne wymagania niefunkcjonalne
- Dodatki zawierają materiały pomocnicze (persony, diagramy)

### 1.2. Wizja, Zakres i Cele Produktu

#### Wizja

> *"HRflow to inteligentna platforma HR, która automatyzuje żmudne procesy kadrowe i pozwala firmom skupić się na tym, co naprawdę ważne - ludziach. Łączymy rekrutację, onboarding, rozwój i zarządzanie talentami w jeden spójny ekosystem, który oszczędza czas i pomaga budować lepsze zespoły."*

#### Zakres systemu

System HRflow obejmuje następujące obszary:

**Moduł Rekrutacji:**

- Automatyczny screening CV z parsowaniem dokumentów
- Semantyczne dopasowanie kandydatów do ofert (Semantic Matching Engine)
- Giełda Talentów - rekrutacja wewnętrzna
- Portal Kandydata z real-time tracking statusu
- System poleceń pracowniczych (Employee Referral Engine)
- Anonimizacja danych w procesie selekcji (Diversity & Inclusion)
- Automatyczna publikacja ofert w social media

**Moduł Onboardingu:**

- Cyfrowy obieg dokumentów z e-podpisem
- Automatyczne generowanie umów
- Zgrywalizowany moduł wdrożeniowy
- Integracja z repozytoriami kodu i dokumentacją techniczną

**Moduł Rozwoju i Szkoleń:**

- Platforma LMS ze spersonalizowanymi ścieżkami rozwoju
- System OKR (Objectives and Key Results)
- Continuous Feedback (opinie peer-to-peer)
- System oceny potencjału (9-box grid)
- Kafeteryjna platforma benefitowa

**Moduł Analityki HR:**

- Predykcja rotacji pracowników (Retention AI)
- Dashboardy i raportowanie
- Ankiety pulsujące

**Moduł Offboardingu:**

- Automatyczne odbieranie dostępów (integracja z SAML)
- Program Alumni dla byłych pracowników

#### Cele biznesowe i KPI

| Cel                        | Metryka (KPI)                              | Wartość docelowa             | Horyzont czasowy |
|----------------------------|--------------------------------------------|------------------------------|------------------|
| Automatyzacja rekrutacji   | Time-to-Hire                               | Skrócenie z 45 do 20 dni     | 6 miesięcy       |
| Trafność dopasowania       | Interview Acceptance Rate                  | Wzrost z 10% do 15%          | 6 miesięcy       |
| Rekrutacja wewnętrzna      | % wakatów wypełnionych wewnętrznie         | 40%                          | 9 miesięcy       |
| Różnorodność               | Wzrost różnorodności kandydatów            | +30%                         | 6 miesięcy       |
| Candidate Experience       | Candidate NPS (cNPS)                       | +50                          | 6 miesięcy       |
| Szybkość wdrożenia         | Time-to-Productivity (programiści)         | Skrócenie z 3 mies. do 6 tyg.| 12 miesięcy      |
| Paperless HR               | Redukcja czasu na dokumentację             | -80%                         | 3 miesiące       |
| Upskilling                 | % przeszkolonej kadry technicznej          | 60%                          | 12 miesięcy      |
| Sukcesja                   | % kluczowych stanowisk z następcą          | 90%                          | 6 miesięcy       |
| Employer Branding          | Zasięg w social media                      | +50%                         | 6 miesięcy       |
| Continuous Feedback        | Średnia opinii peer-to-peer/pracownik      | 4/miesiąc                    | 6 miesięcy       |
| Transparentność celów      | Pokrycie OKR                               | 100%                         | 3 miesiące       |
| Retencja                   | Redukcja rotacji kluczowych specjalistów   | -15%                         | 12 miesięcy      |
| Wykorzystanie benefitów    | Utylizacja budżetu szkoleniowo-benefitowego| 95% (z 60%)                  | 12 miesięcy      |
| Bezpieczeństwo offboardingu| Automatyczne odbieranie dostępów           | 100%                         | od wdrożenia     |
| Program poleceń            | Udział zatrudnień z poleceń                | Wzrost z 8% do 25%           | 9 miesięcy       |

#### Poza zakresem

System HRflow **NIE BĘDZIE** obejmował:

- Pełnej obsługi płacowej (payroll) - integracja z zewnętrznymi systemami
- Zarządzania czasem pracy i grafikami (RCP)
- Obsługi podróży służbowych
- Systemu helpdesk IT
- Zarządzania flotą samochodową
- Obsługi BHP (szkolenia BHP będą w LMS, ale pełna dokumentacja BHP nie)

### 1.3. Definicje, Akronimy i Skróty

| Termin                       | Definicja                                                                    |
|------------------------------|------------------------------------------------------------------------------|
| **Time-to-Hire**             | Czas od publikacji oferty do podpisania umowy z kandydatem                   |
| **Time-to-Productivity**     | Czas od zatrudnienia do osiągnięcia pełnej produktywności                    |
| **cNPS**                     | Candidate Net Promoter Score - wskaźnik satysfakcji kandydatów               |
| **Semantic Matching Engine** | Silnik dopasowania oparty na analizie semantycznej kompetencji               |
| **9-box grid**               | Macierz oceny pracowników (potencjał vs. wydajność)                          |
| **OKR**                      | Objectives and Key Results - metodyka zarządzania przez cele                 |
| **LMS**                      | Learning Management System - platforma e-learningowa                         |
| **SAML**                     | Security Assertion Markup Language                                           |
| **Giełda Talentów**          | Internal Talent Marketplace - system dopasowania pracowników do wakatów      |
| **Retention AI**             | Moduł predykcji ryzyka odejścia pracownika                                   |
| **Employee Referral Engine** | System poleceń pracowniczych                                                 |
| **Kafeteria benefitowa**     | Elastyczny system wymiany punktów na benefity                                |
| **Ankiety pulsujące**        | Krótkie, regularne ankiety badające nastroje pracowników                     |
| **Alumni**                   | Program utrzymywania kontaktu z byłymi pracownikami                          |
| **MVP**                      | Minimum Viable Product - minimalna wersja produktu                           |
| **RODO/GDPR**                | Rozporządzenie o ochronie danych osobowych                                   |

### 1.4. Przegląd dokumentu

| Rozdział                     | Zawartość                                                           |
|------------------------------|---------------------------------------------------------------------|
| **2. Opis Ogólny**           | Główne funkcje systemu, klasy użytkowników, ograniczenia i założenia|
| **3. Interfejsy Zewnętrzne** | Makiety UI, opis integracji z zewnętrznymi systemami                |
| **4. Wymagania Funkcjonalne**| Szczegółowe user stories z kryteriami akceptacji (Given-When-Then)  |
| **5. Atrybuty Jakościowe**   | Wymagania niefunkcjonalne (wydajność, bezpieczeństwo, skalowalność) |
| **6. Analiza Wymagań**       | Analiza porównawcza konkurencji                                     |
| **Dodatki**                  | Diagram przypadków użycia, persony, kwestie do rozwiązania          |

---

## 2. Opis Ogólny

### 2.1. Główne Funkcje Produktu

System HRflow składa się z pięciu głównych modułów:

```
┌───────────────────────────────────────────────────────────────────────┐
│                               HRflow                                  │
├──────────────┬──────────────┬──────────────┬────────────┬─────────────┤
│  REKRUTACJA  │  ONBOARDING  │    ROZWÓJ    │  ANALITYKA │ OFFBOARDING │
├──────────────┼──────────────┼──────────────┼────────────┼─────────────┤
│• ATS         │• Dokumenty   │• LMS         │• Retention │• Odbieranie │
│• Screening   │• E-podpis    │• OKR         │  AI        │  dostępów   │
│• Matching    │• Gamifikacja │• Feedback    │• Dashboardy│• Alumni     │
│• Portal      │• Integracje  │• 9-box       │• Ankiety   │             │
│  Kandydata   │  dewelop.    │• Kafeteria   │            │             │
│• Polecenia   │              │              │            │             │
│• Social      │              │              │            │             │
│  Media       │              │              │            │             │
└──────────────┴──────────────┴──────────────┴────────────┴─────────────┘
```

#### Moduł Rekrutacji

| Funkcja                             | Opis                                                                            |
|-------------------------------------|---------------------------------------------------------------------------------|
| **ATS (Applicant Tracking System)** | Zarządzanie procesem rekrutacyjnym, publikacja ofert, śledzenie kandydatów      |
| **Automatyczny Screening CV**       | Parsowanie CV, ekstrakcja kompetencji, wstępna kwalifikacja                     |
| **Semantic Matching Engine**        | Inteligentne dopasowanie kandydatów do ofert z rozpoznawaniem hierarchii komp.  |
| **Portal Kandydata**                | Interfejs dla kandydatów z real-time tracking statusu aplikacji                 |
| **Giełda Talentów**                 | Dopasowanie obecnych pracowników do wewnętrznych wakatów                        |
| **Employee Referral Engine**        | System poleceń z gamifikacją i automatycznym naliczaniem nagród                 |
| **Anonimizacja D&I**                | Maskowanie danych wrażliwych w procesie selekcji                                |
| **Auto-publikacja Social Media**    | Automatyczne publikowanie ofert na LinkedIn, Facebook, Instagram                |
| **Integracja z kalendarzami**       | Automatyczne umawianie spotkań rekrutacyjnych                                   |

#### Moduł Onboardingu

| Funkcja                      | Opis                                                 |
|------------------------------|------------------------------------------------------|
| **Cyfrowy obieg dokumentów** | Elektroniczne formularze, workflow zatwierdzeń       |
| **E-podpis**                 | Podpisywanie umów i dokumentów elektronicznie        |
| **Generator umów**           | Automatyczne generowanie umów na podstawie szablonów |
| **Moduł wdrożeniowy**        | Zgrywalizowany onboarding z śledzeniem postępów      |
| **Integracje deweloperskie** | Połączenie z repozytoriami kodu, Confluence, Jira    |

#### Moduł Rozwoju i Szkoleń

| Funkcja                | Opis                                            |
|------------------------|-------------------------------------------------|
| **LMS**                | Platforma e-learningowa ze ścieżkami rozwoju    |
| **System OKR**         | Kaskadowanie celów, powiązanie z strategią firmy|
| **Continuous Feedback**| Ciągła wymiana opinii peer-to-peer              |
| **9-box grid**         | Ocena potencjału i planowanie sukcesji          |
| **Kafeteria benefitowa**| Elastyczna wymiana punktów na benefity         |

#### Moduł Analityki HR

| Funkcja               | Opis                                      |
|-----------------------|-------------------------------------------|
| **Retention AI**      | Predykcja ryzyka odejścia pracowników     |
| **Dashboardy**        | Wizualizacja kluczowych metryk HR         |
| **Ankiety pulsujące** | Regularne badanie nastrojów pracowników   |
| **Raportowanie**      | Generowanie raportów dla zarządu          |

#### Moduł Offboardingu

| Funkcja                   | Opis                                            |
|---------------------------|-------------------------------------------------|
| **Zarządzanie dostępami** | Automatyczne odbieranie dostępów przez SAML     |
| **Program Alumni**        | Portal dla byłych pracowników, networking       |

### 2.2. Klasy Użytkowników

System rozróżnia następujące role użytkowników:

#### Użytkownicy zewnętrzni

| Rola           | Opis                              | Dostęp do modułów  |
|----------------|-----------------------------------|--------------------|
| **Kandydat**   | Osoba aplikująca na stanowisko    | Portal Kandydata   |
| **Alumni**     | Były pracownik w programie Alumni | Moduł Alumni       |

#### Użytkownicy wewnętrzni

| Rola                    | Opis                                   | Dostęp do modułów                                            |
|-------------------------|----------------------------------------|--------------------------------------------------------------|
| **Rekruter**            | Prowadzi procesy rekrutacyjne          | Rekrutacja (pełny), Analityka (częściowy)                    |
| **HR Manager**          | Zarządza działem HR, definiuje procesy | Wszystkie moduły                                             |
| **HR Admin**            | Obsługa dokumentacji kadrowej          | Onboarding, Offboarding, Dokumenty                           |
| **Pracownik**           | Standardowy użytkownik systemu         | Rozwój, Feedback, Kafeteria, OKR                             |
| **Menedżer**            | Kierownik zespołu                      | Rekrutacja (hiring manager), Rozwój, Feedback, OKR, Analityka|
| **Trener wewnętrzny**   | Tworzy i prowadzi szkolenia            | LMS (tworzenie treści)                                       |
| **Administrator IT**    | Zarządza integracjami i konfiguracją   | Panel administracyjny, integracje                            |
| **Zarząd**              | Dostęp do strategicznych raportów      | Analityka, Dashboardy                                        |

#### Skrócone persony (pełne w Dodatku B)

**Anna - Rekruterka (28 lat)**
> *"Każdego dnia przeglądam setki CV. Potrzebuję narzędzia, które odsieje tych, którzy kompletnie nie pasują, ale nie przegapi diamentów ukrytych w niestandardowych CV."*

Anna pracuje w firmie IT od 2 lat. Prowadzi jednocześnie 8-12 procesów rekrutacyjnych. Jej główny ból to czas poświęcany na wstępną selekcję CV i koordynację terminów rozmów.

**Marek - Nowy programista (25 lat)**
> *"Pierwszy tydzień w nowej pracy to chaos. Loginy, hasła, dokumenty, spotkania... Chciałbym mieć jedno miejsce, gdzie wszystko jest ogarnięte."*

Marek właśnie dołączył do zespołu backend. Potrzebuje szybko wdrożyć się w projekt i poznać procesy firmy. Lubi gamifikację i jasne cele.

**Katarzyna - HR Manager (42 lata)**
> *"Zarząd pyta mnie o rotację, koszty rekrutacji, development pipeline... Zbieranie tych danych z Exceli to koszmar."*

Katarzyna zarządza 5-osobowym zespołem HR w firmie produkcyjnej (400 pracowników). Potrzebuje narzędzi analitycznych i automatyzacji procesów.

**Tomek - Menedżer zespołu (35 lat)**
> *"Chcę wiedzieć, kto w moim zespole ma potencjał na lidera, a kto może odejść. I chcę to wiedzieć zanim będzie za późno."*

Tomek zarządza 12-osobowym zespołem sprzedaży. Potrzebuje prostych narzędzi do oceny i rozwoju ludzi.

### 2.3. Ograniczenia Projektowe i Implementacyjne

#### Ograniczenia technologiczne

| Kategoria                | Ograniczenie                                                                        | Uzasadnienie i Wpływ na Architekturę                                                                                                                                                                                                                                                                               |
|--------------------------|-------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Architektura Backend** | Architektura oparta na API (REST lub GraphQL) z obsługą asynchroniczności           | **Dlaczego:** System musi obsługiwać wiele operacji w tle (np. parsowanie CV, powiadomienia) bez blokowania interfejsu.<br>**Wpływ:** Wymusza odseparowanie warstwy prezentacji od logiki biznesowej, konieczność zarządzania kontraktami API (np. OpenAPI/Swagger) oraz wdrożenie mechanizmów *non-blocking I/O*. |
| **Technologia Backend**  | Język programowania wysokiego poziomu z dojrzałym ekosystemem bibliotek ML/AI       | **Dlaczego:** Kluczowe funkcje (Matching, Retention) wymagają algorytmów analitycznych.<br>**Wpływ:** Eliminuje konieczność tworzenia "mikroserwisów w innym języku" tylko dla AI. Architektura monolityczna lub modularna w jednej technologii upraszcza stack.                                                   |
| **Frontend**             | Nowoczesny framework typu SPA (Single Page Application)                             | **Dlaczego:** Wymagany interfejs zbliżony do aplikacji desktopowej (płynność, brak przeładowań).<br>**Wpływ:** Przeniesienie logiki renderowania na klienta, konieczność zabezpieczenia API (JWT/OAuth) i obsługi stanu aplikacji (State Management) po stronie przeglądarki.                                      |
| **Baza danych**          | Relacyjna baza danych (RDBMS) ze wsparciem dla danych pół-ustrukturyzowanych (JSON) | **Dlaczego:** CV mają nieregularną strukturę, ale procesy kadrowe wymagają ścisłych relacji i transakcyjności.<br>**Wpływ:** Hybrydowy model danych (kolumny SQL + pola JSONB), co pozwala uniknąć skomplikowanych migracji przy zmianie struktury CV, zachowując spójność ACID.                                   |
| **Cache/Queue**          | System in-memory data store oraz broker wiadomości                                  | **Dlaczego:** Operacje takie jak generowanie raportów czy wysyłka maili nie mogą być synchroniczne.<br>**Wpływ:** Wprowadzenie architektury producent-konsument (Worker Pattern). Zadania trafiają do kolejki, a interfejs zwraca "202 Accepted" zamiast czekać na wynik.                                          |
| **Wyszukiwanie**         | Dedykowany silnik wyszukiwania pełnotekstowego (Full-text search)                   | **Dlaczego:** Standardowe zapytania SQL `LIKE` są niewydajne i nie obsługują synonimów/fleksji językowej.<br>**Wpływ:** Konieczność synchronizacji danych między główną bazą (SQL) a silnikiem wyszukiwania (indeksowanie zdarzeniowe lub cykliczne).                                                              |
| **Infrastruktura**       | Konteneryzacja zgodna ze standardem OCI (Open Container Initiative)                 | **Dlaczego:** Zespół deweloperski pracuje na różnych systemach operacyjnych.<br>**Wpływ:** Całe środowisko (kod, baza, cache) musi być definiowalne jako kod (IaC), co eliminuje problem "u mnie działa" i przyspiesza onboarding nowych programistów.                                                             |
| **Zasoby obliczeniowe**  | Architektura zoptymalizowana pod standardowe instancje chmurowe (CPU-based)         | **Dlaczego:** Budżet nie pozwala na drogie instancje GPU.<br>**Wpływ:** Modele ML muszą być "lekkie" (kwantyzacja, proste regresje) i zoptymalizowane do wnioskowania (inference) na procesorach CPU.                                                                                                              |

#### Ograniczenia organizacyjne

| Kategoria        | Ograniczenie                                       | Uzasadnienie i Wpływ na Realizację                                                                                                                                                                                                                    |
|------------------|----------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Zespół**       | 5-7 deweloperów                                    | **Dlaczego:** Ograniczone zasoby ludzkie (projekt akademicki).<br>**Wpływ:** Konieczność unikania nadmiernego skomplikowania (Overengineering). Preferowany Modular Monolith zamiast Mikroserwisów, aby uniknąć narzutu komunikacyjnego i DevOps.     |
| **Czas**         | MVP w 4 miesiące                                   | **Dlaczego:** Sztywny termin administracyjny.<br>**Wpływ:** Rygorystyczna priorytetyzacja (MoSCoW). Funkcje "Nice-to-have" (np. wideorozmowy) są wycinane lub zastępowane integracjami. Dług technologiczny jest akceptowalny, jeśli przyspiesza MVP. |
| **Budżet**       | Minimalizacja kosztów operacyjnych (OpEx)          | **Dlaczego:** Brak finansowania zewnętrznego.<br>**Wpływ:** Wykluczenie płatnych usług SaaS (np. Auth0, płatne API map). System musi być samowystarczalny (Self-hosted) i korzystać z rozwiązań Open Source.                                          |
| **Metodyka**     | Praca w iteracjach (Agile/Scrum)                   | **Dlaczego:** Wymóg elastyczności i częstej weryfikacji postępów.<br>**Wpływ:** Architektura musi wspierać częste wdrożenia (CI/CD). Kod musi być testowalny automatycznie, aby uniknąć regresji przy szybkich zmianach.                              |
| **Dokumentacja** | SRS oraz dokumentacja techniczna jako "Code-Close" | **Dlaczego:** Wymóg łatwego przekazania projektu.<br>**Wpływ:** Dokumentacja API (np. Swagger) generowana automatycznie z kodu. Diagramy architektury jako kod (np. Mermaid.js) w repozytorium.                                                       |
| **Jakość kodu**  | Obowiązkowe Code Review i procesy CI/CD            | **Dlaczego:** Zespół ma różny poziom doświadczenia.<br>**Wpływ:** Wymuszenie reguł "Branch protection". Pipeline CI blokuje merge, jeśli testy nie przechodzą lub linter wykrywa błędy, co spowalnia proces, ale zwiększa stabilność.                 |

#### Ograniczenia prawne i środowiskowe

| Kategoria                  | Ograniczenie                                  | Uzasadnienie i Wpływ na Architekturę                                                                                                                                                                                                                     |
|----------------------------|-----------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **RODO (GDPR)**            | Pełna zgodność (Privacy by Design & Default)  | **Dlaczego:** Wysokie ryzyko prawne przy przetwarzaniu danych osobowych.<br>**Wpływ:** Implementacja "Soft Delete" (ukrywanie zamiast usuwania) dla audytowalności, szyfrowanie kolumn wrażliwych w bazie, obowiązkowe logi dostępu do danych osobowych. |
| **Retencja danych**        | Mechanizmy automatycznego cyklu życia danych  | **Dlaczego:** Dane kandydatów nie mogą być trzymane w nieskończoność.<br>**Wpływ:** Wdrożenie procesów w tle (Cron Jobs), które cyklicznie anonimizują lub usuwają stare rekordy zgodnie z polityką firmy.                                               |
| **Prawo dostępu**          | Interfejsy eksportu danych (Data Portability) | **Dlaczego:** Prawo użytkownika do przenoszenia danych.<br>**Wpływ:** Konieczność stworzenia endpointów API agregujących dane z różnych modułów do jednego pliku JSON/XML.                                                                               |
| **Regulacje HR**           | Zgodność z lokalnym prawem pracy              | **Dlaczego:** System musi być legalny w użyciu.<br>**Wpływ:** Sztywna walidacja reguł biznesowych (np. minimalne okresy wypowiedzenia) zaszyta w logice backendu, której nie można obejść przez UI.                                                      |
| **Podpis elektroniczny**   | Zgodność ze standardami (np. eIDAS)           | **Dlaczego:** Umowy muszą mieć moc prawną.<br>**Wpływ:** System nie implementuje kryptografii podpisu samodzielnie, lecz działa jako pośrednik (Proxy) do certyfikowanego dostawcy usług zaufania.                                                       |
| **Dostępność (A11y)**      | Zgodność z wytycznymi WCAG 2.1 (poziom AA)    | **Dlaczego:** Zapobieganie wykluczeniu cyfrowemu.<br>**Wpływ:** Frontend musi obsługiwać nawigację klawiaturą, czytniki ekranowe (ARIA labels) i odpowiedni kontrast. Testy automatyczne UI (np. Lighthouse) w pipeline CI.                              |
| **Własność intelektualna** | Czystość licencyjna                           | **Dlaczego:** Unikanie roszczeń prawnych.<br>**Wpływ:** Automatyczne skanowanie zależności (SCA) w poszukiwaniu bibliotek z licencjami wirusowymi (np. GPL) w procesie budowania aplikacji.                                                              |

### 2.4. Założenia Projektowe

#### Założenia biznesowe

| ID        | Założenie                                                  | Uzasadnienie i Wpływ na Architekturę                                                                                                                                                                                                           |
|-----------|------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **ZB-01** | Organizacja docelowa to MŚP (100-1000 pracowników)         | **Dlaczego:** Skala definiuje wymagania niefunkcjonalne.<br>**Wpływ:** Skalowalność wertykalna (dołożenie RAM/CPU) jest wystarczająca na start. Brak konieczności implementacji skomplikowanego shardingu bazy danych czy Kubernetes na start. |
| **ZB-02** | W organizacji istnieje rola lub dział odpowiedzialny za HR | **Dlaczego:** System potrzebuje "super-użytkownika".<br>**Wpływ:** Konieczność budowy zaawansowanego panelu administracyjnego z szerokimi uprawnieniami, oddzielonego od widoku pracownika.                                                    |
| **ZB-03** | Organizacja prowadzi ciągłe procesy rekrutacyjne           | **Dlaczego:** Uzasadnia inwestycję w moduł ATS.<br>**Wpływ:** Moduł rekrutacji jest traktowany jako "Core Domain" w architekturze, z największym priorytetem wydajnościowym i dostępnością.                                                    |
| **ZB-04** | Pracownicy posiadają dostęp do infrastruktury cyfrowej     | **Dlaczego:** System ma być dostępny dla wszystkich.<br>**Wpływ:** Interfejs musi być responsywny (RWD/Mobile First), aby umożliwić dostęp z telefonów prywatnych lub służbowych bez dedykowanej aplikacji natywnej.                           |
| **ZB-05** | Organizacja posiada centralny system tożsamości            | **Dlaczego:** Bezpieczeństwo i wygoda logowania.<br>**Wpływ:** Architektura autoryzacji oparta na standardach federacyjnych (SAML/OIDC). System nie przechowuje haseł pracowników, polega na tokenach z IdP.                                   |

#### Założenia techniczne

| ID        | Założenie                                                  | Uzasadnienie i Wpływ na Architekturę                                                                                                                                                                                                       |
|-----------|------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **ZT-01** | Użytkownicy końcowi korzystają z nowoczesnych przeglądarek | **Dlaczego:** Koszt wspierania starych technologii (IE11) jest zbyt wysoki.<br>**Wpływ:** Możliwość użycia nowoczesnych API przeglądarkowych (Grid Layout, WebSockets, LocalStorage) bez tworzenia skomplikowanych obejść (polyfills).     |
| **ZT-02** | Dostępne stabilne łącze internetowe                        | **Dlaczego:** Aplikacje SPA wymagają pobrania kodu startowego.<br>**Wpływ:** Brak konieczności pełnego trybu "Offline-first". Implementacja mechanizmów "Retry" przy przesyłaniu dużych plików CV w przypadku chwilowej utraty połączenia. |
| **ZT-03** | Dokumenty wejściowe (CV) są w formatach parsowalnych       | **Dlaczego:** Tekst jest łatwiejszy do analizy niż obraz.<br>**Wpływ:** Moduł parsowania opiera się na ekstrakcji tekstu i metadanych. Brak konieczności wdrażania ciężkich i drogich rozwiązań OCR (Computer Vision) w MVP.               |
| **ZT-04** | Infrastruktura klienta umożliwia federację tożsamości      | **Dlaczego:** Centralizacja zarządzania dostępem.<br>**Wpływ:** System musi implementować wzorzec "Service Provider" dla protokołów SAML/OAuth, delegując uwierzytelnianie na zewnątrz.                                                    |
| **ZT-05** | Dostępność zasobów do uruchomienia silnika wyszukiwania    | **Dlaczego:** Wyszukiwanie semantyczne wymaga pamięci RAM.<br>**Wpływ:** Architektura musi przewidywać osobny kontener/usługę dla silnika wyszukiwania (np. Elasticsearch), co zwiększa minimalne wymagania sprzętowe hostingu.            |

#### Założenia dotyczące użytkowników

| ID        | Założenie                                                      | Uzasadnienie i Wpływ na Architekturę                                                                                                                                                                                                      |
|-----------|----------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **ZU-01** | Użytkownicy administracyjni (HR) posiadają kompetencje cyfrowe | **Dlaczego:** Pozwala uniknąć nadmiernego upraszczania profesjonalnych narzędzi.<br>**Wpływ:** Interfejs dla HR może być gęsty w informacje (dashboardy, tabele), priorytetyzując efektywność pracy nad prostotą (Power User UX).         |
| **ZU-02** | Kandydaci akceptują w pełni cyfrową ścieżkę aplikacji          | **Dlaczego:** Minimalizacja papierologii.<br>**Wpływ:** Skrajny minimalizm formularzy aplikacyjnych (UX) i walidacja w czasie rzeczywistym, aby zminimalizować współczynnik porzuceń (Drop-off rate).                                     |
| **ZU-03** | Pracownicy są kulturowo gotowi na system feedbacku             | **Dlaczego:** System potrzebuje danych wejściowych od ludzi.<br>**Wpływ:** Implementacja mechanizmów "Nudge" (przypomnień) i grywalizacji, aby technicznie stymulować aktywność użytkowników.                                             |
| **ZU-04** | Kadra menedżerska będzie aktualizować statusy w systemie       | **Dlaczego:** Raporty są bezużyteczne bez aktualnych danych.<br>**Wpływ:** Integracja z kanałami codziennej pracy (e-mail, komunikatory), aby umożliwić akcje (np. akceptacja urlopu) bez konieczności logowania się do głównego systemu. |

#### Zależności zewnętrzne

| ID        | Zależność                                   | Alternatywa (Plan B)                       | Uzasadnienie i Wpływ na Architekturę                                                                                                                                                 |
|-----------|---------------------------------------------|--------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **ZZ-01** | Publiczne API platform społecznościowych    | Ręczna publikacja i kopiowanie linków      | **Wpływ:** Warstwa abstrakcji dla "Job Boardów". Jeśli API LinkedIn zablokuje dostęp, system przełącza się na generowanie sformatowanego tekstu do ręcznego wklejenia.               |
| **ZZ-02** | Zewnętrzny dostawca podpisu elektronicznego | Proces hybrydowy (drukuj-podpisz-skanuj)   | **Wpływ:** Architektura sterowana zdarzeniami (Webhooks). System nasłuchuje na statusy dokumentów ("Podpisano", "Odrzucono") z zewnętrznej platformy, zamiast przetwarzać je samemu. |
| **ZZ-03** | Usługa wysyłki wiadomości transakcyjnych    | Własny serwer pocztowy (trudne utrzymanie) | **Wpływ:** Rozdzielenie generowania treści maila (templating) od samej wysyłki. Możliwość łatwej podmiany providera (np. z SendGrid na AWS SES) w konfiguracji.                      |
| **ZZ-04** | Korporacyjny Dostawca Tożsamości (IdP)      | Lokalne uwierzytelnianie w bazie danych    | **Wpływ:** Podwójna strategia logowania. System musi obsługiwać zarówno logowanie przez SSO (dla pracowników), jak i lokalne hasła (dla kandydatów/alumni).                          |
| **ZZ-05** | System kalendarzowy (Google/Outlook)        | Manualne uzgadnianie terminów              | **Wpływ:** Złożona logika synchronizacji dwukierunkowej i obsługi stref czasowych. Konieczność przechowywania tokenów dostępowych (Refresh Tokens) per użytkownik.                   |

---

## 3. Wymagania Dotyczące Interfejsów Zewnętrznych

### 3.1. Interfejsy Użytkownika (UI)

#### Ogólne wytyczne projektowe

**Styl wizualny:**

- Design system oparty na Material Design 3
- Kolorystyka: niebieski (#1976D2) jako primary, szary (#424242) jako secondary
- Typografia: Inter dla UI, system fonts jako fallback
- Responsywność: Mobile-first, breakpoints: 320px, 768px, 1024px, 1440px

**Zasady UX:**

- Maksymalnie 3 kliknięcia do najważniejszych akcji
- Jasne komunikaty błędów z sugestią rozwiązania
- Skeleton loaders zamiast spinnerów
- Wsparcie dla dark mode
- Dostępność WCAG 2.1 AA

#### Makiety głównego przypadku użycia: Aplikowanie na ofertę

### Ekran 1: Lista ofert pracy (widok kandydata)

```text
┌─────────────────────────────────────────────────────────────────┐
│  (o) [Szukaj stanowiska...]        @ Lokalizacja v   # Filtruj  │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  ┌───────────────────────────────────────────────────────────┐  │
│  │ (H) Senior Python Developer                 @ Warszawa    │  │
│  │     TechCorp Sp. z o.o.                     $ 18-24k PLN  │  │
│  │     Python * FastAPI * PostgreSQL           D do 15.01    │  │
│  │     [Zobacz szczegóły]                      [* Zapisz]    │  │
│  └───────────────────────────────────────────────────────────┘  │
│                                                                 │
│  ┌───────────────────────────────────────────────────────────┐  │
│  │ (H) HR Business Partner                     @ Krakow      │  │
│  │     BigFactory S.A.                         $ 12-15k PLN  │  │
│  │     HR * Rekrutacja * HRIS                  D do 20.01    │  │
│  │     [Zobacz szczegóły]                      [* Zapisz]    │  │
│  └───────────────────────────────────────────────────────────┘  │
│                                                                 │
│  ┌───────────────────────────────────────────────────────────┐  │
│  │ (H) Junior Frontend Developer               @ Remote      │  │
│  │     StartupXYZ                              $ 8-12k PLN   │  │
│  │     React * TypeScript * CSS                D do 10.01    │  │
│  │     [Zobacz szczegóły]                      [* Zapisz]    │  │
│  └───────────────────────────────────────────────────────────┘  │
│                                                                 │
│  [Pokaż więcej ofert...]                                        │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

### Ekran 2: Szczegóły oferty

```text
┌─────────────────────────────────────────────────────────────────┐
│  < Wróć do listy                                                │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  (H) Senior Python Developer                                    │
│  =======================================                        │
│                                                                 │
│  TechCorp Sp. z o.o.    @ Warszawa (hybrydowo)                  │
│  $ 18 000 - 24 000 PLN netto (B2B)                              │
│  D Rekrutacja do: 15 stycznia 2025                              │
│                                                                 │
│  ┌───────────────────────────────────────────────────────────┐  │
│  │ Dopasowanie do Twojego profilu: [XXXXXXXXXXXX--] 78%      │  │
│  │ (v) Python (Twój poziom: Expert)                          │  │
│  │ (v) FastAPI (Twój poziom: Mid)                            │  │
│  │ (!) Kubernetes (brak w profilu)                           │  │
│  └───────────────────────────────────────────────────────────┘  │
│                                                                 │
│  (#) OPIS STANOWISKA                                            │
│  Szukamy doświadczonego Python Developera do zespołu            │
│  platformy płatniczej. Będziesz pracować nad...                 │
│  [Pokaż więcej...]                                              │
│                                                                 │
│  (^) WYMAGANIA                                                  │
│  * 5+ lat doświadczenia z Python                                │
│  * Znajomość FastAPI lub Django                                 │
│  * Doświadczenie z PostgreSQL                                   │
│  * Mile widziane: Kubernetes, AWS                               │
│                                                                 │
│  (+) OFERUJEMY                                                  │
│  * Praca hybrydowa (2 dni w biurze)                             │
│  * Budżet szkoleniowy 5000 PLN/rok                              │
│  * Prywatna opieka medyczna                                     │
│                                                                 │
│  ┌───────────────────────────────────────────────────────────┐  │
│  │  [   (^) APLIKUJ TERAZ   ]   [* Zapisz]   [> Udostępnij]  │  │
│  └───────────────────────────────────────────────────────────┘  │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

### Ekran 3: Formularz aplikacji

```text
┌─────────────────────────────────────────────────────────────────┐
│  < Wróć do oferty                                               │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  (^) Aplikujesz na: Senior Python Developer                     │
│      TechCorp Sp. z o.o.                                        │
│  =======================================                        │
│                                                                 │
│  (D) TWOJE CV                                                   │
│  ┌───────────────────────────────────────────────────────────┐  │
│  │ (v) Jan_Kowalski_CV_2024.pdf                              │  │
│  │     Dodane: 10.12.2024    [Zmień CV]                      │  │
│  └───────────────────────────────────────────────────────────┘  │
│                                                                 │
│  (T) LIST MOTYWACYJNY (opcjonalnie)                             │
│  ┌───────────────────────────────────────────────────────────┐  │
│  │                                                           │  │
│  │  Napisz kilka słów o sobie i dlaczego                     │  │
│  │  interesujesz się tą ofertą...                            │  │
│  │                                                           │  │
│  │                                                           │  │
│  └───────────────────────────────────────────────────────────┘  │
│                                              0/2000 znaków      │
│                                                                 │
│  ($) OCZEKIWANIA FINANSOWE                                      │
│  [    15000    ] PLN netto/mies.                                │
│                                                                 │
│  (o) DOSTĘPNOŚĆ                                                 │
│  ( ) Natychmiast                                                │
│  (X) 2 tygodnie                                                 │
│  ( ) 1 miesiąc                                                  │
│  ( ) Inna: [________]                                           │
│                                                                 │
│  [X] Wyrażam zgodę na przetwarzanie danych osobowych...         │
│  [X] Chcę otrzymywać podobne oferty pracy                       │
│                                                                 │
│  ┌───────────────────────────────────────────────────────────┐  │
│  │         [     (v) WYŚLIJ APLIKACJĘ     ]                  │  │
│  └───────────────────────────────────────────────────────────┘  │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

### Ekran 4: Potwierdzenie i status

```text
┌─────────────────────────────────────────────────────────────────┐
│                                                                 │
│                         ( V )                                   │
│                                                                 │
│              Twoja aplikacja została wysłana!                   │
│                                                                 │
│  ┌───────────────────────────────────────────────────────────┐  │
│  │                                                           │  │
│  │  Senior Python Developer @ TechCorp                       │  │
│  │                                                           │  │
│  │  Status: (X) WYSŁANA                                      │  │
│  │  Data aplikacji: 12.12.2024, 14:32                        │  │
│  │                                                           │  │
│  │  =======================================                  │  │
│  │  (X) Wysłana  ->  ( ) W ocenie  ->  ( ) Rozmowa  ->  ( )  │  │
│  │  =======================================                  │  │
│  │                                                           │  │
│  │  Rekruter skontaktuje się z Tobą w ciągu 5 dni            │  │
│  │  roboczych. Włącz powiadomienia, żeby nie przegapić       │  │
│  │  wiadomości!                                              │  │
│  │                                                           │  │
│  └───────────────────────────────────────────────────────────┘  │
│                                                                 │
│  [(!) Powiadomienia]   [(#) Moje aplikacje]   [(H) Start]       │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

### 3.2. Interfejsy Programowe (API)

#### Integracje zewnętrzne

System HRflow integruje się z następującymi systemami zewnętrznymi:

**Integracje wymagane (MVP):**

| System | Typ integracji | Cel | Protokół |
|--------|----------------|-----|----------|
| **SAML** | Outbound | SSO, zarządzanie dostępami | SAML |
| **SMTP Server** | Outbound | Wysyłka powiadomień email | SMTP/TLS |
| **Google Calendar / Outlook 365** | Bidirectional | Umawianie spotkań rekrutacyjnych | OAuth2 + REST API |
| **Dostawca e-podpisu** | Outbound | Podpisywanie umów | REST API (webhook) |

**Integracje planowane (post-MVP):**

| System | Typ integracji | Cel | Protokół |
|--------|----------------|-----|----------|
| **LinkedIn** | Outbound | Publikacja ofert, import profili | OAuth2 + REST API |
| **JustJoin.it** | Outbound | Publikacja ofert | REST API |
| **Slack / MS Teams** | Bidirectional | Powiadomienia, feedback | Webhooks + Bot API |
| **Jira / Confluence** | Outbound | Onboarding developerów | REST API |
| **GitHub / GitLab** | Outbound | Onboarding, dostępy do repo | OAuth2 + REST API |
| **System payroll** | Outbound | Eksport danych pracowników | REST API / SFTP |

#### Specyfikacja API - przykład endpointów rekrutacji

**POST /api/v1/applications**
Złożenie aplikacji na ofertę

```json
// Request
{
  "job_offer_id": "uuid",
  "cv_file_id": "uuid",
  "cover_letter": "string (optional)",
  "expected_salary": 15000,
  "availability": "2_weeks",
  "consents": {
    "data_processing": true,
    "marketing": false
  }
}

// Response 201 Created
{
  "application_id": "uuid",
  "status": "SUBMITTED",
  "submitted_at": "2024-12-12T14:32:00Z",
  "estimated_response_days": 5
}
```

**GET /api/v1/applications/{id}/status**
Pobranie statusu aplikacji

```json
// Response 200 OK
{
  "application_id": "uuid",
  "job_offer": {
    "id": "uuid",
    "title": "Senior Python Developer",
    "company": "TechCorp Sp. z o.o."
  },
  "status": "IN_REVIEW",
  "status_history": [
    {"status": "SUBMITTED", "at": "2024-12-12T14:32:00Z"},
    {"status": "IN_REVIEW", "at": "2024-12-13T09:15:00Z"}
  ],
  "next_step": "Oczekuj na kontakt rekrutera"
}
```

**Webhook - zmiana statusu aplikacji**

```json
// POST na URL skonfigurowany przez kandydata
{
  "event": "application.status_changed",
  "application_id": "uuid",
  "old_status": "IN_REVIEW",
  "new_status": "INTERVIEW_SCHEDULED",
  "timestamp": "2024-12-14T10:00:00Z",
  "details": {
    "interview_date": "2024-12-18T14:00:00Z",
    "interview_type": "VIDEO"
  }
}
```

#### Integracja z Active Directory

```yaml
# Konfiguracja SAML
saml:
  enabled: true
  
  # Konfiguracja Dostawcy Tożsamości (Identity Provider - IdP)
  idp:
    # URL metadanych IdP (np. ADFS, Azure AD, Okta)
    entity_id: "http://adfs.company.local/adfs/services/trust"
    sso_url: "https://adfs.company.local/adfs/ls/"
    # Certyfikat publiczny IdP (niezbędny do weryfikacji podpisu)
    x509_cert: |
      MIID... (tutaj wklejasz treść certyfikatu od dostawcy) ...
    
  # Konfiguracja Aplikacji (Service Provider - SP)
  sp:
    entity_id: "https://hrflow.company.local/saml/metadata"
    assertion_consumer_service_url: "https://hrflow.company.local/saml/acs"

  # Mapowanie atrybutów (SAML Claims)
  # W SAML atrybuty często są pełnymi adresami URI (szczególnie w ADFS/Azure)
  attribute_mapping:
    username: "http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name"  # odpowiednik sAMAccountName
    email: "http://schemas.xmlsoap.org/ws/2005/05/identity/claims/emailaddress"
    first_name: "http://schemas.xmlsoap.org/ws/2005/05/identity/claims/givenname"
    last_name: "http://schemas.xmlsoap.org/ws/2005/05/identity/claims/surname"
    department: "http://schemas.xmlsoap.org/ws/2005/05/identity/claims/department" # lub nazwa własna
    manager: "http://schemas.company.local/claims/manager" # atrybut niestandardowy

  # Mapowanie ról/grup
  group_sync:
    enabled: true
    # Nazwa atrybutu w tokenie SAML, który przechowuje grupy użytkownika
    group_attribute: "http://schemas.microsoft.com/ws/2008/06/identity/claims/groups"
    # Mapowanie wartości z tokenu SAML na role w aplikacji
    role_mapping:
      # W SAML zazwyczaj przesyła się samą nazwę grupy (CN) lub jej ID, a nie pełne DN
      hrflow_admins: "HRFlow-Admins"
      hrflow_managers: "HRFlow-Managers"

```

#### Integracja z kalendarzem (Google Calendar)

```python
# Przykład użycia Google Calendar API
from googleapiclient.discovery import build

def schedule_interview(candidate_email, recruiter_email, datetime_utc, duration_minutes=60):
    """
    Tworzy wydarzenie w kalendarzu rekrutera i wysyła zaproszenie kandydatowi
    """
    event = {
        'summary': f'Rozmowa rekrutacyjna - {candidate_name}',
        'location': 'Google Meet (link zostanie wygenerowany)',
        'start': {'dateTime': datetime_utc, 'timeZone': 'Europe/Warsaw'},
        'end': {'dateTime': end_datetime_utc, 'timeZone': 'Europe/Warsaw'},
        'attendees': [
            {'email': candidate_email},
            {'email': recruiter_email}
        ],
        'conferenceData': {
            'createRequest': {'requestId': str(uuid4())}
        },
        'reminders': {
            'useDefault': False,
            'overrides': [
                {'method': 'email', 'minutes': 24 * 60},
                {'method': 'popup', 'minutes': 30}
            ]
        }
    }
    
    return calendar_service.events().insert(
        calendarId='primary',
        body=event,
        conferenceDataVersion=1,
        sendUpdates='all'
    ).execute()
```

---

## 4. Wymagania Funkcjonalne

### 4.1. Moduł Rekrutacji

#### WF-REK-001: Automatyczny Screening CV

**Opis:** System automatycznie analizuje przesłane CV, wydobywa kluczowe informacje (kompetencje, doświadczenie, wykształcenie) i ocenia dopasowanie kandydata do oferty.

**Historyjka Użytkownika:**
> Jako rekruter,  
> chcę aby system automatycznie analizował napływające CV i pokazywał mi ranking dopasowania,  
> abym mógł skupić się na najlepiej rokujących kandydatach zamiast ręcznie przeglądać setki dokumentów.

**Cel Biznesowy:** Skrócenie Time-to-Hire z 45 do 20 dni poprzez automatyzację wstępnej selekcji. Obsłużenie 2x więcej kandydatów bez zwiększania zespołu HR.

**Warunki Wstępne:**  

- Oferta pracy jest opublikowana w systemie  
- Kandydat przesłał CV w formacie PDF/DOCX

**Warunki Końcowe:**  

- CV jest sparsowane i informacje zapisane w profilu kandydata  
- Kandydat ma przypisany score dopasowania do oferty  
- Rekruter widzi kandydata na liście z informacją o dopasowaniu

**Kryteria Akceptacji:**

**WF-REK-001-01: Pomyślne parsowanie CV (Scenariusz główny)**  

- **Given:** Kandydat przesłał CV w formacie PDF zawierające sekcje: dane kontaktowe, doświadczenie, umiejętności, wykształcenie  
- **When:** System przetwarza przesłany plik  
- **Then:** W profilu kandydata zapisane są: imię, nazwisko, email, telefon, lista stanowisk z datami, lista umiejętności  
- **And:** Czas parsowania nie przekracza 10 sekund  
- **And:** Kandydat widzi podgląd wyekstrahowanych danych z możliwością korekty

**WF-REK-001-02: Scoring dopasowania kandydata (Scenariusz główny)**  

- **Given:** CV kandydata zostało sparsowane, oferta ma zdefiniowane wymagane i opcjonalne kompetencje  
- **When:** System oblicza dopasowanie kandydata  
- **Then:** Kandydat otrzymuje score 0-100% z rozbiciem na kategorie (umiejętności techniczne, doświadczenie, wykształcenie)  
- **And:** Rekruter widzi wizualnie które wymagania kandydat spełnia, a których nie

**WF-REK-001-03: CV w nieobsługiwanym formacie (Scenariusz alternatywny)**  

- **Given:** Kandydat próbuje przesłać CV w formacie innym niż PDF/DOCX (np. JPG, TXT)  
- **When:** Kliknie "Prześlij CV"  
- **Then:** System wyświetla komunikat "Akceptujemy tylko pliki PDF i DOCX. Proszę zapisać CV w jednym z tych formatów."  
- **And:** Plik nie jest przesyłany

**WF-REK-001-04: CV uszkodzone lub nieczytelne (Scenariusz wyjątkowy)**  

- **Given:** Kandydat przesłał plik PDF który jest uszkodzony lub zawiera tylko obrazy bez warstwy tekstowej  
- **When:** System próbuje sparsować plik  
- **Then:** System wyświetla komunikat "Nie udało się odczytać treści CV. Sprawdź czy plik nie jest uszkodzony i czy zawiera tekst (nie tylko obrazy)."  
- **And:** Kandydat może przesłać plik ponownie  
- **And:** Aplikacja trafia do kolejki do ręcznej weryfikacji przez rekrutera

---

#### WF-REK-002: Semantyczne Dopasowanie Kandydatów (Semantic Matching Engine)

**Opis:** Silnik dopasowania rozpoznaje hierarchię i relacje między kompetencjami, np. wnioskuje że znajomość "DB2" implikuje znajomość "SQL", albo że "React Developer" zna "JavaScript".

**Historyjka Użytkownika:**  
> Jako rekruter,  
> chcę aby system rozumiał że kandydat ze znajomością PostgreSQL prawdopodobnie zna też SQL,  
> abym nie odrzucał wykwalifikowanych kandydatów tylko dlatego, że nie użyli dokładnie tych słów kluczowych co w ofercie.

**Cel Biznesowy:** Zwiększenie Interview Acceptance Rate z 10% do 15% poprzez eliminację fałszywych odrzuceń.

**Warunki Wstępne:**  

- Zdefiniowana ontologia kompetencji (graf wiedzy)  
- CV kandydata zostało sparsowane

**Warunki Końcowe:**  

- Score uwzględnia kompetencje pokrewne  
- Rekruter widzi wyjaśnienie dlaczego kandydat pasuje/nie pasuje

**Kryteria Akceptacji:**

**WF-REK-002-01: Rozpoznanie kompetencji pokrewnych (Scenariusz główny)**  

- **Given:** Oferta wymaga "SQL", kandydat ma w CV "PostgreSQL" i "Oracle DB"  
- **When:** System oblicza dopasowanie  
- **Then:** Wymaganie "SQL" jest oznaczone jako spełnione z adnotacją "Wykryte poprzez: PostgreSQL, Oracle DB"  
- **And:** Score kandydata jest wyższy niż przy dosłownym porównaniu

**WF-REK-002-02: Hierarchia frameworków (Scenariusz główny)**  

- **Given:** Oferta wymaga "JavaScript", kandydat ma w CV tylko "React" i "Vue.js"  
- **When:** System oblicza dopasowanie  
- **Then:** Wymaganie "JavaScript" jest oznaczone jako spełnione z adnotacją "Wykryte poprzez: React, Vue.js"

**WF-REK-002-03: Brak kompetencji i pokrewnych (Scenariusz alternatywny)**  

- **Given:** Oferta wymaga "Kubernetes", kandydat nie ma żadnych kompetencji z obszaru container orchestration  
- **When:** System oblicza dopasowanie  
- **Then:** Wymaganie "Kubernetes" jest oznaczone jako niespełnione  
- **And:** System sugeruje kandydatowi szkolenia z Kubernetes jeśli zaaplikuje

---

#### WF-REK-003: Portal Kandydata z Real-time Tracking

**Opis:** Dedykowany portal dla kandydatów pozwalający śledzić status aplikacji w czasie rzeczywistym i otrzymywać automatyczny feedback.

**Historyjka Użytkownika:**  
> Jako kandydat,  
> chcę widzieć na jakim etapie jest moja aplikacja bez konieczności dzwonienia do HR,  
> abym miał kontrolę nad procesem i mógł planować swoje działania.

**Cel Biznesowy:** Osiągnięcie Candidate NPS (cNPS) na poziomie +50 poprzez transparentność procesu.

**Warunki Wstępne:**  

- Kandydat złożył aplikację i ma konto w systemie  
- Aplikacja ma przypisany status

**Warunki Końcowe:**  

- Kandydat widzi aktualny status  
- Kandydat otrzymuje powiadomienie przy zmianie statusu

**Kryteria Akceptacji:**

**WF-REK-003-01: Podgląd statusu aplikacji (Scenariusz główny)**  

- **Given:** Jestem zalogowany jako kandydat i mam 3 aktywne aplikacje  
- **When:** Wchodzę na stronę "Moje aplikacje"  
- **Then:** Widzę listę wszystkich moich aplikacji z aktualnym statusem (np. "Wysłana", "W ocenie", "Zaproszenie na rozmowę", "Odrzucona")  
- **And:** Dla każdej aplikacji widzę timeline z historią zmian statusów i datami

**WF-REK-003-02: Powiadomienie o zmianie statusu (Scenariusz główny)**  

- **Given:** Moja aplikacja zmieniła status z "W ocenie" na "Zaproszenie na rozmowę"  
- **When:** Rekruter zapisuje zmianę statusu  
- **Then:** Otrzymuję powiadomienie email w ciągu 5 minut  
- **And:** Widzę powiadomienie w portalu (czerwona kropka przy dzwoneczku)  
- **And:** Jeśli mam aplikację mobilną, dostaję push notification

**WF-REK-003-03: Automatyczny feedback przy odrzuceniu (Scenariusz główny)**  

- **Given:** Moja aplikacja została odrzucona, rekruter wybrał powód odrzucenia  
- **When:** Status zmienia się na "Odrzucona"  
- **Then:** Otrzymuję spersonalizowany email z informacją o powodzie (bez szczegółów wrażliwych)  
- **And:** Jeśli powód to brak kompetencji X, system sugeruje szkolenia z X

**WF-REK-003-04: Aplikacja bez zmian przez 14 dni (Scenariusz wyjątkowy)**  

- **Given:** Moja aplikacja jest w statusie "W ocenie" od 14 dni bez żadnych zmian  
- **When:** Mija 14 dni  
- **Then:** Otrzymuję automatyczny email "Twoja aplikacja jest nadal rozpatrywana. Dziękujemy za cierpliwość."  
- **And:** Rekruter otrzymuje alert o zaległej aplikacji

---

#### WF-REK-004: Giełda Talentów (Internal Talent Marketplace)

**Opis:** System automatycznie dopasowuje obecnych pracowników do nowych wakatów wewnętrznych na podstawie ich umiejętności i preferencji rozwojowych.

**Historyjka Użytkownika:**  
> Jako pracownik,  
> chcę dostawać powiadomienia o wewnętrznych wakatach pasujących do moich umiejętności,  
> abym mógł rozwijać karierę w obecnej firmie zamiast szukać pracy na zewnątrz.

**Cel Biznesowy:** Wypełnienie 40% nowych wakatów kandydatami wewnętrznymi w ciągu 9 miesięcy.

**Warunki Wstępne:**  

- Pracownik ma uzupełniony profil umiejętności  
- Istnieją otwarte wakaty wewnętrzne

**Warunki Końcowe:**  

- Pracownik widzi dopasowane oferty wewnętrzne  
- Menedżer widzi zainteresowanych pracowników

**Kryteria Akceptacji:**

**WF-REK-004-01: Rekomendacje wakatów wewnętrznych (Scenariusz główny)**  

- **Given:** Jestem pracownikiem z profilem zawierającym: Python (Expert), SQL (Advanced), 3 lata doświadczenia  
- **And:** W firmie otwarto wakat "Senior Data Engineer" wymagający Python i SQL  
- **When:** Otwieram sekcję "Możliwości rozwoju" w portalu  
- **Then:** Widzę ten wakat z informacją o 85% dopasowania  
- **And:** Widzę które moje kompetencje pasują, a czego mi brakuje

**WF-REK-004-02: Aplikowanie na wakat wewnętrzny (Scenariusz główny)**  

- **Given:** Znalazłem interesujący wakat wewnętrzny, mój bezpośredni przełożony skonfigurował zgodę na rekrutację wewnętrzną  
- **When:** Klikam "Wyraź zainteresowanie"  
- **Then:** Mój menedżer i HR otrzymują powiadomienie  
- **And:** Rekruter prowadzący wakat widzi mnie na liście zainteresowanych z pełnym profilem

**WF-REK-004-03: Brak zgody menedżera na rekrutację wewnętrzną (Scenariusz alternatywny)**  

- **Given:** Mój bezpośredni przełożony ustawił blokadę rekrutacji wewnętrznej dla swojego zespołu  
- **When:** Próbuję kliknąć "Wyraź zainteresowanie"  
- **Then:** System wyświetla komunikat "Aplikowanie na wewnętrzne wakaty wymaga rozmowy z Twoim menedżerem. Skontaktuj się z HR jeśli chcesz omówić możliwości."

---

#### WF-REK-005: System Poleceń Pracowniczych (Employee Referral Engine)

**Opis:** Gamifikowany system poleceń z transparentnym śledzeniem statusu i automatycznym naliczaniem nagród.

**Historyjka Użytkownika:**
> Jako pracownik,  
> chcę polecać znajomych na otwarte stanowiska i widzieć status mojego polecenia,  
> abym był motywowany do rekomendowania dobrych kandydatów.

**Cel Biznesowy:** Zwiększenie udziału zatrudnień z poleceń z 8% do 25% w ciągu 9 miesięcy, skrócenie czasu zatrudnienia kandydatów z polecenia o 30%.

**Warunki Wstępne:**  

- Pracownik jest zatrudniony min. 3 miesiące  
- Istnieją otwarte wakaty objęte programem poleceń

**Warunki Końcowe:**  

- Polecenie jest zarejestrowane  
- Pracownik może śledzić status

**Kryteria Akceptacji:**

**WF-REK-005-01: Polecenie kandydata (Scenariusz główny)**  

- **Given:** Jestem pracownikiem z 6-miesięcznym stażem, mam znajomego szukającego pracy  
- **And:** Istnieje otwarty wakat "Frontend Developer" z bonusem za polecenie 5000 PLN  
- **When:** Wchodzę w sekcję "Poleć znajomego", wybieram wakat i podaję dane znajomego (imię, email, opcjonalnie CV)  
- **Then:** Znajomy otrzymuje spersonalizowany email z zaproszeniem do aplikowania  
- **And:** Polecenie pojawia się w moim panelu "Moje polecenia" ze statusem "Wysłane zaproszenie"

**WF-REK-005-02: Śledzenie statusu polecenia (Scenariusz główny)**  

- **Given:** Poleciłem kandydata tydzień temu, kandydat złożył aplikację  
- **When:** Wchodzę w "Moje polecenia"  
- **Then:** Widzę aktualny status: "Kandydat aplikował → W ocenie → [następne etapy]"  
- **And:** Widzę estymowaną datę decyzji i aktualny poziom mojego bonusu (np. "Bonus: 2500 PLN zablokowane, wypłata po okresie próbnym")

**WF-REK-005-03: Automatyczne naliczenie bonusu (Scenariusz główny)**  

- **Given:** Polecony kandydat został zatrudniony i ukończył 3-miesięczny okres próbny  
- **When:** Mija data końca okresu próbnego  
- **Then:** Mój bonus zmienia status na "Do wypłaty"  
- **And:** Dział kadr otrzymuje automatyczne zlecenie wypłaty bonusu  
- **And:** Dostaję powiadomienie "Gratulacje! Twój bonus za polecenie [imię] jest gotowy do wypłaty."

**WF-REK-005-04: Polecenie osoby już w bazie (Scenariusz alternatywny)**  

- **Given:** Próbuję polecić znajomego którego email już istnieje w bazie kandydatów  
- **When:** Podaję jego email  
- **Then:** System informuje "Ten kandydat jest już w naszej bazie. Jeśli chcesz powiązać polecenie, skontaktuj się z HR."

---

#### WF-REK-006: Anonimizacja Procesu Selekcji (Diversity & Inclusion)

**Opis:** Mechanizm ukrywania danych mogących prowadzić do nieświadomych uprzedzeń (imię, zdjęcie, wiek, uczelnia) w fazie wstępnej selekcji.

**Historyjka Użytkownika:**
> Jako HR Manager,  
> chcę mieć możliwość włączenia trybu anonimowego w procesie selekcji,  
> abyśmy oceniali kandydatów tylko na podstawie kompetencji, nie danych demograficznych.

**Cel Biznesowy:** Zwiększenie różnorodności kandydatów zapraszanych na rozmowy o 30% w ciągu 6 miesięcy.

**Warunki Wstępne:**  

- HR Manager skonfigurował tryb anonimowy dla danego procesu rekrutacyjnego  
- Kandydaci złożyli aplikacje

**Warunki Końcowe:**  

- Rekruter ocenia kandydatów bez dostępu do danych wrażliwych  
- Dane są ujawniane dopiero na etapie zaproszenia na rozmowę

**Kryteria Akceptacji:**

**WF-REK-006-01: Widok anonimowy dla rekrutera (Scenariusz główny)**  

- **Given:** Jestem rekruterem, proces ma włączony tryb anonimowy  
- **When:** Otwieram listę kandydatów  
- **Then:** Zamiast imion widzę identyfikatory (np. "Kandydat #A7F3")  
- **And:** Nie widzę: zdjęć, wieku, płci, nazw uczelni (tylko poziom wykształcenia)  
- **And:** Widzę: listę kompetencji, lata doświadczenia (bez dat), opis doświadczenia

**WF-REK-006-02: Ujawnienie danych przy zaproszeniu (Scenariusz główny)**  

- **Given:** Zdecydowałem się zaprosić Kandydata #A7F3 na rozmowę  
- **When:** Klikam "Zaproś na rozmowę"  
- **Then:** System ujawnia pełne dane kandydata (imię, kontakt)  
- **And:** Mogę teraz wysłać spersonalizowane zaproszenie

**WF-REK-006-03: Analiza bias w ogłoszeniach (Scenariusz główny)**  

- **Given:** Tworzę nowe ogłoszenie o pracę  
- **When:** Zapisuję treść ogłoszenia  
- **Then:** System analizuje tekst pod kątem language bias (np. agresywny język kojarzy się z męskimi kandydatami)  
- **And:** Jeśli wykryje bias, sugeruje alternatywne sformułowania (np. "ninja" → "specjalista", "young dynamic team" → "energetic team")

---

### 4.2. Moduł Onboardingu

#### WF-ONB-001: Cyfrowy Obieg Dokumentów z E-podpisem

**Opis:** W pełni elektroniczny proces podpisywania dokumentów zatrudnienia - umowy, NDA, regulaminy - bez konieczności drukowania i skanowania.

**Historyjka Użytkownika:**  
> Jako nowo zatrudniony pracownik,  
> chcę podpisać wszystkie dokumenty elektronicznie przed pierwszym dniem pracy,  
> abym w pierwszy dzień mógł skupić się na poznawaniu zespołu, a nie papierologii.

**Cel Biznesowy:** Redukcja czasu pracy działu kadr na obsługę dokumentacji nowo zatrudnionych o 80% w ciągu 3 miesięcy.

**Warunki Wstępne:**  

- Kandydat zaakceptował ofertę pracy
- HR przygotował pakiet dokumentów do podpisu

**Warunki Końcowe:**  

- Wszystkie dokumenty są podpisane elektronicznie
- Dokumenty są zarchiwizowane w systemie
- Dział kadr może wygenerować raport zgodności

**Kryteria Akceptacji:**

**WF-ONB-001-01: Podpisanie umowy elektronicznie (Scenariusz główny)**  

- **Given:** Jestem nowo zatrudnionym pracownikiem, HR wysłał mi pakiet dokumentów do podpisu
- **When:** Otwieram link z emaila, loguję się, przeglądam dokumenty i klikam "Podpisz"
- **Then:** System wysyła mnie do dostawcy e-podpisu (np. Autenti)
- **And:** Po złożeniu podpisu, wracam do HRflow gdzie widzę status "Podpisane"
- **And:** Otrzymuję email z podpisanymi dokumentami w PDF

**WF-ONB-001-02: Automatyczne generowanie umowy (Scenariusz główny)**  

- **Given:** Jestem HR Adminem, kandydat Jan Kowalski zaakceptował ofertę na stanowisko Senior Developer z wynagrodzeniem 20 000 PLN B2B
- **When:** Klikam "Generuj umowę" i wybieram szablon "Umowa B2B IT"
- **Then:** System automatycznie wypełnia szablon danymi: imię, nazwisko, stanowisko, wynagrodzenie, data rozpoczęcia
- **And:** Mogę przejrzeć dokument przed wysłaniem do podpisu
- **And:** Dokument jest zapisany w formacie pozwalającym na e-podpis

**WF-ONB-001-03: Przypomnienie o niepodpisanych dokumentach (Scenariusz alternatywny)**  

- **Given:** Wysłano dokumenty do podpisu 3 dni temu, pracownik ich nie podpisał
- **When:** Mija 72 godziny od wysłania
- **Then:** System wysyła automatyczne przypomnienie do pracownika
- **And:** HR widzi alert w panelu o zaległych dokumentach

**WF-ONB-001-04: Wygaśnięcie linku do podpisu (Scenariusz wyjątkowy)**  

- **Given:** Link do podpisu dokumentów był ważny 7 dni, pracownik próbuje go użyć po 10 dniach
- **When:** Klika w stary link
- **Then:** System wyświetla komunikat "Link wygasł. Skontaktuj się z działem HR aby otrzymać nowy link."
- **And:** HR Admin może wygenerować nowy link jednym kliknięciem

---

#### WF-ONB-002: Zgrywalizowany Moduł Wdrożeniowy

**Opis:** Interaktywny, zgrywalizowany program onboardingowy z zadaniami, quizami i śledzeniem postępów, zintegrowany z narzędziami deweloperskimi.

**Historyjka Użytkownika:**  
> Jako nowy programista,  
> chcę mieć jasną ścieżkę onboardingu z konkretnymi zadaniami i celami,  
> abym wiedział co mam robić i mógł mierzyć swój postęp.

**Cel Biznesowy:** Skrócenie Time-to-Productivity nowych programistów z 3 miesięcy do 6 tygodni w ciągu roku.

**Warunki Wstępne:**  

- Pracownik rozpoczął pracę
- HR/Menedżer przypisał odpowiednią ścieżkę onboardingu

**Warunki Końcowe:**  

- Pracownik ukończył wszystkie obowiązkowe moduły
- Menedżer ma raport z postępów onboardingu

**Kryteria Akceptacji:**

**WF-ONB-002-01: Start programu onboardingowego (Scenariusz główny)**  

- **Given:** Jestem nowym programistą, to mój pierwszy dzień pracy
- **When:** Loguję się do HRflow
- **Then:** Widzę spersonalizowaną ścieżkę onboardingową "Developer Onboarding" z etapami: Tydzień 1-2 (Podstawy), Tydzień 3-4 (Projekt), Tydzień 5-6 (Samodzielność)
- **And:** Każdy etap ma konkretne zadania, materiały i quizy
- **And:** Widzę progress bar pokazujący 0% ukończenia

**WF-ONB-002-02: Wykonanie zadania onboardingowego (Scenariusz główny)**  

- **Given:** Mam zadanie "Skonfiguruj środowisko deweloperskie" z checklistą: zainstaluj IDE, sklonuj repo, uruchom projekt lokalnie
- **When:** Wykonuję kolejne kroki i zaznaczam je jako ukończone
- **Then:** Mój progress rośnie, zdobywam punkty XP (np. 50 XP za zadanie)
- **And:** Odblokowane zostaje kolejne zadanie
- **And:** Mój menedżer widzi aktualizację postępu w swoim panelu

**WF-ONB-002-03: Integracja z repozytoriami kodu (Scenariusz główny)**  

- **Given:** Mam zadanie "Zrób pierwszy commit do repozytorium projektu"
- **When:** Robię commit i push do repo (GitHub/GitLab)
- **Then:** System automatycznie wykrywa commit poprzez webhook
- **And:** Zadanie oznacza się jako ukończone
- **And:** Dostaję badge "First Commit" i bonus XP

**WF-ONB-002-04: Quiz sprawdzający wiedzę (Scenariusz główny)**  

- **Given:** Ukończyłem moduł "Architektura systemu"
- **When:** Przechodzę do quizu końcowego
- **Then:** Muszę odpowiedzieć na 10 pytań (próg zaliczenia: 70%)
- **And:** Jeśli zdam, odblokowany jest następny moduł
- **And:** Jeśli nie zdam, mogę powtórzyć quiz po 24h lub przejrzeć materiały ponownie

**WF-ONB-002-05: Buddy system (Scenariusz główny)**  

- **Given:** Menedżer przypisał mi "buddy'ego" - doświadczonego pracownika
- **When:** Mam pytanie lub problem
- **Then:** Widzę w systemie kto jest moim buddy i mogę wysłać mu wiadomość bezpośrednio z HRflow
- **And:** Buddy dostaje powiadomienie i może odpowiedzieć
- **And:** Po onboardingu, buddy może ocenić moją gotowość do samodzielnej pracy

---

### 4.3. Moduł Rozwoju i Szkoleń

#### WF-DEV-001: Platforma LMS ze Spersonalizowanymi Ścieżkami Rozwoju

**Opis:** System e-learningowy sugerujący szkolenia na podstawie luk kompetencyjnych, celów rozwojowych i wymagań stanowiska.

**Historyjka Użytkownika:**  
> Jako pracownik,  
> chcę dostawać rekomendacje szkoleń dopasowanych do moich celów zawodowych,  
> abym mógł systematycznie rozwijać kompetencje potrzebne do awansu.

**Cel Biznesowy:** Przeszkolenie 60% kadry technicznej z nowych technologii chmurowych w ciągu 12 miesięcy, redukcja wydatków na zewnętrznych konsultantów o 200 tys. PLN.

**Warunki Wstępne:**  

- Pracownik ma uzupełniony profil kompetencji
- Dostępne są szkolenia w bibliotece LMS

**Warunki Końcowe:**  

- Pracownik ukończył szkolenie
- Kompetencja dodana do profilu
- Menedżer ma raport z rozwoju zespołu

**Kryteria Akceptacji:**

**WF-DEV-001-01: Rekomendacje szkoleń (Scenariusz główny)**  

- **Given:** Jestem Python Developerem, mój cel na rok to "nauczyć się AWS"
- **And:** Na moim stanowisku wymagane jest AWS (którego nie mam w profilu)
- **When:** Otwieram sekcję "Mój rozwój"
- **Then:** Na górze widzę spersonalizowane rekomendacje: "AWS dla Python Developerów", "Podstawy Cloud Computing"
- **And:** Przy każdym szkoleniu widzę szacowany czas, poziom trudności i jak wypełnia moje luki

**WF-DEV-001-02: Ukończenie szkolenia z certyfikatem (Scenariusz główny)**  

- **Given:** Zapisałem się na szkolenie "AWS Fundamentals" (8 godzin, 5 modułów)
- **When:** Ukończę wszystkie moduły i zdam test końcowy (min. 80%)
- **Then:** Otrzymuję certyfikat PDF do pobrania
- **And:** Kompetencja "AWS - podstawy" automatycznie dodaje się do mojego profilu
- **And:** Mój menedżer otrzymuje powiadomienie o ukończonym szkoleniu

**WF-DEV-001-03: Ścieżka rozwoju (Learning Path) (Scenariusz główny)**  

- **Given:** Chcę zostać Tech Leadem w ciągu 2 lat
- **When:** Wybieram cel "Tech Lead" w kreatorze ścieżki
- **Then:** System generuje spersonalizowaną ścieżkę z sekwencją szkoleń: techniczne → leadership → communication
- **And:** Widzę timeline z kamieniami milowymi
- **And:** Mogę zapisać ścieżkę i śledzić postęp

**WF-DEV-001-04: Brak czasu na szkolenie (Scenariusz alternatywny)**  

- **Given:** Zapisałem się na szkolenie, ale nie mam czasu w godzinach pracy
- **When:** Rozmawiam z menedżerem przez system (sekcja "Prośba o czas na rozwój")
- **Then:** Menedżer dostaje notyfikację i może zaakceptować/odrzucić prośbę
- **And:** Jeśli zaakceptuje, blok czasu pojawia się w kalendarzu jako "Czas rozwojowy"

---

#### WF-DEV-002: System OKR (Objectives and Key Results)

**Opis:** System kaskadowania celów od strategii firmy przez cele zespołowe do celów indywidualnych, z wizualizacją powiązań i śledzeniem postępu.

**Historyjka Użytkownika:**  
> Jako menedżer,  
> chcę widzieć jak cele mojego zespołu łączą się z celami firmy,  
> abym mógł lepiej priorytetyzować pracę i tłumaczyć zespołowi sens naszych działań.

**Cel Biznesowy:** Zapewnienie 100% transparentności powiązań między celami indywidualnymi a strategią firmy w ciągu 3 miesięcy.

**Warunki Wstępne:**  

- Zarząd zdefiniował cele strategiczne firmy
- Trwa kwartał (cykl OKR)

**Warunki Końcowe:**  

- Cele są skaskadowane na wszystkie poziomy
- Postęp jest mierzony i widoczny

**Kryteria Akceptacji:**

**WF-DEV-002-01: Tworzenie OKR indywidualnego (Scenariusz główny)**  

- **Given:** Jestem pracownikiem, rozpoczyna się nowy kwartał
- **And:** Mój menedżer opublikował cele zespołu
- **When:** Tworzę swój OKR z Objective "Poprawić wydajność API" i Key Results: "Zmniejszyć response time o 30%", "Osiągnąć 99.9% uptime"
- **Then:** System wymusza powiązanie z celem zespołowym (wybieram z listy)
- **And:** Menedżer otrzymuje powiadomienie do akceptacji
- **And:** Po akceptacji, mój OKR jest widoczny w drzewie celów

**WF-DEV-002-02: Wizualizacja drzewa celów (Scenariusz główny)**  

- **Given:** Jestem pracownikiem
- **When:** Otwieram "Drzewo OKR"
- **Then:** Widzę hierarchiczną wizualizację: Cele Firmy → Cele Mojego Działu → Cele Zespołu → Moje Cele
- **And:** Widzę progress każdego celu (0-100%)
- **And:** Mogę kliknąć w dowolny cel aby zobaczyć szczegóły

**WF-DEV-002-03: Aktualizacja postępu Key Result (Scenariusz główny)**  

- **Given:** Mój Key Result to "Zmniejszyć response time o 30%", obecny postęp to 60%
- **When:** Zmierzę że response time spadł o kolejne 10% (łącznie 20%)
- **Then:** Aktualizuję wartość w systemie, postęp zmienia się na ~67%
- **And:** System automatycznie przelicza postęp nadrzędnego Objective
- **And:** Dodaję komentarz z wyjaśnieniem co zrobiłem

**WF-DEV-002-04: Check-in tygodniowy (Scenariusz główny)**  

- **Given:** Jest piątek, system przypomina o aktualizacji OKR
- **When:** Wchodzę w sekcję "Check-in"
- **Then:** Widzę formularz z moimi Key Results i mogę szybko zaktualizować postęp
- **And:** Mogę dodać notatkę "co poszło dobrze", "co blokowało"
- **And:** Menedżer widzi moje check-iny przed spotkaniem 1:1

---

#### WF-DEV-003: Continuous Feedback (Ciągła Informacja Zwrotna)

**Opis:** System umożliwiający regularne, nieformalne wymiany feedbacku między współpracownikami, wspierający kulturę ciągłego doskonalenia.

**Historyjka Użytkownika:**  
> Jako pracownik,  
> chcę móc szybko docenić kolegę lub poprosić o feedback po zakończeniu projektu,  
> abym mógł ciągle się rozwijać bez czekania na roczną ocenę.

**Cel Biznesowy:** Przejście z rocznych ocen na system ciągłego feedbacku, uzyskanie średnio 4 opinii peer-to-peer na pracownika miesięcznie w ciągu 6 miesięcy.

**Warunki Wstępne:**  

- Pracownicy są przypisani do zespołów
- System feedbacku jest aktywny

**Warunki Końcowe:**  

- Feedback jest zapisany i dostępny dla odbiorcy
- Statystyki feedbacku są widoczne dla HR

**Kryteria Akceptacji:**

**WF-DEV-003-01: Wysłanie szybkiego feedbacku (Scenariusz główny)**  

- **Given:** Kolega z zespołu pomógł mi rozwiązać trudny problem
- **When:** Klikam "Wyślij kudos" przy jego profilu, wybieram kategorię "Pomoc zespołowa", piszę krótką wiadomość
- **Then:** Kolega otrzymuje powiadomienie z moim feedbackiem
- **And:** Feedback pojawia się na jego profilu (widoczny dla niego i jego menedżera)
- **And:** Zdobywa punkty do rankingu miesięcznego "Pomocni współpracownicy"

**WF-DEV-003-02: Poproszenie o feedback (Scenariusz główny)**  

- **Given:** Ukończyłem duży projekt i chcę wiedzieć jak mi poszło
- **When:** Wysyłam prośbę o feedback do 3 osób z którymi pracowałem
- **Then:** Każda osoba otrzymuje powiadomienie z prośbą
- **And:** Mają 7 dni na odpowiedź
- **And:** Po otrzymaniu feedbacku, widzę go w sekcji "Otrzymany feedback"

**WF-DEV-003-03: Anonimowy feedback (Scenariusz alternatywny)**  

- **Given:** Chcę dać konstruktywną krytykę, ale wolę pozostać anonimowy
- **When:** Wysyłam feedback z zaznaczoną opcją "Wyślij anonimowo"
- **Then:** Odbiorca widzi treść feedbacku bez informacji kto go wysłał
- **And:** Menedżer odbiorcy również nie widzi nadawcy
- **And:** W statystykach HR widać tylko że był anonimowy feedback

**WF-DEV-003-04: Integracja ze Slackiem/Teams (Scenariusz główny)**  

- **Given:** Mam zainstalowaną integrację HRflow ze Slackiem
- **When:** Napiszę w Slacku "/kudos @jan.kowalski Świetna robota z prezentacją!"
- **Then:** Feedback trafia do systemu HRflow
- **And:** Jan dostaje powiadomienie zarówno w Slacku jak i w HRflow

---

### 4.4. Moduł Analityki HR

#### WF-ANA-001: Predykcja Rotacji Pracowników (Retention AI)

**Opis:** Moduł wykorzystujący machine learning do identyfikacji pracowników zagrożonych odejściem na podstawie wzorców zachowań, wyników ankiet i danych systemowych.

**Historyjka Użytkownika:**
> Jako HR Manager,  
> chcę wiedzieć z wyprzedzeniem którzy kluczowi pracownicy mogą odejść,  
> abym mógł podjąć działania retencyjne zanim będzie za późno.

**Cel Biznesowy:** Obniżenie wskaźnika rotacji kluczowych specjalistów o 15% w ciągu roku, poprzez wykrywanie ryzyka odejścia na 30 dni przed rezygnacją.

**Warunki Wstępne:**

- Pracownik jest w systemie min. 6 miesięcy (dane do analizy)
- Skonfigurowane ankiety pulsujące
- Model ML wytrenowany na danych historycznych

**Warunki Końcowe:**

- HR/Menedżer widzi alert o ryzyku
- Uruchomiony proces retencyjny

**Kryteria Akceptacji:**

**WF-ANA-001-01: Dashboard ryzyka rotacji (Scenariusz główny)**

- **Given:** Jestem HR Managerem z dostępem do analityki
- **When:** Otwieram dashboard "Retention Risk"
- **Then:** Widzę listę pracowników posortowaną wg ryzyka odejścia (%, kolor: zielony/żółty/czerwony)
- **And:** Dla pracowników z ryzykiem >70% widzę główne czynniki ryzyka (np. "brak awansu 2 lata", "spadek engagement score")
- **And:** Mogę filtrować po dziale, stanowisku, stażu

**WF-ANA-001-02: Alert o wysokim ryzyku (Scenariusz główny)**

- **Given:** Ryzyko odejścia programisty Jana Kowalskiego wzrosło z 40% do 75% (próg alertu: 70%)
- **When:** System przelicza ryzyko (codziennie o 6:00)
- **Then:** Menedżer Jana i HR otrzymują email "Alert: Wysokie ryzyko odejścia - Jan Kowalski"
- **And:** W alercie są sugerowane działania: "Zaplanuj rozmowę 1:1", "Sprawdź możliwości awansu", "Przejrzyj wynagrodzenie vs. rynek"

**WF-ANA-001-03: Czynniki wpływające na ryzyko (Scenariusz główny)**

- **Given:** Kliknę w konkretnego pracownika na dashboardzie
- **When:** Otwieram szczegóły
- **Then:** Widzę rozbicie ryzyka na czynniki z wagami: np. "Brak podwyżki 18 miesięcy (waga 30%)", "Niska ocena w ankiecie pulsującej (waga 25%)", "Brak rozwoju kompetencji (waga 20%)"
- **And:** Przy każdym czynniku widzę rekomendację działania

**WF-ANA-001-04: Ankieta pulsująca (Scenariusz główny)**

- **Given:** Jestem pracownikiem, jest pierwszy poniedziałek miesiąca
- **When:** Dostaję powiadomienie o ankiecie
- **Then:** Ankieta ma max 5 pytań (np. "Jak oceniasz swoje samopoczucie w pracy 1-10?", "Czy czujesz się doceniany?")
- **And:** Wypełnienie zajmuje max 2 minuty
- **And:** Odpowiedzi są anonimowe dla menedżera (widzi tylko średnią zespołu), ale system używa ich do modelu retencji

---

#### WF-ANA-002: System Oceny Potencjału (9-box Grid)

**Opis:** Narzędzie dla menedżerów do oceny pracowników w dwóch wymiarach: wydajność (performance) i potencjał rozwojowy, wspierające planowanie sukcesji.

**Historyjka Użytkownika:**
> Jako menedżer,  
> chcę mieć ustrukturyzowane narzędzie do oceny potencjału moich ludzi,  
> abym mógł planować ich rozwój i identyfikować przyszłych liderów.

**Cel Biznesowy:** Zidentyfikowanie następców dla 90% kluczowych stanowisk menedżerskich w ciągu 6 miesięcy.

**Warunki Wstępne:**

- Menedżer ma zespół min. 3 osoby
- Trwa okres ocen (np. koniec kwartału)

**Warunki Końcowe:**

- Każdy pracownik ma przypisaną pozycję w 9-box
- HR ma raport talent pool
- Zdefiniowane plany rozwojowe dla High Potentials

**Kryteria Akceptacji:**

**WF-ANA-002-01: Ocena pracownika w 9-box (Scenariusz główny)**

- **Given:** Jestem menedżerem, rozpoczął się okres ocen
- **When:** Otwieram profil pracownika w sekcji "Ocena potencjału"
- **Then:** Widzę matrycę 3x3 (oś X: Performance Low/Medium/High, oś Y: Potential Low/Medium/High)
- **And:** Dla każdej osi mam suwak z uzasadnieniem (np. "High Performance because: przekroczył cele o 20%")
- **And:** System automatycznie umieszcza pracownika w odpowiedniej kratce

**WF-ANA-002-02: Widok zespołu na 9-box (Scenariusz główny)**

- **Given:** Oceniłem wszystkich pracowników swojego zespołu
- **When:** Otwieram widok "Mój zespół - Talent Grid"
- **Then:** Widzę wszystkich pracowników rozłożonych na matrycy (jako avatary lub inicjały)
- **And:** Widzę statystyki: "High Potential: 3 osoby", "Solid Performers: 5 osób", "Underperformers: 1 osoba"
- **And:** Mogę porównać z poprzednim kwartałem (kto awansował, kto spadł)

**WF-ANA-002-03: Planowanie sukcesji (Scenariusz główny)**

- **Given:** Jestem HR Managerem, mam zdefiniowane kluczowe stanowiska w firmie
- **When:** Otwieram moduł "Planowanie sukcesji"
- **Then:** Widzę listę kluczowych stanowisk z informacją: obecny holder, gotowość następcy (czerwony/żółty/zielony), kandydaci na następcę
- **And:** Mogę przypisać kandydatów do stanowisk z oceną "gotowy teraz", "gotowy za 1-2 lata", "wymaga rozwoju"
- **And:** System alertuje jeśli stanowisko nie ma żadnego następcy

---

### 4.5. Moduł Kafeterii Benefitowej

#### WF-BEN-001: Elastyczna Platforma Benefitowa

**Opis:** System pozwalający pracownikom samodzielnie wybierać benefity z dostępnej puli punktów, z możliwością wymiany na usługi prozdrowotne, szkoleniowe i lifestyle.

**Historyjka Użytkownika:**
> Jako pracownik,  
> chcę samodzielnie decydować na co wydać mój budżet benefitowy,  
> abym mógł wybrać rzeczy które naprawdę mi się przydadzą, zamiast dostawać narzucone benefity.

**Cel Biznesowy:** Zwiększenie utylizacji budżetu szkoleniowo-benefitowego do 95% w ciągu roku (z obecnych 60%).

**Warunki Wstępne:**

- Pracownik ma przypisany budżet punktów
- Skonfigurowane są kategorie i dostawcy benefitów

**Warunki Końcowe:**

- Pracownik wykorzystał punkty
- Zamówienie trafiło do dostawcy
- HR ma raport wykorzystania

**Kryteria Akceptacji:**

**WF-BEN-001-01: Przeglądanie kafeterii (Scenariusz główny)**

- **Given:** Jestem pracownikiem z budżetem 500 punktów miesięcznie
- **When:** Otwieram "Kafeterię benefitów"
- **Then:** Widzę kategorie: Zdrowie, Sport, Kultura, Rozwój, Lifestyle
- **And:** W każdej kategorii widzę dostępne opcje z ceną w punktach
- **And:** Na górze widzę moje saldo: "Dostępne: 500 pkt, Wykorzystane: 0 pkt"

**WF-BEN-001-02: Zakup benefitu (Scenariusz główny)**

- **Given:** Mam 500 punktów, chcę kupić karnet na siłownię za 200 pkt
- **When:** Wybieram "MultiSport Classic", klikam "Zamów"
- **Then:** Punkty są pobierane z mojego salda (zostaje 300 pkt)
- **And:** Otrzymuję potwierdzenie z instrukcją aktywacji karnetu
- **And:** W historii widzę transakcję

**WF-BEN-001-03: Brak wystarczających punktów (Scenariusz alternatywny)**

- **Given:** Mam 100 punktów, próbuję kupić benefit za 200 pkt
- **When:** Klikam "Zamów"
- **Then:** System wyświetla "Niewystarczająca liczba punktów. Brakuje: 100 pkt"
- **And:** Sugeruje tańsze alternatywy lub możliwość doładowania z własnej kieszeni

---

### 4.6. Moduł Offboardingu

#### WF-OFF-001: Automatyczne Odbieranie Dostępów

**Opis:** System automatycznie dezaktywuje dostępy do wszystkich systemów IT w momencie zakończenia zatrudnienia, poprzez integrację z Active Directory i innymi systemami.

**Historyjka Użytkownika:**
> Jako Administrator IT,  
> chcę aby dostępy odchodzącego pracownika były automatycznie odbierane,  
> abym nie musiał pamiętać o każdym systemie i nie ryzykować wycieku danych.

**Cel Biznesowy:** Zautomatyzowanie procesu odbierania dostępów do systemów IT w 100% przypadków w momencie rozwiązania umowy (redukcja ryzyka wycieku danych).

**Warunki Wstępne:**

- Pracownik ma zakończoną umowę (data końca zatrudnienia)
- Skonfigurowana integracja z SAML i innymi systemami

**Warunki Końcowe:**

- Wszystkie dostępy są odebrane
- IT ma raport z wykonanych akcji
- Konto jest zarchiwizowane (nie usunięte)

**Kryteria Akceptacji:**

**WF-OFF-001-01: Automatyczna dezaktywacja w dniu zakończenia (Scenariusz główny)**

- **Given:** Pracownik Jan Kowalski ma ostatni dzień pracy 31.01.2025
- **When:** Nastaje 31.01.2025, godzina 23:59
- **Then:** System automatycznie: wyłącza konto AD, odbiera dostęp do email, dezaktywuje VPN, odbiera dostępy do systemów wewnętrznych (Jira, Confluence, GitHub)
- **And:** IT Admin otrzymuje raport z listą odebranych dostępów
- **And:** Menedżer otrzymuje powiadomienie "Dostępy Jana Kowalskiego zostały odebrane"

**WF-OFF-001-02: Lista kontrolna offboardingu (Scenariusz główny)**

- **Given:** Jestem HR Adminem, pracownik złożył wypowiedzenie
- **When:** Rozpoczynam proces offboardingu
- **Then:** System generuje checklistę: zwrot sprzętu, przekazanie obowiązków, rozmowa exit interview, dostępy do odebrania
- **And:** Mogę przypisać zadania do odpowiednich osób (IT, menedżer, HR)
- **And:** System śledzi wykonanie i przypomina o zaległych zadaniach

**WF-OFF-001-03: Exit interview (Scenariusz główny)**

- **Given:** Pracownik jest w okresie wypowiedzenia
- **When:** HR wysyła zaproszenie na exit interview
- **Then:** Pracownik może wypełnić ankietę online lub umówić się na rozmowę
- **And:** Odpowiedzi są zapisywane anonimowo (chyba że pracownik zgodzi się na jawność)
- **And:** HR widzi zagregowane wyniki exit interviews w analityce

---

#### WF-OFF-002: Program Alumni

**Opis:** Portal dla byłych pracowników umożliwiający utrzymanie kontaktu, networking i potencjalny powrót do firmy w przyszłości.

**Historyjka Użytkownika:**
> Jako były pracownik,  
> chcę utrzymać kontakt z firmą i byłymi kolegami,  
> abym mógł wrócić jeśli pojawi się ciekawa okazja.

**Cel Biznesowy:** Konwersja 20% odchodzących pracowników do programu Alumni w celu przyszłej rekrutacji (boomerang hiring).

**Warunki Wstępne:**

- Pracownik zakończył zatrudnienie
- Wyraził zgodę na udział w programie Alumni

**Warunki Końcowe:**

- Były pracownik ma konto Alumni
- Może przeglądać oferty i utrzymywać kontakt

**Kryteria Akceptacji:**

**WF-OFF-002-01: Dołączenie do programu Alumni (Scenariusz główny)**

- **Given:** Kończę pracę w firmie, podczas offboardingu HR pyta czy chcę dołączyć do Alumni
- **When:** Wyrażam zgodę i podaję prywatny email
- **Then:** Otrzymuję link do aktywacji konta Alumni
- **And:** Moje podstawowe dane (imię, stanowisko, okres zatrudnienia) są zachowane
- **And:** Dane wrażliwe (wynagrodzenie, oceny) są usunięte

**WF-OFF-002-02: Portal Alumni - oferty pracy (Scenariusz główny)**

- **Given:** Jestem w programie Alumni od 6 miesięcy
- **When:** Loguję się do portalu Alumni
- **Then:** Widzę aktualne oferty pracy w firmie z oznaczeniem "Dla Alumni"
- **And:** Mogę aplikować jednym kliknięciem (moje dane są już w systemie)
- **And:** Moja aplikacja jest oznaczona jako "Boomerang" i ma priorytet

---

### 4.7. Priorytetyzacja Wymagań Funkcjonalnych

#### Macierz MoSCoW

| ID | Funkcjonalność | Must | Should | Could | Won't (MVP) |
|----|----------------|------|--------|-------|-------------|
| WF-REK-001 | Automatyczny Screening CV | ✓ | | | |
| WF-REK-002 | Semantic Matching Engine | | ✓ | | |
| WF-REK-003 | Portal Kandydata z tracking | ✓ | | | |
| WF-REK-004 | Giełda Talentów | | | ✓ | |
| WF-REK-005 | System Poleceń Pracowniczych | | ✓ | | |
| WF-REK-006 | Anonimizacja D&I | | | ✓ | |
| WF-ONB-001 | Cyfrowy obieg dokumentów | ✓ | | | |
| WF-ONB-002 | Zgrywalizowany onboarding | | ✓ | | |
| WF-DEV-001 | Platforma LMS | | ✓ | | |
| WF-DEV-002 | System OKR | | | ✓ | |
| WF-DEV-003 | Continuous Feedback | | ✓ | | |
| WF-ANA-001 | Retention AI | | | ✓ | |
| WF-ANA-002 | 9-box Grid | | | ✓ | |
| WF-BEN-001 | Kafeteria benefitowa | | | | ✓ |
| WF-OFF-001 | Automatyczne odbieranie dostępów | ✓ | | | |
| WF-OFF-002 | Program Alumni | | | | ✓ |

#### Uzasadnienie priorytetów

**Must Have (MVP):**

- **Screening CV** - bez tego system nie ma sensu, to core funkcjonalność
- **Portal Kandydata** - kluczowe dla Candidate Experience (cel: cNPS +50)
- **Cyfrowy obieg dokumentów** - bezpośrednio wpływa na cel redukcji czasu kadr o 80%
- **Odbieranie dostępów** - krytyczne dla bezpieczeństwa, zero tolerancji na błędy

**Should Have (v1.1):**

- **Semantic Matching** - zwiększa wartość screeningu, ale wymaga danych do treningu
- **System poleceń** - ważny cel biznesowy, ale firma może funkcjonować bez niego
- **Gamifikowany onboarding** - wpływa na Time-to-Productivity, ale można zacząć od prostszej wersji
- **LMS** - ważne dla rozwoju, ale można początkowo używać zewnętrznych platform
- **Continuous Feedback** - kulturowa zmiana wymaga czasu

**Could Have (v1.2+):**

- **Giełda Talentów** - wymaga dojrzałych danych o kompetencjach
- **Anonimizacja D&I** - wartościowe, ale nie blokuje rekrutacji
- **OKR** - wymaga buy-in od zarządu i zmiany kultury
- **Retention AI** - wymaga min. 12 miesięcy danych historycznych
- **9-box Grid** - uzupełnia Retention AI

**Won't Have (poza MVP):**

- **Kafeteria benefitowa** - wymaga integracji z wieloma dostawcami
- **Program Alumni** - nice-to-have, niski priorytet biznesowy

---

## 5. Atrybuty Jakościowe

### 5.1. Jakość Wykonania (Runtime Quality)

#### Wydajność (Performance)

| ID | Wymaganie | Metryka | Wartość docelowa | Warunki pomiaru |
|----|-----------|---------|------------------|-----------------|
| **WNF-WYD-01** | Czas odpowiedzi - lista ofert | Response time (P95) | ≤ 1.5 sekundy | 200 jednoczesnych użytkowników, 10 000 ofert w bazie |
| **WNF-WYD-02** | Czas odpowiedzi - wyszukiwanie | Response time (P95) | ≤ 2 sekundy | Wyszukiwanie pełnotekstowe + filtry, 200 użytkowników |
| **WNF-WYD-03** | Czas parsowania CV | Processing time | ≤ 10 sekund | Plik PDF do 5MB, standardowa struktura |
| **WNF-WYD-04** | Czas obliczenia matchingu | Processing time | ≤ 3 sekundy | Kandydat vs. 1 oferta, pełny matching semantyczny |
| **WNF-WYD-05** | Czas ładowania dashboardu | Time to Interactive | ≤ 3 sekundy | Dashboard analityczny z 10 widgetami |
| **WNF-WYD-06** | Przepustowość API | Requests/second | ≥ 500 req/s | Endpoint listy ofert, peak load |

#### Dostępność (Availability)

| ID | Wymaganie | Metryka | Wartość docelowa | Uwagi |
|----|-----------|---------|------------------|-------|
| **WNF-DOST-01** | Dostępność systemu | Uptime | ≥ 99.5% rocznie | ~43h niedostępności/rok, excluding planowane okna |
| **WNF-DOST-02** | Planowane okna serwisowe | Maintenance window | Max 4h/miesiąc | Nocą (01:00-05:00), z 48h wyprzedzeniem |
| **WNF-DOST-03** | Czas odtworzenia po awarii | RTO (Recovery Time Objective) | ≤ 4 godziny | Od wykrycia do przywrócenia usługi |
| **WNF-DOST-04** | Maksymalna utrata danych | RPO (Recovery Point Objective) | ≤ 1 godzina | Backup co godzinę |

#### Bezpieczeństwo (Security)

| ID | Wymaganie | Opis | Weryfikacja |
|----|-----------|------|-------------|
| **WNF-BEZ-01** | Hashowanie haseł | Hasła muszą być hashowane z użyciem bcrypt (cost factor ≥ 12) lub Argon2 | Code review, test jednostkowy |
| **WNF-BEZ-02** | Sesje użytkowników | Sesja wygasa po 30 minutach bezczynności, max 8h aktywna sesja | Test manualny |
| **WNF-BEZ-03** | Szyfrowanie w tranzycie | Cała komunikacja przez HTTPS/TLS 1.3 | SSL Labs test (ocena A+) |
| **WNF-BEZ-04** | Szyfrowanie danych wrażliwych | Dane osobowe szyfrowane AES-256 w spoczynku | Audyt bazy danych |
| **WNF-BEZ-05** | Ochrona przed OWASP Top 10 | System musi być odporny na: SQL Injection, XSS, CSRF, Broken Auth | Testy penetracyjne (OWASP ZAP) |
| **WNF-BEZ-06** | Logowanie zdarzeń bezpieczeństwa | Każde logowanie, zmiana uprawnień, dostęp do danych wrażliwych musi być logowane | Audit log review |
| **WNF-BEZ-07** | Rate limiting | API musi mieć rate limiting: 100 req/min dla niezalogowanych, 1000 req/min dla zalogowanych | Test obciążeniowy |
| **WNF-BEZ-08** | Zarządzanie tokenami | JWT z krótkim czasem życia (15 min), refresh token (7 dni), możliwość revoke | Test integracyjny |

#### Zgodność z RODO (GDPR Compliance)

| ID | Wymaganie | Opis | Weryfikacja |
|----|-----------|------|-------------|
| **WNF-RODO-01** | Prawo do usunięcia | Użytkownik może zażądać usunięcia wszystkich swoich danych w ciągu 72h | Test E2E, procedura |
| **WNF-RODO-02** | Prawo do eksportu | Użytkownik może pobrać wszystkie swoje dane w formacie JSON/CSV | Test funkcjonalny |
| **WNF-RODO-03** | Retencja danych kandydatów | Dane kandydatów automatycznie usuwane po 24 miesiącach od ostatniej aktywności (lub wcześniej na żądanie) | Cron job, test integracyjny |
| **WNF-RODO-04** | Zgody na przetwarzanie | System musi zbierać i przechowywać explicit consent z timestampem i wersją polityki | Audit trail |
| **WNF-RODO-05** | Minimalizacja danych | System zbiera tylko dane niezbędne do realizacji celu (lista w dokumentacji) | Data mapping review |

#### Skalowalność (Scalability)

| ID | Wymaganie | Metryka | Wartość docelowa | Uwagi |
|----|-----------|---------|------------------|-------|
| **WNF-SKAL-01** | Użytkownicy jednoczesni | Concurrent sessions | ≥ 5000 | Bez degradacji wydajności (WNF-WYD-01 nadal spełnione) |
| **WNF-SKAL-02** | Skalowalność horyzontalna | Scale-out | Auto-scaling 2-10 instancji | Na podstawie CPU > 70% przez 5 min |
| **WNF-SKAL-03** | Skalowalność bazy danych | Read replicas | ≥ 2 repliki | Dla operacji odczytu (lista ofert, wyszukiwanie) |
| **WNF-SKAL-04** | Rozmiar bazy danych | Data volume | Obsługa 1M kandydatów, 100k ofert | Bez degradacji wydajności |

### 5.2. Jakość Projektu (Design Quality)

#### Modyfikowalność (Modifiability)

| ID | Wymaganie | Opis | Weryfikacja |
|----|-----------|------|-------------|
| **WNF-MOD-01** | Architektura modułowa | Każdy moduł (Rekrutacja, Onboarding, Rozwój, Analityka, Offboarding) jest niezależnym bounded context | Architecture review |
| **WNF-MOD-02** | Pluginy integracyjne | Dodanie nowej integracji (np. nowy kalendarz) nie wymaga modyfikacji core code | Adapter pattern, code review |
| **WNF-MOD-03** | Feature flags | Nowe funkcjonalności można włączać/wyłączać per tenant bez deploymentu | Test konfiguracji |
| **WNF-MOD-04** | Konfigurowalność workflow | Workflow rekrutacyjny (etapy, statusy) konfigurowalne przez HR bez deweloperów | Test UI konfiguracji |

#### Testowalność (Testability)

| ID | Wymaganie | Metryka | Wartość docelowa |
|----|-----------|---------|------------------|
| **WNF-TEST-01** | Pokrycie testami jednostkowymi | Code coverage | ≥ 80% dla logiki biznesowej |
| **WNF-TEST-02** | Pokrycie testami integracyjnymi | API endpoints coverage | 100% krytycznych ścieżek |
| **WNF-TEST-03** | Testy E2E | Critical user journeys | 100% (aplikowanie, onboarding, feedback) |
| **WNF-TEST-04** | Czas wykonania testów | CI pipeline duration | ≤ 15 minut (unit + integration) |

#### Przenośność (Portability)

| ID | Wymaganie | Opis | Weryfikacja |
|----|-----------|------|-------------|
| **WNF-PRZEN-01** | Konteneryzacja | Cała aplikacja uruchamialna przez `docker-compose up` | Test na świeżej maszynie |
| **WNF-PRZEN-02** | Cloud-agnostic | Brak vendor lock-in (AWS/GCP/Azure) dla core funkcjonalności | Architecture review |
| **WNF-PRZEN-03** | Wsparcie przeglądarek | Chrome, Firefox, Safari, Edge (ostatnie 2 wersje) | Cross-browser testing |
| **WNF-PRZEN-04** | Responsywność | Pełna funkcjonalność na desktop, tablet, mobile | Responsive testing |

#### Użyteczność (Usability)

| ID | Wymaganie | Metryka | Wartość docelowa |
|----|-----------|---------|------------------|
| **WNF-UZ-01** | Onboarding użytkownika | Time to first task completion | ≤ 5 minut bez szkolenia (kandydat) |
| **WNF-UZ-02** | Dostępność WCAG | WCAG 2.1 compliance | Poziom AA |
| **WNF-UZ-03** | Satysfakcja użytkowników | System Usability Scale (SUS) | ≥ 75 punktów |
| **WNF-UZ-04** | Czas wykonania zadania | Time on task - złożenie aplikacji | ≤ 3 minuty (z gotowym CV) |

#### Niezawodność (Reliability)

| ID | Wymaganie | Metryka | Wartość docelowa |
|----|-----------|---------|------------------|
| **WNF-NIEZ-01** | Błędy użytkownika | Error rate | ≤ 0.1% requestów kończy się błędem 5xx |
| **WNF-NIEZ-02** | Transakcje krytyczne | Transaction success rate | 99.99% (podpisywanie umów, zmiana statusu) |
| **WNF-NIEZ-03** | Spójność danych | Data integrity | Zero utraty danych w transakcjach |

### 5.3. Priorytetyzacja Atrybutów Jakościowych

| Priorytet | Atrybut | Uzasadnienie |
|-----------|---------|--------------|
| **1 (Krytyczny)** | Bezpieczeństwo (WNF-BEZ-*) | Dane osobowe, RODO - brak kompromisów |
| **2 (Krytyczny)** | RODO Compliance (WNF-RODO-*) | Wymóg prawny, kary do 4% obrotu |
| **3 (Wysoki)** | Dostępność (WNF-DOST-*) | System musi działać w godzinach pracy |
| **4 (Wysoki)** | Wydajność (WNF-WYD-*) | Wpływa na Candidate Experience (cel: cNPS +50) |
| **5 (Średni)** | Użyteczność (WNF-UZ-*) | Kluczowe dla adopcji, ale można iterować |
| **6 (Średni)** | Skalowalność (WNF-SKAL-*) | Ważne dla wzrostu, ale MVP może mieć limity |
| **7 (Niski)** | Modyfikowalność (WNF-MOD-*) | Inwestycja w przyszłość, nie blokuje MVP |
| **8 (Niski)** | Testowalność (WNF-TEST-*) | Ważne, ale coverage można budować iteracyjnie |

## 6. Odkrywanie i Analiza Wymagań

### 6.1. Analiza Porównawcza (Benchmarking)

#### Krok 1: Identyfikacja Konkurencji i Wzorców

Zidentyfikowaliśmy następujące podmioty rozwiązujące podobne problemy:

**Konkurencja bezpośrednia (kompleksowe systemy HR):**

| System | Opis | Rynek docelowy |
|--------|------|----------------|
| **Workday HCM** | Lider rynku enterprise HR, pełen cykl życia pracownika | Duże korporacje (5000+ pracowników) |
| **SAP SuccessFactors** | Moduły rekrutacji, onboardingu, rozwoju, analityki | Enterprise, mid-market |
| **BambooHR** | HR dla SMB, przyjazny UX | Małe i średnie firmy (do 1000 pracowników) |
| **Personio** | Europejski HR dla SMB, silny w DACH | SMB w Europie |

**Konkurencja pośrednia (specjaliści w poszczególnych obszarach):**

| System | Specjalizacja | Mocne strony |
|--------|---------------|--------------|
| **Greenhouse** | ATS (rekrutacja) | Świetny UX, integracje, structured hiring |
| **Lever** | ATS + CRM kandydatów | Nurturing kandydatów, employer branding |
| **Lattice** | Performance management, OKR, feedback | Continuous feedback, 1:1s, engagement |
| **15Five** | Feedback i engagement | Pulse surveys, recognition |
| **LinkedIn Recruiter** | Sourcing kandydatów | Dostęp do bazy kandydatów |

**Wzorce funkcjonalne (inspiracje z innych domen):**

| System | Funkcja do zaadaptowania |
|--------|--------------------------|
| **Uber** | Real-time tracking statusu |
| **Duolingo** | Gamifikacja onboardingu |
| **Spotify** | Personalizowane rekomendacje (szkolenia) |
| **Amazon** | One-click apply |

#### Krok 2: Kryteria Oceny

Ocenialiśmy konkurencję w skali 1-5 (1=słabo, 5=doskonale) w następujących kategoriach:

**Tabela porównawcza:**

| Kryterium | Workday | SAP SF | BambooHR | Personio | Greenhouse | Lattice | HRflow (cel) |
|-----------|---------|--------|----------|----------|------------|---------|--------------|
| **FUNKCJONALNOŚĆ** | | | | | | | |
| Rekrutacja (ATS) | 4 | 4 | 3 | 3 | 5 | 2 | 4 |
| Onboarding | 4 | 4 | 4 | 4 | 2 | 2 | 5 |
| Performance/Feedback | 4 | 4 | 2 | 3 | 1 | 5 | 4 |
| Analityka predykcyjna | 3 | 4 | 1 | 2 | 2 | 3 | 4 |
| LMS/Rozwój | 4 | 5 | 1 | 2 | 1 | 3 | 4 |
| Integracje | 5 | 5 | 4 | 4 | 5 | 4 | 3 |
| **UX** | | | | | | | |
| Prostota użycia | 2 | 2 | 5 | 4 | 4 | 5 | 5 |
| Mobile experience | 3 | 3 | 4 | 4 | 3 | 5 | 4 |
| Candidate Experience | 3 | 2 | 3 | 3 | 5 | - | 5 |
| **MODEL BIZNESOWY** | | | | | | | |
| Cena (dostępność dla SMB) | 1 | 1 | 4 | 4 | 3 | 3 | 5 |
| Time to value | 1 | 1 | 4 | 3 | 4 | 4 | 4 |
| **TECHNOLOGIA** | | | | | | | |
| AI/ML capabilities | 4 | 4 | 1 | 2 | 3 | 3 | 4 |
| API/Extensibility | 4 | 3 | 3 | 3 | 5 | 4 | 4 |
| RODO compliance | 4 | 4 | 4 | 5 | 4 | 4 | 5 |

#### Krok 3: Synteza Wyników

**Co konkurencja robi dobrze:**

1. **Greenhouse** - najlepszy Candidate Experience
   - Przejrzysty portal kandydata
   - Structured hiring (scorecards, interview kits)
   - Integracja z 400+ narzędziami
   - **Wniosek dla HRflow:** Priorytetyzujemy Portal Kandydata (WF-REK-003)

2. **Lattice** - lider w continuous feedback
   - Prosty UX do dawania feedbacku
   - Integracja ze Slackiem
   - Pulse surveys
   - **Wniosek dla HRflow:** Implementujemy integrację Slack/Teams (WF-DEV-003-04)

3. **Workday/SAP** - zaawansowana analityka
   - Predykcja rotacji
   - Dashboardy dla zarządu
   - **Wniosek dla HRflow:** Retention AI jako differentiator (WF-ANA-001)

4. **BambooHR** - prostota
   - Intuicyjny interfejs
   - Szybkie wdrożenie
   - **Wniosek dla HRflow:** UX jako priorytet, WCAG compliance

**Słabe punkty konkurencji (nasze szanse):**

| Słaby punkt | Kogo dotyczy | Nasza odpowiedź |
|-------------|--------------|-----------------|
| Brak gamifikacji onboardingu | Wszyscy | WF-ONB-002 - zgrywalizowany moduł wdrożeniowy |
| Semantic matching tylko w enterprise | SMB bez dostępu | WF-REK-002 - demokratyzujemy AI matching |
| Drogi, długie wdrożenie | Workday, SAP | Docker-compose deployment, Time to Value < 1 tydzień |
| Słaba rekrutacja wewnętrzna | Większość | WF-REK-004 - Giełda Talentów |
| Brak real-time tracking dla kandydatów | Większość ATS | WF-REK-003 - Portal Kandydata z live updates |

**Unikalne funkcje konkurencji do rozważenia:**

| Funkcja | System | Ocena |
|---------|--------|-------|
| Video interviews | Greenhouse, Lever | Rozważamy w v2 |
| Skills assessment | TestGorilla (integracja) | Integracja, nie build |
| Background checks | Checkr (integracja) | Integracja |
| Compensation benchmarking | Lattice, Workday | Could Have, dane zewnętrzne |

#### Wnioski z analizy - wpływ na wymagania

Na podstawie analizy porównawczej podjęliśmy następujące decyzje:

**Dodane/wzmocnione wymagania:**

| Wymaganie | Źródło inspiracji | Zmiana |
|-----------|-------------------|--------|
| WF-REK-003 (Portal Kandydata) | Greenhouse | Podwyższony priorytet do Must Have |
| WF-DEV-003-04 (Integracja Slack) | Lattice | Dodany scenariusz |
| WF-ONB-002 (Gamifikacja) | Duolingo pattern | Rozbudowany o system XP i badge'y |
| WNF-UZ-04 (Time on task ≤3min) | Amazon one-click | Dodana metryka |

**Świadomie pominięte funkcje:**

| Funkcja | Powód pominięcia |
|---------|------------------|
| Video interviews (built-in) | Integracja z Zoom/Teams wystarczy, nie budujemy video infra |
| Payroll | Poza zakresem, integracja z dedykowanymi systemami |
| Time tracking | Zbyt wiele komplikacji prawnych, osobny rynek |

**Nasza unikalna propozycja wartości:**

> *"HRflow to pierwszy system HR dla firm 100-1000 pracowników, który łączy inteligentne dopasowanie kandydatów (AI Matching), gamifikowany onboarding i predykcyjną analitykę retencji - funkcje dotąd dostępne tylko w drogich rozwiązaniach enterprise - w przystępnej cenie i z wdrożeniem w tydzień."*

## Dodatki

### Dodatek A: Modele Analityczne

#### Diagram Przypadków Użycia

```
┌─────────────────────────────────────────────────────────────────────────────────┐
│                                    HRflow                                       │
│                                                                                 │
│  ┌─────────────────────────────────────────────────────────────────────────────┐│
│  │                           MODUŁ REKRUTACJI                                  ││
│  │                                                                             ││
│  │    ┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐        ││
│  │    │ Przeglądaj      │    │ Aplikuj na      │    │ Śledź status    │        ││
│  │    │ oferty pracy    │    │ stanowisko      │    │ aplikacji       │        ││
│  │    └────────┬────────┘    └────────┬────────┘    └────────┬────────┘        ││
│  │             │                      │                      │                 ││
│  │             └──────────────────────┼──────────────────────┘                 ││
│  │                                    │                                        ││
│  │                              ┌─────┴─────┐                                  ││
│  │                              │ KANDYDAT  │                                  ││
│  │                              └───────────┘                                  ││
│  │                                                                             ││
│  │    ┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐        ││
│  │    │ Publikuj        │    │ Oceniaj         │    │ Zarządzaj       │        ││
│  │    │ oferty          │    │ kandydatów      │    │ procesem        │        ││
│  │    └────────┬────────┘    └────────┬────────┘    └────────┬────────┘        ││
│  │             │                      │                      │                 ││
│  │             └──────────────────────┼──────────────────────┘                 ││
│  │                                    │                                        ││
│  │                              ┌─────┴─────┐                                  ││
│  │                              │ REKRUTER  │                                  ││
│  │                              └───────────┘                                  ││
│  │                                                                             ││
│  │    ┌─────────────────┐                         ┌─────────────────┐          ││
│  │    │ Poleć           │                         │ Przeglądaj      │          ││
│  │    │ kandydata       │                         │ Giełdę Talentów │          ││
│  │    └────────┬────────┘                         └────────┬────────┘          ││
│  │             └────────────────┬──────────────────────────┘                   ││
│  │                              │                                              ││
│  │                        ┌─────┴─────┐                                        ││
│  │                        │ PRACOWNIK │                                        ││
│  │                        └───────────┘                                        ││
│  └─────────────────────────────────────────────────────────────────────────────┘│
│                                                                                 │
│  ┌─────────────────────────────────────────────────────────────────────────────┐│
│  │                           MODUŁ ONBOARDINGU                                 ││
│  │                                                                             ││
│  │    ┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐        ││
│  │    │ Podpisz         │    │ Wykonaj         │    │ Ukończ          │        ││
│  │    │ dokumenty       │    │ zadania         │    │ quiz            │        ││
│  │    └────────┬────────┘    └────────┬────────┘    └────────┬────────┘        ││
│  │             │                      │                      │                 ││
│  │             └──────────────────────┼──────────────────────┘                 ││
│  │                                    │                                        ││
│  │                        ┌───────────┴───────────┐                            ││
│  │                        │ NOWY PRACOWNIK        │                            ││
│  │                        └───────────────────────┘                            ││
│  │                                                                             ││
│  │    ┌─────────────────┐    ┌─────────────────┐                               ││
│  │    │ Generuj         │    │ Śledź postępy   │                               ││
│  │    │ umowy           │    │ onboardingu     │                               ││
│  │    └────────┬────────┘    └────────┬────────┘                               ││
│  │             └──────────────────────┘                                        ││
│  │                        │                                                    ││
│  │                  ┌─────┴─────┐                                              ││
│  │                  │ HR ADMIN  │                                              ││
│  │                  └───────────┘                                              ││
│  └─────────────────────────────────────────────────────────────────────────────┘│
│                                                                                 │
│  ┌─────────────────────────────────────────────────────────────────────────────┐│
│  │                           MODUŁ ROZWOJU                                     ││
│  │                                                                             ││
│  │    ┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐        ││
│  │    │ Przeglądaj      │    │ Definiuj        │    │ Wymieniaj       │        ││
│  │    │ szkolenia LMS   │    │ OKR             │    │ feedback        │        ││
│  │    └────────┬────────┘    └────────┬────────┘    └────────┬────────┘        ││
│  │             │                      │                      │                 ││
│  │             └──────────────────────┼──────────────────────┘                 ││
│  │                                    │                                        ││
│  │                        ┌───────────┴───────────┐                            ││
│  │                        │     PRACOWNIK         │                            ││
│  │                        └───────────────────────┘                            ││
│  │                                                                             ││
│  │    ┌─────────────────┐    ┌─────────────────┐                               ││
│  │    │ Oceniaj         │    │ Planuj          │                               ││
│  │    │ zespół (9-box)  │    │ sukcesję        │                               ││
│  │    └────────┬────────┘    └────────┬────────┘                               ││
│  │             └──────────────────────┘                                        ││
│  │                        │                                                    ││
│  │                  ┌─────┴─────┐                                              ││
│  │                  │ MENEDŻER  │                                              ││
│  │                  └───────────┘                                              ││
│  └─────────────────────────────────────────────────────────────────────────────┘│
│                                                                                 │
│  ┌─────────────────────────────────────────────────────────────────────────────┐│
│  │                           MODUŁ ANALITYKI                                   ││
│  │                                                                             ││
│  │    ┌─────────────────┐    ┌─────────────────┐                               ││
│  │    │ Przeglądaj      │    │ Eksportuj       │                               ││
│  │    │ dashboardy      │    │ raporty         │                               ││
│  │    └────────┬────────┘    └────────┬────────┘                               ││
│  │             └──────────────────────┘                                        ││
│  │                        │                                                    ││
│  │              ┌─────────┴─────────┐                                          ││
│  │              │ HR MANAGER/ZARZĄD │                                          ││
│  │              └───────────────────┘                                          ││
│  └─────────────────────────────────────────────────────────────────────────────┘│
│                                                                                 │
│  ┌─────────────────────────────────────────────────────────────────────────────┐│
│  │                           MODUŁ OFFBOARDINGU                                ││
│  │                                                                             ││
│  │    ┌─────────────────┐    ┌─────────────────┐                               ││
│  │    │ Dołącz do       │    │ Przeglądaj      │                               ││
│  │    │ Alumni          │    │ oferty (Alumni) │                               ││
│  │    └────────┬────────┘    └────────┬────────┘                               ││
│  │             └──────────────────────┘                                        ││
│  │                        │                                                    ││
│  │              ┌─────────┴─────────┐                                          ││
│  │              │ BYŁY PRACOWNIK    │                                          ││
│  │              └───────────────────┘                                          ││
│  │                                                                             ││
│  │    ┌─────────────────┐    ┌─────────────────┐                               ││
│  │    │ Zarządzaj       │    │ Odbieraj        │                               ││
│  │    │ checklistą      │    │ dostępy         │                               ││
│  │    └────────┬────────┘    └────────┬────────┘                               ││
│  │             └──────────────────────┘                                        ││
│  │                        │                                                    ││
│  │              ┌─────────┴─────────┐                                          ││
│  │              │ HR ADMIN / IT     │                                          ││
│  │              └───────────────────┘                                          ││
│  └─────────────────────────────────────────────────────────────────────────────┘│
│                                                                                 │
└─────────────────────────────────────────────────────────────────────────────────┘
```

---

### Dodatek B: Persony Użytkowników

#### Persona 1: Anna Wiśniewska - Rekruterka IT

**Dane demograficzne:**

- Wiek: 28 lat
- Stanowisko: IT Recruiter w firmie software house (150 pracowników)
- Doświadczenie: 3 lata w rekrutacji IT
- Lokalizacja: Warszawa

**Zdjęcie:** Młoda kobieta, casual business, często na słuchawkach

**Cytat:**
> *"Każdego dnia przeglądam setki CV. Potrzebuję narzędzia, które odsieje tych, którzy kompletnie nie pasują, ale nie przegapi diamentów ukrytych w niestandardowych CV."*

**Cele i motywacje:**

- Zamykać procesy rekrutacyjne szybciej (presja na Time-to-Hire)
- Dostarczać hiring managerom kandydatów wysokiej jakości
- Budować pozytywne relacje z kandydatami (employer branding)
- Rozwijać się w kierunku HR Business Partner

**Frustracje i bóle:**

- Tonę w CV - 80% to spam lub kompletnie niedopasowani kandydaci
- Koordynacja terminów rozmów to koszmar (ping-pong mailowy)
- Hiring managerowie zmieniają wymagania w trakcie procesu
- Kandydaci narzekają że nie dostają feedbacku (a ja nie mam czasu)
- Nasz ATS to Excel z lat 90-tych

**Zachowania technologiczne:**

- Power user LinkedIn Recruiter
- Używa Calendly do umawiania spotkań (prywatnie)
- Slack do komunikacji wewnętrznej
- Frustracja z firmowego ATS (wolny, nieintuicyjny)

**Scenariusz użycia HRflow:**
Anna zaczyna dzień od sprawdzenia dashboardu - widzi 47 nowych aplikacji na stanowisko Senior Java Developer. System automatycznie posortował je wg dopasowania. Top 10 ma score >80%. Anna przegląda ich profile, widzi że system prawidłowo rozpoznał że "Spring Boot" = "Java". Wybiera 5 kandydatów do rozmowy telefonicznej, klika "Zaproponuj terminy" - system sprawdza kalendarz jej i hiring managera i wysyła kandydatom 3 opcje. Do końca dnia ma zaplanowane 4 rozmowy na następny tydzień. Kandydaci którzy nie przeszli dostają automatyczny, spersonalizowany feedback.

---

#### Persona 2: Marek Nowicki - Nowy Programista (Junior)

**Dane demograficzne:**

- Wiek: 25 lat
- Stanowisko: Junior Backend Developer (właśnie zatrudniony)
- Doświadczenie: 1 rok (bootcamp + staż)
- Lokalizacja: Kraków (praca hybrydowa)

**Zdjęcie:** Młody mężczyzna, hoodie, słuchawki na szyi

**Cytat:**
> *"Pierwszy tydzień w nowej pracy to chaos. Loginy, hasła, dokumenty, spotkania... Chciałbym mieć jedno miejsce, gdzie wszystko jest ogarnięte."*

**Cele i motywacje:**

- Szybko wdrożyć się w projekt i zacząć dowozić wartość
- Nie wyglądać na niekompetentnego przed zespołem
- Nauczyć się stack'u technicznego firmy (nowy dla niego)
- Zdobyć doświadczenie na CV

**Frustracje i bóle:**

- Nie wiem do kogo się zwrócić z pytaniem
- Dokumentacja jest rozproszona (Confluence, Google Docs, README, Slack)
- Nie wiem czy robię postępy - nikt mi nie mówi
- Dużo formalności (NDA, umowa, sprzęt) - gubię się

**Zachowania technologiczne:**

- Digital native - wszystko na telefonie
- Gamifikacja go motywuje (Duolingo streak!)
- Preferuje video tutoriale nad dokumentację tekstową
- Aktywny na Slacku

**Scenariusz użycia HRflow:**
Marek dostaje maila "Witaj w firmie!" z linkiem do HRflow. Loguje się i widzi spersonalizowaną ścieżkę onboardingu "Backend Developer - Tydzień 1". Ma checklistę: podpisz dokumenty (e-podpis, gotowe w 5 min), obejrzyj video o firmie, skonfiguruj środowisko (instrukcja krok po kroku + automatyczna weryfikacja gdy sklonuje repo). Za każde zadanie dostaje XP i odblokuje kolejne. Widzi że jego "buddy" to Senior Dev Adam - może mu napisać bezpośrednio z systemu. Po tygodniu ma 75% ukończenia onboardingu i badge "First PR Merged". Czuje że ma kontrolę nad procesem.

---

#### Persona 3: Katarzyna Mazur - HR Manager

**Dane demograficzne:**

- Wiek: 42 lata
- Stanowisko: HR Manager w firmie produkcyjnej (400 pracowników)
- Doświadczenie: 15 lat w HR
- Lokalizacja: Poznań

**Zdjęcie:** Kobieta w średnim wieku, profesjonalny strój, tablet w ręku

**Cytat:**
> *"Zarząd pyta mnie o rotację, koszty rekrutacji, development pipeline... Zbieranie tych danych z Exceli to koszmar. Potrzebuję jednego źródła prawdy."*

**Cele i motywacje:**

- Zmniejszyć rotację (obecnie 18%, cel: 12%)
- Mieć argumenty liczbowe w rozmowach z zarządem
- Zbudować employer brand firmy
- Rozwinąć zespół HR (ma 4 osoby)

**Frustracje i bóle:**

- Dane są w 10 różnych miejscach (payroll, ATS, Excel, papier)
- Rotacja w produkcji to czarna dziura (nie wiem dlaczego odchodzą)
- Menedżerowie nie prowadzą 1:1 z ludźmi
- Brak budżetu na duże systemy HR (Workday to kosmos)

**Zachowania technologiczne:**

- Poweruser Excel (pivot tables, VLOOKUP)
- Używa PowerBI do raportowania (podstawy)
- Woli spotkania twarzą w twarz niż Slack
- Sceptyczna wobec "AI" - chce zobaczyć konkretne wyniki

**Scenariusz użycia HRflow:**
Katarzyna otwiera dashboard o 8 rano. Widzi alert: "Ryzyko odejścia: 3 pracowników działu utrzymania ruchu w czerwonej strefie (>70%)". Klika w szczegóły - system wskazuje czynniki: brak podwyżki 2 lata, spadek engagement score, ich menedżer ma najniższy rating w firmie. Katarzyna umawia spotkanie z dyrektorem produkcji - pokazuje mu dane z HRflow. Razem planują działania: przegląd wynagrodzeń, szkolenie dla menedżera. Za miesiąc sprawdza - ryzyko spadło do 45%. Ma konkretne dane na board meeting.

---

#### Persona 4: Tomasz Kowalczyk - Menedżer Zespołu

**Dane demograficzne:**

- Wiek: 35 lat
- Stanowisko: Sales Manager (zespół 12 osób)
- Doświadczenie: 8 lat w sprzedaży, 3 lata jako menedżer
- Lokalizacja: Wrocław

**Zdjęcie:** Mężczyzna w koszuli, pewny siebie, telefon przy uchu

**Cytat:**
> *"Chcę wiedzieć, kto w moim zespole ma potencjał na lidera, a kto może odejść. I chcę to wiedzieć zanim będzie za późno."*

**Cele i motywacje:**

- Dowieźć target sprzedażowy zespołu
- Rozwinąć top performerów na liderów
- Zatrzymać najlepszych (konkurencja kusi)
- Mieć czas na strategię, nie tylko gaszenie pożarów

**Frustracje i bóle:**

- Rozmowy rozwojowe z ludźmi to "kiedyś zrobię"
- Nie wiem kto naprawdę jest niezadowolony (dowiaduję się jak składa wypowiedzenie)
- Roczne oceny to fikcja - wypełniam bo muszę
- Feedback od zespołu? "Wszystko ok, szefie"

**Zachowania technologiczne:**

- CRM (Salesforce) to jego drugie biurko
- Smartfon zawsze w ręku
- Lubi dashboardy i wykresy (łatwo pokazać zarządowi)
- Nie ma czasu na skomplikowane systemy

**Scenariusz użycia HRflow:**
Tomek dostaje powiadomienie push w piątek: "Przypomnienie: Weekly check-in z zespołem". Otwiera aplikację mobilną, widzi status OKR każdego handlowca. Kasia ma 120% celu - wysyła jej szybki kudos "Świetna robota z klientem X!". Marek ma tylko 60% - klika "Zaplanuj 1:1" na poniedziałek. W sekcji "Talent Grid" sprawdza - system sugeruje że Kasia jest "High Potential" i powinna dostać leadership track. Przygotowuje się do rozmowy z HR o jej awansie.

---

### Dodatek C: Kwestie do Rozwiązania

Lista pytań i niejasności które pojawiły się w trakcie analizy i wymagają decyzji:

#### Kwestie Biznesowe

| ID | Kwestia | Proponowane rozwiązanie | Status | Właściciel |
|----|---------|-------------------------|--------|------------|
| **KB-01** | Czy wspieramy multi-tenancy (jedna instalacja, wiele firm) czy single-tenant? | Multi-tenant (SaaS model), ale z możliwością dedicated dla enterprise | Do decyzji | Product Owner |
| **KB-02** | Jaki model cenowy? Per user? Per moduł? | Freemium + per active employee/month | Do decyzji | Product Owner |
| **KB-03** | Czy integracja z payroll jest w scope MVP? | NIE - poza scope, integracja w przyszłości | Zdecydowane | Team |
| **KB-04** | Czy system ma wspierać wiele języków od MVP? | MVP: polski + angielski, później więcej | Do decyzji | Product Owner |
| **KB-05** | Jak długo przechowujemy dane nieaktywnych kandydatów? | 24 miesiące (RODO), potem anonimizacja | Zdecydowane | Team |

#### Kwestie Techniczne

| ID | Kwestia | Proponowane rozwiązanie | Status | Właściciel |
|----|---------|-------------------------|--------|------------|
| **KT-01** | Jaki provider e-podpisu? Autenti vs DocuSign vs Signaturit | Autenti (polski, tańszy, RODO) | Do decyzji | Tech Lead |
| **KT-02** | Jak trenować model Semantic Matching bez danych historycznych? | Pre-trained embeddings (BERT) + fine-tuning na publicznych datasetsach | Do prototypu | ML Engineer |
| **KT-03** | Self-hosted Elasticsearch vs managed (Elastic Cloud)? | Managed dla MVP (szybciej), self-hosted jeśli koszty za wysokie | Do decyzji | Tech Lead |
| **KT-04** | Jak obsługiwać integrację z różnymi wersjami SAML? | Abstraction layer + konfigurowalne mapowanie atrybutów | Do implementacji | Backend |
| **KT-05** | Czy model Retention AI wymaga GPU? | CPU wystarczy dla inference, GPU do treningu (sporadycznie) | Zdecydowane | ML Engineer |

#### Kwestie UX/Design

| ID | Kwestia | Proponowane rozwiązanie | Status | Właściciel |
|----|---------|-------------------------|--------|------------|
| **KU-01** | Jak prezentować "ryzyko odejścia" menedżerom - czy to etyczne pokazywać score przy pracowniku? | Pokazujemy trendy zespołowe, indywidualne tylko dla HR z odpowiednimi uprawnieniami | Do konsultacji | UX + HR |
| **KU-02** | Czy gamifikacja onboardingu nie będzie infantylna dla seniorów? | Opcjonalna (można wyłączyć), różne style (XP vs. progress bar) | Do testów A/B | UX |
| **KU-03** | Jak obsłużyć accessibility dla osób niewidomych w drag-and-drop (np. Kanban rekrutacji)? | Alternatywny interfejs listowy, keyboard navigation | Do implementacji | Frontend |

#### Kwestie Prawne

| ID | Kwestia | Proponowane rozwiązanie | Status | Właściciel |
|----|---------|-------------------------|--------|------------|
| **KP-01** | Czy predykcja rotacji na podstawie ML nie narusza RODO (automated decision making)? | Nie jest to automated decision - zawsze człowiek podejmuje decyzję, system tylko sugeruje | Do konsultacji prawnej | Prawnik |
| **KP-02** | Jak obsłużyć prawo do bycia zapomnianym jeśli kandydat był w kilku procesach? | Pełna anonimizacja wszystkich powiązanych rekordów | Do implementacji | Backend |
| **KP-03** | Czy e-podpis kwalifikowany jest wymagany dla umów o pracę? | W Polsce: tak dla umów o pracę, nie dla B2B | Zdecydowane | Prawnik |

---

### Historia zmian dokumentu

| Wersja | Data       | Autor              | Opis zmian                                                     |
|--------|------------|--------------------|----------------------------------------------------------------|
| 0.1    | 2026-01-10 | Adrian Jabłoński   | Inicjalizacja projektu, wstęp i struktura dokumentu            |
| 0.2    | 2026-01-10 | Paweł Gorgolewski  | Wprowadzenie, tabele i ograniczenia projektowe                 |
| 0.3    | 2026-01-11 | Kamil Pierzchała   | Wymagania ogólne i doprecyzowanie SRS                          |
| 0.4    | 2026-01-12 | Łukasz Bartoszek   | Interfejsy zewnętrzne systemu                                  |
| 0.5    | 2026-01-14 | Kamil Pierzchała   | Moduł rekrutacji (wymagania funkcjonalne)                      |
| 0.6    | 2026-01-16 | Paweł Gorgolewski  | Rozszerzenie wymagań funkcjonalnych                            |
| 0.7    | 2026-01-16 | Bartosz Balawender | Analityka HR, benefity, offboarding                            |
| 0.8    | 2026-01-16 | Łukasz Bartoszek   | Atrybuty jakościowe systemu                                    |
| 0.9    | 2026-01-16 | Adrian Jabłoński   | Analiza konkurencyjna i poprawki formatowania                  |
| 1.0    | 2026-01-17 | Bartosz Balawender | Dodatki: diagramy przypadków użycia, persony i kwestie otwarte |

---
