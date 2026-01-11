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
