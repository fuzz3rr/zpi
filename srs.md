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

- Automatyczne odbieranie dostępów (integracja z AD/LDAP)
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
| **AD/LDAP**                  | Active Directory / Lightweight Directory Access Protocol                     |
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
| **Zarządzanie dostępami** | Automatyczne odbieranie dostępów przez AD/LDAP  |
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

| Kategoria        | Ograniczenie                           | Uzasadnienie                         |
|------------------|----------------------------------------|--------------------------------------|
| **Backend**      | Python 3.11+ / FastAPI lub Node.js 20+ | Wymagana dobra obsługa ML i async    |
| **Frontend**     | React 18+ / TypeScript                 | Standard rynkowy, duża społeczność   |
| **Baza danych**  | PostgreSQL 15+                         | Wsparcie dla JSON, full-text search  |
| **Cache/Queue**  | Redis                                  | Sesje, kolejki zadań, real-time      |
| **ML/AI**        | Python + scikit-learn / spaCy          | Matching Engine, Retention AI        |
| **Wyszukiwarka** | Elasticsearch                          | Wyszukiwanie semantyczne CV          |
| **Kontenery**    | Docker + Docker Compose                | Deployment, środowiska deweloperskie |
| **Hosting**      | Minimum 8GB RAM, 4 vCPU dla MVP        | Wymagania ML i Elasticsearch         |

#### Ograniczenia organizacyjne

| Kategoria        | Ograniczenie                        | Uwagi                                       |
|------------------|-------------------------------------|---------------------------------------------|
| **Zespół**       | 5-7 deweloperów                     | Ograniczona dostępność (projekt uczelniany) |
| **Czas**         | MVP w 4 miesiące                    | Deadline wynikający z harmonogramu studiów  |
| **Budżet**       | Brak budżetu na płatne usługi       | Tylko open-source i darmowe tiers           |
| **Metodyka**     | Scrum, sprinty 2-tygodniowe         | Wymóg przedmiotu                            |
| **Dokumentacja** | SRS, dokumentacja techniczna w repo | Wymóg oddania projektu                      |
| **Code Review**  | Wymagane PR z min. 1 review         | Jakość kodu                                 |

#### Ograniczenia prawne i środowiskowe

| Kategoria                | Ograniczenie                    | Wpływ na system                               |
|--------------------------|---------------------------------|-----------------------------------------------|
| **RODO (GDPR)**          | Pełna zgodność                  | Szyfrowanie danych, prawo do usunięcia, zgody |
| **RODO - retencja**      | Dane kandydatów max 2 lata      | Automatyczne usuwanie danych                  |
| **RODO - dostęp**        | Prawo dostępu do swoich danych  | Eksport danych użytkownika                    |
| **Kodeks Pracy**         | Zgodność z polskim prawem pracy | Wzory umów, okresy wypowiedzenia              |
| **Podpis elektroniczny** | eIDAS - kwalifikowany podpis    | Integracja z dostawcą podpisu                 |
| **Accessibility**        | WCAG 2.1 AA                     | Dostępność dla osób z niepełnosprawnościami   |
| **Regulacje uczelniane** | Projekt akademicki              | Kod jako własność intelektualna studentów     |

### 2.4. Założenia Projektowe

#### Założenia biznesowe

| ID        | Założenie                                                  | Ryzyko jeśli nieprawdziwe                                        | 
|-----------|------------------------------------------------------------|------------------------------------------------------------------|
| **ZB-01** | Firma docelowa zatrudnia 100-1000 pracowników              | Za mała firma = zbędne funkcje; za duża = problemy wydajnościowe |
| **ZB-02** | Istnieje dział HR z min. 2 osobami                         | Brak HR = brak użytkowników systemu                              |
| **ZB-03** | Firma prowadzi aktywną rekrutację (min. 5 wakatów/miesiąc) | Brak rekrutacji = moduł nieużywany                               |
| **ZB-04** | Pracownicy mają dostęp do komputera/smartfona              | Brak dostępu = brak adopcji                                      |
| **ZB-05** | Firma ma już podstawowe systemy IT (email, AD)             | Brak = problemy z integracją                                     |

#### Założenia techniczne

| ID        | Założenie | Ryzyko jeśli nieprawdziwe |
|-----------|------------------------------------------------------------------------------------------------------|-----------------------------------------|
| **ZT-01** | Użytkownicy korzystają z nowoczesnych przeglądarek (Chrome, Firefox, Edge - ostatnie 2 wersje)       | Stare przeglądarki = problemy z UI      |
| **ZT-02** | Dostępne stabilne łącze internetowe min. 10 Mbps                                                     | Wolne łącze = timeout przy uploadzie CV |
| **ZT-03** | CV są w formatach PDF/DOCX/DOC                                                                       | Inne formaty = błędy parsowania         |
| **ZT-04** | Dostępna integracja OAuth2 z firmowym IdP                                                            | Brak = osobne loginy, security risk     |
| **ZT-05** | Elasticsearch dostępny jako managed service lub self-hosted                                          | Brak = brak wyszukiwania semantycznego  |

#### Założenia dotyczące użytkowników

| ID        | Założenie                                               | Ryzyko jeśli nieprawdziwe                  |
|-----------|---------------------------------------------------------|--------------------------------------------|
| **ZU-01** | HR i menedżerowie przejdą szkolenie z systemu (min. 2h) | Brak szkolenia = niska adopcja             |
| **ZU-02** | Kandydaci są przyzwyczajeni do portali rekrutacyjnych   | Nieintuicyjny UX = porzucone aplikacje     |
| **ZU-03** | Pracownicy będą aktywnie korzystać z systemu feedbacku  | Brak adopcji = puste metryki               |
| **ZU-04** | Menedżerowie będą prowadzić regularne 1:1               | Brak spotkań = nieaktualne dane w systemie |

#### Zależności zewnętrzne

| ID        | Zależność                                  | Alternatywa                           |
|-----------|--------------------------------------------|---------------------------------------|
| **ZZ-01** | API LinkedIn do publikacji ofert           | Ręczna publikacja                     |
| **ZZ-02** | Dostawca e-podpisu (np. Autenti, DocuSign) | Podpis offline + skan                 |
| **ZZ-03** | Serwer SMTP do wysyłki maili               | Zewnętrzny serwis (SendGrid, Mailgun) |
| **ZZ-04** | Active Directory / LDAP firmy              | Lokalne konta w systemie              |
| **ZZ-05** | System kalendarzowy (Google/Outlook)       | Manualnie uzgadniane terminy          |

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

**Ekran 1: Lista ofert pracy (widok kandydata)**

```
┌─────────────────────────────────────────────────────────────────┐
│  🔍 [Szukaj stanowiska...]        📍 Lokalizacja ▼   🎯 Filtruj │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  ┌─────────────────────────────────────────────────────────┐   │
│  │ 💼 Senior Python Developer              📍 Warszawa     │   │
│  │    TechCorp Sp. z o.o.                  💰 18-24k PLN  │   │
│  │    Python • FastAPI • PostgreSQL        📅 do 15.01    │   │
│  │    [Zobacz szczegóły]              [⭐ Zapisz]        │   │
│  └─────────────────────────────────────────────────────────┘   │
│                                                                 │
│  ┌─────────────────────────────────────────────────────────┐   │
│  │ 💼 HR Business Partner                  📍 Kraków       │   │
│  │    BigFactory S.A.                      💰 12-15k PLN  │   │
│  │    HR • Rekrutacja • HRIS               📅 do 20.01    │   │
│  │    [Zobacz szczegóły]              [⭐ Zapisz]        │   │
│  └─────────────────────────────────────────────────────────┘   │
│                                                                 │
│  ┌─────────────────────────────────────────────────────────┐   │
│  │ 💼 Junior Frontend Developer            📍 Remote       │   │
│  │    StartupXYZ                           💰 8-12k PLN   │   │
│  │    React • TypeScript • CSS             📅 do 10.01    │   │
│  │    [Zobacz szczegóły]              [⭐ Zapisz]        │   │
│  └─────────────────────────────────────────────────────────┘   │
│                                                                 │
│  [Pokaż więcej ofert...]                                       │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

**Ekran 2: Szczegóły oferty**

```
┌─────────────────────────────────────────────────────────────────┐
│  ← Wróć do listy                                               │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  💼 Senior Python Developer                                    │
│  ═══════════════════════════════════════                       │
│                                                                 │
│  TechCorp Sp. z o.o.    📍 Warszawa (hybrydowo)               │
│  💰 18 000 - 24 000 PLN netto (B2B)                           │
│  📅 Rekrutacja do: 15 stycznia 2025                           │
│                                                                 │
│  ┌─────────────────────────────────────────────────────────┐   │
│  │ Dopasowanie do Twojego profilu: ████████████░░ 78%      │   │
│  │ ✓ Python (Twój poziom: Expert)                          │   │
│  │ ✓ FastAPI (Twój poziom: Mid)                            │   │
│  │ ⚠ Kubernetes (brak w profilu)                           │   │
│  └─────────────────────────────────────────────────────────┘   │
│                                                                 │
│  📋 OPIS STANOWISKA                                            │
│  Szukamy doświadczonego Python Developera do zespołu          │
│  platformy płatniczej. Będziesz pracować nad...               │
│  [Pokaż więcej...]                                             │
│                                                                 │
│  🎯 WYMAGANIA                                                   │
│  • 5+ lat doświadczenia z Python                              │
│  • Znajomość FastAPI lub Django                                │
│  • Doświadczenie z PostgreSQL                                  │
│  • Mile widziane: Kubernetes, AWS                              │
│                                                                 │
│  🎁 OFERUJEMY                                                   │
│  • Praca hybrydowa (2 dni w biurze)                            │
│  • Budżet szkoleniowy 5000 PLN/rok                             │
│  • Prywatna opieka medyczna                                    │
│                                                                 │
│  ┌───────────────────────────────────────────────────────────┐ │
│  │  [     📤 APLIKUJ TERAZ     ]    [⭐ Zapisz] [📤 Udostępnij] │ │
│  └───────────────────────────────────────────────────────────┘ │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

**Ekran 3: Formularz aplikacji**

```
┌─────────────────────────────────────────────────────────────────┐
│  ← Wróć do oferty                                              │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  📤 Aplikujesz na: Senior Python Developer                     │
│     TechCorp Sp. z o.o.                                        │
│  ═══════════════════════════════════════                       │
│                                                                 │
│  📄 TWOJE CV                                                    │
│  ┌─────────────────────────────────────────────────────────┐   │
│  │ ✓ Jan_Kowalski_CV_2024.pdf                              │   │
│  │   Dodane: 10.12.2024    [Zmień CV]                      │   │
│  └─────────────────────────────────────────────────────────┘   │
│                                                                 │
│  📝 LIST MOTYWACYJNY (opcjonalnie)                             │
│  ┌─────────────────────────────────────────────────────────┐   │
│  │                                                          │   │
│  │  Napisz kilka słów o sobie i dlaczego                   │   │
│  │  interesujesz się tą ofertą...                          │   │
│  │                                                          │   │
│  │                                                          │   │
│  └─────────────────────────────────────────────────────────┘   │
│                                             0/2000 znaków      │
│                                                                 │
│  💰 OCZEKIWANIA FINANSOWE                                      │
│  [    15000    ] PLN netto/mies.                               │
│                                                                 │
│  📅 DOSTĘPNOŚĆ                                                  │
│  ○ Natychmiast                                                 │
│  ● 2 tygodnie                                                  │
│  ○ 1 miesiąc                                                   │
│  ○ Inna: [________]                                            │
│                                                                 │
│  ☑ Wyrażam zgodę na przetwarzanie danych osobowych...         │
│  ☑ Chcę otrzymywać podobne oferty pracy                       │
│                                                                 │
│  ┌───────────────────────────────────────────────────────────┐ │
│  │         [     ✓ WYŚLIJ APLIKACJĘ     ]                   │ │
│  └───────────────────────────────────────────────────────────┘ │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

**Ekran 4: Potwierdzenie i status**

```
┌─────────────────────────────────────────────────────────────────┐
│                                                                 │
│                         ✓                                       │
│                                                                 │
│              Twoja aplikacja została wysłana!                  │
│                                                                 │
│  ┌─────────────────────────────────────────────────────────┐   │
│  │                                                          │   │
│  │  Senior Python Developer @ TechCorp                      │   │
│  │                                                          │   │
│  │  Status: ● WYSŁANA                                       │   │
│  │  Data aplikacji: 12.12.2024, 14:32                       │   │
│  │                                                          │   │
│  │  ═══════════════════════════════════════                 │   │
│  │  ● Wysłana  →  ○ W ocenie  →  ○ Rozmowa  →  ○ Decyzja   │   │
│  │  ═══════════════════════════════════════                 │   │
│  │                                                          │   │
│  │  Rekruter skontaktuje się z Tobą w ciągu 5 dni          │   │
│  │  roboczych. Włącz powiadomienia, żeby nie przegapić     │   │
│  │  wiadomości!                                             │   │
│  │                                                          │   │
│  └─────────────────────────────────────────────────────────┘   │
│                                                                 │
│  [🔔 Włącz powiadomienia]    [📋 Moje aplikacje]    [🏠 Start] │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

### 3.2. Interfejsy Programowe (API)

#### Integracje zewnętrzne

System HRflow integruje się z następującymi systemami zewnętrznymi:

**Integracje wymagane (MVP):**

| System | Typ integracji | Cel | Protokół |
|--------|----------------|-----|----------|
| **Active Directory / LDAP** | Outbound | SSO, zarządzanie dostępami | LDAP/LDAPS |
| **SMTP Server** | Outbound | Wysyłka powiadomień email | SMTP/TLS |
| **Google Calendar / Outlook 365** | Bidirectional | Umawianie spotkań rekrutacyjnych | OAuth2 + REST API |
| **Dostawca e-podpisu** | Outbound | Podpisywanie umów | REST API (webhook) |

**Integracje planowane (post-MVP):**

| System | Typ integracji | Cel | Protokół |
|--------|----------------|-----|----------|
| **LinkedIn** | Outbound | Publikacja ofert, import profili | OAuth2 + REST API |
| **Facebook Jobs** | Outbound | Publikacja ofert | REST API |
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
# Konfiguracja LDAP
ldap:
  server: ldap://ad.company.local
  port: 636
  use_ssl: true
  bind_dn: cn=hrflow-service,ou=ServiceAccounts,dc=company,dc=local
  base_dn: ou=Users,dc=company,dc=local
  
  # Mapowanie atrybutów
  attribute_mapping:
    username: sAMAccountName
    email: mail
    first_name: givenName
    last_name: sn
    department: department
    manager: manager

  # Synchronizacja grup
  group_sync:
    enabled: true
    hrflow_admins: CN=HRFlow-Admins,OU=Groups,DC=company,DC=local
    hrflow_managers: CN=HRFlow-Managers,OU=Groups,DC=company,DC=local
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