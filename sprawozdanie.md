# Sprawozdanie — Zadanie 3: Planowanie Projektu i Symulacja Sprintu (Scrum)

Dokument łączy **Product Backlog + Roadmapę (MVP 3 miesiące)** oraz **plan Sprintu 1 (PoC)**.

---

# HRflow - Roadmapa Projektu (MVP 3 miesiące)

## Oś Czasu Epików

**Okres planowania:** Styczeń 2026 - Kwiecień 2026 (12 tygodni)

---

## Wykres Gantta

![Wykres Gantta - HRflow MVP Roadmapa](images/gantt_chart.png)

---

## Harmonogram szczegółowy

### Moduł Rekrutacji - ATS i Screening CV

**EPIC-1** | Tydzień 1-6 (20.01 - 03.03.2026)

| Tydzień | Daty | Zakres prac |
|---------|------|-------------|
| T1 | 20-24.01.2026 | Parsowanie CV (PDF/DOCX), ekstrakcja danych |
| T2 | 27-31.01.2026 | Scoring dopasowania, obsługa błędów plików |
| T3 | 03-07.02.2026 | Lista kandydatów z rankingiem |
| T4 | 10-14.02.2026 | Tworzenie i publikacja ofert pracy |
| T5 | 17-21.02.2026 | Filtrowanie, wyszukiwanie kandydatów |
| T6 | 24-28.02.2026 | Kanban rekrutacyjny, testy integracyjne |

**Deliverables:**

- ✅ Automatyczny screening CV
- ✅ Scoring dopasowania kandydatów
- ✅ Panel rekrutera

---

### Infrastruktura i Bezpieczeństwo

**EPIC-5** | Tydzień 3-12 (03.02 - 14.04.2026)

| Tydzień | Daty | Zakres prac |
|---------|------|-------------|
| T3 | 03-07.02.2026 | Setup projektu, Baza danych PostgreSQL |
| T4 | 10-14.02.2026 | Autentykacja JWT, RBAC |
| T5 | 17-21.02.2026 | HTTPS/TLS, Rate limiting |
| T6 | 24-28.02.2026 | Szyfrowanie danych (AES-256) |
| T7 | 03-07.03.2026 | Audit logging |
| T8 | 10-14.03.2026 | Mechanizmy RODO (zgody) |
| T9 | 17-21.03.2026 | Eksport i usuwanie danych (RODO) |
| T10 | 24-28.03.2026 | Redis Cache setup |
| T11 | 31.03-04.04.2026 | Elasticsearch config |
| T12 | 07-11.04.2026 | Konteneryzacja, Monitoring (finalizacja) |

**Deliverables:**

- ✅ Bezpieczna infrastruktura zgodna z RODO
- ✅ Audytowalność i monitoring
- ✅ Pełne środowisko produkcyjne

---

### Portal Kandydata

**EPIC-2** | Tydzień 5-9 (17.02 - 17.03.2026)

| Tydzień | Daty | Zakres prac |
|---------|------|-------------|
| T5 | 17-21.02.2026 | Rejestracja i logowanie kandydata |
| T6 | 24-28.02.2026 | Profil kandydata, formularz aplikacji |
| T7 | 03-07.03.2026 | Dashboard "Moje aplikacje" |
| T8 | 10-14.03.2026 | Powiadomienia email + push |
| T9 | 17.03.2026 | Automatyczny feedback (Finish) |

**Deliverables:**

- ✅ Portal kandydata z trackingiem
- ✅ System powiadomień

---

### Cyfrowy Obieg Dokumentów (E-podpis)

**EPIC-3** | Tydzień 7-10 (03.03 - 31.03.2026)

| Tydzień | Daty | Zakres prac |
|---------|------|-------------|
| T7 | 03-07.03.2026 | Integracja z Autenti API |
| T8 | 10-14.03.2026 | Automatyczne generowanie umów |
| T9 | 17-21.03.2026 | Workflow podpisywania |
| T10 | 24-28.03.2026 | Panel HR, Archiwum |

**Deliverables:**

- ✅ E-podpis zintegrowany z Autenti
- ✅ Generator umów

---

### Offboarding

**EPIC-4** | Tydzień 9-12 (17.03 - 14.04.2026)

| Tydzień | Daty | Zakres prac |
|---------|------|-------------|
| T9 | 17-21.03.2026 | Integracja z Active Directory |
| T10 | 24-28.03.2026 | Scheduler dezaktywacji kont |
| T11 | 31.03-04.04.2026 | Checklist offboardingu |
| T12 | 07-11.04.2026 | Exit interview, Raporty |

**Deliverables:**

- ✅ Automatyczne odbieranie dostępów
- ✅ Proces offboardingu

---

## Kamienie milowe (Milestones)

| Data | Milestone | Opis |
|------|-----------|------|
| **03.03.2026** | 🏁 M1: Rekrutacja MVP | Działający ATS ze scoringiem (PoC integrated) |
| **17.03.2026** | 🏁 M2: Portal Kandydata Live | Portal dostępny dla kandydatów |
| **31.03.2026** | 🏁 M3: E-podpis Ready | Cyfrowy obieg umów działający |
| **14.04.2026** | 🏁 M4: Project Complete | Pełna infrastruktura, Offboarding, System gotowy |
---

## Zależności między Epikami

```
                    ┌─────────────────────────────────┐
                    │      🏗️  EPIC-5                 │
                    │  Infrastruktura i Bezpieczeństwo│
                    └───────────────┬─────────────────┘
                                    │
              ┌─────────────────────┼─────────────────────┐
              │                     │                     │
              ▼                     ▼                     ▼
┌─────────────────────┐  ┌─────────────────────┐  ┌─────────────────────┐
│    📋 EPIC-1        │  │    👤 EPIC-2        │  │    🚪 EPIC-4        │
│ Moduł Rekrutacji    │  │  Portal Kandydata   │  │    Offboarding      │
│       ATS           │  │                     │  │                     │
└──────────┬──────────┘  └─────────────────────┘  └─────────────────────┘
           │                       ▲
           │                       │
           └───────────────────────┤
                                   │
                    ┌──────────────┴──────────────┐
                    │       📝 EPIC-3             │
                    │ Cyfrowy Obieg Dokumentów    │
                    └─────────────────────────────┘
```


**Opis zależności:**

- **EPIC-1 (Rekrutacja)** - Startuje jako pierwszy (PoC).
- **EPIC-5 (Infrastruktura)** - Rozwija się równolegle, wspierając kolejne moduły.
- **EPIC-1 → EPIC-2** - Portal Kandydata wymaga ofert z ATS.
- **EPIC-1 → EPIC-3** - Obieg dokumentów wymaga kandydatów z ATS.

---

## Alokacja zespołu

| Rola | Osoba | Główne Epiki |
|------|-------|--------------|
| Tech Lead | Adrian Jabłoński | EPIC-5, EPIC-4 |
| Backend Developer | Paweł Gorgolewski | EPIC-1, EPIC-3 |
| Frontend Developer | Kamil Pierzchała | EPIC-2 |
| Full-stack Developer | Łukasz Bartoszek | EPIC-1, EPIC-2 |
| DevOps/QA | Bartosz Balawender | EPIC-5, wszystkie testy |

---

## Ryzyka i mitygacje

| Ryzyko | Prawdopodobieństwo | Impact | Mitygacja |
|--------|-------------------|--------|-----------|
| Opóźnienie integracji Autenti | Średnie | Wysoki | Wczesne rozpoczęcie negocjacji, alternatywny provider (DocuSign) |
| Problemy z parsowaniem CV | Średnie | Średni | Zbiór testowy 50+ CV, fallback do manual review |
| Integracja AD w różnych środowiskach | Wysokie | Średni | Adapter pattern, środowisko testowe AD |
| Wydajność scoringu ML | Niskie | Średni | Cache Redis, async processing |

---

---

# Backlog Produktu - Szczegóły

## EPIC-1: Moduł Rekrutacji - ATS i Screening CV

**Cel:** Automatyzacja procesu rekrutacyjnego z inteligentnym screeningiem CV i zarządzaniem kandydatami. Skrócenie Time-to-Hire z 45 do 20 dni.

### Historyjki użytkownika

---

#### STORY-1: Parsowanie CV z ekstrakcją danych

| Pole | Wartość |
|------|---------|
| **Tytuł** | Parsowanie CV z ekstrakcją danych |
| **Priorytet** | High |
| **Story Points** | 8 |

**Opis wymagań:**
System automatycznie analizuje przesłane CV (PDF/DOCX), wydobywa kluczowe informacje: dane kontaktowe, doświadczenie zawodowe, umiejętności, wykształcenie. Kandydat może zobaczyć podgląd wyekstrahowanych danych i dokonać korekty.

**User Story:**
> Jako rekruter, chcę aby system automatycznie parsował CV kandydatów, abym nie musiał ręcznie przepisywać danych z dokumentów.

**Kryteria Akceptacji:**

- **Given:** Kandydat przesłał CV w formacie PDF zawierające sekcje: dane kontaktowe, doświadczenie, umiejętności, wykształcenie
- **When:** System przetwarza przesłany plik
- **Then:** W profilu kandydata zapisane są: imię, nazwisko, email, telefon, lista stanowisk z datami, lista umiejętności
- **And:** Czas parsowania nie przekracza 10 sekund
- **And:** Kandydat widzi podgląd wyekstrahowanych danych z możliwością korekty

**Refinement:**

- *Techniczny:* Implementacja parsera PDF/DOCX (biblioteka: PyMuPDF lub python-docx)
- *Techniczny:* Model NLP do ekstrakcji encji (NER) - rozważyć spaCy z modelem pl_core_news_lg
- *Techniczny:* API endpoint POST /api/v1/candidates/cv z obsługą multipart/form-data
- *Techniczny:* Walidacja formatów plików i limitów rozmiaru (max 5MB)
- *Organizacyjny:* Przygotować zestaw testowych CV (min. 50 dokumentów różnych formatów)
- *Organizacyjny:* Zdefiniować mapowanie pól CV na strukturę bazy danych

---

#### STORY-2: Scoring dopasowania kandydata do oferty

| Pole | Wartość |
|------|---------|
| **Tytuł** | Scoring dopasowania kandydata do oferty |
| **Priorytet** | High |
| **Story Points** | 8 |

**Opis wymagań:**
System oblicza score dopasowania (0-100%) kandydata do oferty na podstawie sparsowanego CV i wymagań oferty. Rozbicie na kategorie: umiejętności techniczne, doświadczenie, wykształcenie. Wizualizacja które wymagania kandydat spełnia.

**User Story:**
> Jako rekruter, chcę widzieć procentowe dopasowanie kandydata do oferty, abym mógł szybko priorytetyzować najlepszych kandydatów.

**Kryteria Akceptacji:**

- **Given:** CV kandydata zostało sparsowane, oferta ma zdefiniowane wymagane i opcjonalne kompetencje
- **When:** System oblicza dopasowanie kandydata
- **Then:** Kandydat otrzymuje score 0-100% z rozbiciem na kategorie
- **And:** Rekruter widzi wizualnie które wymagania kandydat spełnia, a których nie

**Refinement:**

- *Techniczny:* Algorytm scoringu z wagami dla różnych kategorii (konfigurowalny)
- *Techniczny:* Endpoint GET /api/v1/candidates/{id}/matching/{job_id}
- *Techniczny:* Cache scorów w Redis (TTL: 1h) dla wydajności
- *Organizacyjny:* Walidacja algorytmu z zespołem HR (warsztaty)

---

#### STORY-3: Obsługa nieobsługiwanych formatów CV

| Pole | Wartość |
|------|---------|
| **Tytuł** | Obsługa nieobsługiwanych formatów CV |
| **Priorytet** | Medium |
| **Story Points** | 3 |

---

#### STORY-4: Obsługa uszkodzonych plików CV

| Pole | Wartość |
|------|---------|
| **Tytuł** | Obsługa uszkodzonych plików CV |
| **Priorytet** | Medium |
| **Story Points** | 3 |

---

#### STORY-5: Lista kandydatów z rankingiem

| Pole | Wartość |
|------|---------|
| **Tytuł** | Lista kandydatów z rankingiem |
| **Priorytet** | High |
| **Story Points** | 5 |

---

#### STORY-6: Tworzenie i publikacja ofert pracy

| Pole | Wartość |
|------|---------|
| **Tytuł** | Tworzenie i publikacja ofert pracy |
| **Priorytet** | High |
| **Story Points** | 8 |

**Opis wymagań:**
Rekruter ma możliwość tworzenia nowych ofert pracy za pomocą kreatora. Może zdefiniować: tytuł, poziom stanowiska, widełki płacowe, lokalizację (remote/hybrid/office), opis stanowiska (rich text), oraz wymagane i mile widziane kompetencje (zintegrowane z silnikiem matchingu). Oferta może zostać zapisana jako szkic lub natychmiast opublikowana.

**User Story:**
> Jako rekruter, chcę szybko tworzyć i publikować atrakcyjne wizualnie oferty pracy, aby przyciągnąć najlepszych kandydatów.

**Kryteria Akceptacji:**

- **Given:** Jestem zalogowany jako Rekruter i jestem w kreatorze oferty
- **When:** Wypełniam formularz, definiuję wymagane kompetencje (np. Python > 3 lata) i klikam "Publikuj"
- **Then:** Oferta otrzymuje status 'Opublikowana' i jest widoczna na Portalu Kandydata
- **And:** Generowany jest unikalny link do oferty do udostępniania w social media
- **And:** System podpowiada sugerowane kompetencje na podstawie tytułu stanowiska (np. dla "Python Dev" podpowiada "Django")

**Refinement:**

- *Techniczny:* Tabela `job_offers` z polami JSONB dla elastycznych atrybutów
- *Techniczny:* Integracja z edytorem tekstu WYSIWYG (np. Quill.js lub TipTap)
- *Techniczny:* Endpoint POST /api/v1/jobs z walidacją danych
- *Techniczny:* Integracja z modułem kompetencji (współdzielony słownik)
- *Organizacyjny:* Zdefiniowanie szablonów ofert dla najczęstszych stanowisk
- *Organizacyjny:* Polityka widełek płacowych (czy są obowiązkowe?)

---

#### STORY-7: Filtrowanie i wyszukiwanie kandydatów

| Pole | Wartość |
|------|---------|
| **Tytuł** | Filtrowanie i wyszukiwanie kandydatów |
| **Priorytet** | Medium |
| **Story Points** | 5 |

---

#### STORY-8: Kanban rekrutacyjny (drag & drop statusów)

| Pole | Wartość |
|------|---------|
| **Tytuł** | Kanban rekrutacyjny (drag & drop statusów) |
| **Priorytet** | Medium |
| **Story Points** | 8 |

---

## EPIC-2: Portal Kandydata

**Cel:** Dedykowany portal dla kandydatów z real-time trackingiem statusu aplikacji i automatycznym feedbackiem. Osiągnięcie cNPS +50.

### Historyjki użytkownika

---

#### STORY-9: Dashboard moich aplikacji (kandydat)

| Pole | Wartość |
|------|---------|
| **Tytuł** | Dashboard moich aplikacji (kandydat) |
| **Priorytet** | High |
| **Story Points** | 8 |

**Opis wymagań:**
Portal dla kandydatów gdzie widzą wszystkie swoje aplikacje z aktualnym statusem. Timeline z historią zmian statusów i datami. Możliwość sortowania i filtrowania aplikacji.

**User Story:**
> Jako kandydat, chcę widzieć status wszystkich moich aplikacji w jednym miejscu, abym miał kontrolę nad procesami rekrutacyjnymi.

**Kryteria Akceptacji:**

- **Given:** Jestem zalogowanym kandydatem z 3 aktywnymi aplikacjami
- **When:** Otwieram sekcję 'Moje aplikacje'
- **Then:** Widzę listę wszystkich aplikacji z nazwą stanowiska, firmą, datą aplikacji i statusem
- **And:** Dla każdej aplikacji widzę timeline z historią zmian statusów i datami

**Refinement:**

- *Techniczny:* Endpoint GET /api/v1/candidates/me/applications z paginacją
- *Techniczny:* Model danych ApplicationStatusHistory z timestampami
- *Techniczny:* Frontend: React component z timeline visualization (np. react-vertical-timeline)
- *Techniczny:* WebSocket subscription dla real-time updates
- *Organizacyjny:* Design UI/UX dashboardu (mockupy w Figma)

---

#### STORY-10: Powiadomienia o zmianie statusu (email + push)

| Pole | Wartość |
|------|---------|
| **Tytuł** | Powiadomienia o zmianie statusu (email + push) |
| **Priorytet** | High |
| **Story Points** | 8 |

**Opis wymagań:**
System wysyła powiadomienia do kandydata przy każdej zmianie statusu aplikacji. Email w ciągu 5 minut, powiadomienie w portalu (czerwona kropka), opcjonalnie push notification na mobile.

**User Story:**
> Jako kandydat, chcę otrzymywać natychmiastowe powiadomienia o zmianach w moich aplikacjach, abym był na bieżąco bez konieczności ciągłego sprawdzania.

**Kryteria Akceptacji:**

- **Given:** Moja aplikacja zmieniła status z 'W ocenie' na 'Zaproszenie na rozmowę'
- **When:** Rekruter zapisuje zmianę statusu
- **Then:** Otrzymuję powiadomienie email w ciągu 5 minut
- **And:** Widzę powiadomienie w portalu (czerwona kropka przy dzwoneczku)
- **And:** Jeśli mam aplikację mobilną, dostaję push notification

**Refinement:**

- *Techniczny:* Event-driven architecture (Kafka/RabbitMQ) dla powiadomień
- *Techniczny:* Email service z szablonami (np. SendGrid, Mailgun)
- *Techniczny:* Push notifications via Firebase Cloud Messaging
- *Techniczny:* Notification preferences dla kandydata (opt-out opcje)
- *Techniczny:* Endpoint GET /api/v1/notifications z filtrami read/unread
- *Organizacyjny:* Przygotowanie szablonów emaili (copywriting)

---

#### STORY-11: Automatyczny feedback przy odrzuceniu

| Pole | Wartość |
|------|---------|
| **Tytuł** | Automatyczny feedback przy odrzuceniu |
| **Priorytet** | Medium |
| **Story Points** | 5 |

---

#### STORY-12: Przypomnienie o aplikacji bez zmian (14 dni)

| Pole | Wartość |
|------|---------|
| **Tytuł** | Przypomnienie o aplikacji bez zmian (14 dni) |
| **Priorytet** | Low |
| **Story Points** | 3 |

---

#### STORY-13: Rejestracja i logowanie kandydata

| Pole | Wartość |
|------|---------|
| **Tytuł** | Rejestracja i logowanie kandydata |
| **Priorytet** | High |
| **Story Points** | 5 |

**Opis wymagań:**
Kandydaci mogą założyć konto w Portalu Kandydata, aby aplikować na oferty, śledzić statusy i zarządzać swoimi danymi. System obsługuje rejestrację tradycyjną (Email/Hasło) oraz Social Login (Google, LinkedIn). Wymagane jest potwierdzenie adresu email oraz akceptacja regulaminu i zgód RODO.

**User Story:**
> Jako kandydat, chcę łatwo zalogować się do systemu (najlepiej jednym kliknięciem przez LinkedIn), aby nie tracić czasu na wypełnianie formularzy rejestracyjnych.

**Kryteria Akceptacji:**

- **Given:** Jestem nowym użytkownikiem na stronie głównej
- **When:** Klikam "Zaloguj przez LinkedIn" i autoryzuję aplikację
- **Then:** System tworzy dla mnie konto pobierając imię, nazwisko i zdjęcie z LinkedIn
- **And:** Jestem zalogowany i przekierowany do dashboardu
- **And:** Na mój adres email przychodzi powiadomienie powitalne

**Refinement:**

- *Techniczny:* Implementacja OAuth2 Client dla Google i LinkedIn
- *Techniczny:* Bezpieczne przechowywanie haseł (Argon2 / bcrypt) dla logowania emailowego
- *Techniczny:* Mechanizm sesji (JWT Access Token + Refresh Token w HttpOnly Cookie)
- *Techniczny:* Obsługa flow "Zapomniałem hasła" ze zmianą przez link email
- *Organizacyjny:* Rejestracja aplikacji w Google Console i LinkedIn Developers
- *Organizacyjny:* Przygotowanie treści zgód i regulaminu (współpraca z prawnikiem)

---

#### STORY-14: Profil kandydata (edycja danych)

| Pole | Wartość |
|------|---------|
| **Tytuł** | Profil kandydata (edycja danych) |
| **Priorytet** | Medium |
| **Story Points** | 5 |

---

#### STORY-15: Formularz aplikacji na ofertę

| Pole | Wartość |
|------|---------|
| **Tytuł** | Formularz aplikacji na ofertę |
| **Priorytet** | High |
| **Story Points** | 5 |

---

## EPIC-3: Cyfrowy Obieg Dokumentów i E-podpis

**Cel:** Elektroniczny proces podpisywania dokumentów zatrudnienia bez drukowania i skanowania. Redukcja czasu pracy działu kadr o 80%.

### Historyjki użytkownika

---

#### STORY-16: Podpisanie umowy elektronicznie (e-podpis)

| Pole | Wartość |
|------|---------|
| **Tytuł** | Podpisanie umowy elektronicznie (e-podpis) |
| **Priorytet** | High |
| **Story Points** | 13 |

**Opis wymagań:**
Nowo zatrudniony pracownik otrzymuje pakiet dokumentów do podpisu elektronicznego. Po kliknięciu linku z emaila, przechodzi do dostawcy e-podpisu (Autenti), składa podpis i wraca do HRflow ze statusem 'Podpisane'. Otrzymuje email z podpisanymi dokumentami w PDF.

**User Story:**
> Jako nowo zatrudniony pracownik, chcę podpisać wszystkie dokumenty elektronicznie przed pierwszym dniem pracy, abym w pierwszy dzień mógł skupić się na poznawaniu zespołu.

**Kryteria Akceptacji:**

- **Given:** HR wysłał mi pakiet dokumentów do podpisu
- **When:** Otwieram link z emaila, loguję się, przeglądam dokumenty i klikam 'Podpisz'
- **Then:** System wysyła mnie do dostawcy e-podpisu (np. Autenti)
- **And:** Po złożeniu podpisu, wracam do HRflow gdzie widzę status 'Podpisane'
- **And:** Otrzymuję email z podpisanymi dokumentami w PDF

**Refinement:**

- *Techniczny:* Integracja z Autenti API (OAuth2, webhooks)
- *Techniczny:* Workflow engine dla procesu podpisywania (statusy: draft, sent, viewed, signed)
- *Techniczny:* Storage dla dokumentów (S3 + szyfrowanie AES-256)
- *Techniczny:* Endpoint POST /api/v1/documents/{id}/sign-request
- *Organizacyjny:* Negocjacja warunków z Autenti (pricing, SLA)
- *Organizacyjny:* Przygotowanie szablonów dokumentów (umowa o pracę, B2B, NDA)

---

#### STORY-17: Automatyczne generowanie umów z szablonu

| Pole | Wartość |
|------|---------|
| **Tytuł** | Automatyczne generowanie umów z szablonu |
| **Priorytet** | High |
| **Story Points** | 8 |

**Opis wymagań:**
HR Admin może wygenerować umowę automatycznie wypełnioną danymi kandydata (imię, nazwisko, stanowisko, wynagrodzenie, data rozpoczęcia) z predefiniowanego szablonu. Możliwość podglądu przed wysłaniem do podpisu.

**User Story:**
> Jako HR Admin, chcę generować umowy automatycznie z szablonów, abym nie musiał ręcznie wypełniać każdego dokumentu.

**Kryteria Akceptacji:**

- **Given:** Kandydat zaakceptował ofertę na stanowisko Senior Developer z wynagrodzeniem 20 000 PLN B2B
- **When:** Klikam 'Generuj umowę' i wybieram szablon 'Umowa B2B IT'
- **Then:** System automatycznie wypełnia szablon danymi: imię, nazwisko, stanowisko, wynagrodzenie, data rozpoczęcia
- **And:** Mogę przejrzeć dokument przed wysłaniem do podpisu
- **And:** Dokument jest zapisany w formacie pozwalającym na e-podpis

**Refinement:**

- *Techniczny:* Template engine (np. docxtpl dla Python, Handlebars dla Node.js)
- *Techniczny:* CRUD API dla szablonów: /api/v1/document-templates
- *Techniczny:* PDF conversion (LibreOffice headless lub Pandoc)
- *Techniczny:* Wersjonowanie szablonów
- *Organizacyjny:* Współpraca z działem prawnym przy tworzeniu szablonów

---

#### STORY-18: Przypomnienie o niepodpisanych dokumentach

| Pole | Wartość |
|------|---------|
| **Tytuł** | Przypomnienie o niepodpisanych dokumentach |
| **Priorytet** | Medium |
| **Story Points** | 3 |

---

#### STORY-19: Wygaśnięcie linku do podpisu (7 dni)

| Pole | Wartość |
|------|---------|
| **Tytuł** | Wygaśnięcie linku do podpisu (7 dni) |
| **Priorytet** | Low |
| **Story Points** | 2 |

---

#### STORY-20: Panel HR - zarządzanie dokumentami

| Pole | Wartość |
|------|---------|
| **Tytuł** | Panel HR - zarządzanie dokumentami |
| **Priorytet** | High |
| **Story Points** | 8 |

---

#### STORY-21: Archiwum podpisanych dokumentów

| Pole | Wartość |
|------|---------|
| **Tytuł** | Archiwum podpisanych dokumentów |
| **Priorytet** | Medium |
| **Story Points** | 5 |

---

## EPIC-4: Automatyczne Odbieranie Dostępów (Offboarding)

**Cel:** Automatyczna dezaktywacja dostępów do systemów IT przy zakończeniu zatrudnienia. 100% automatyzacja procesu odbierania dostępów.

### Historyjki użytkownika

---

#### STORY-22: Automatyczna dezaktywacja kont w dniu zakończenia

| Pole | Wartość |
|------|---------|
| **Tytuł** | Automatyczna dezaktywacja kont w dniu zakończenia |
| **Priorytet** | High |
| **Story Points** | 13 |

**Opis wymagań:**
W ostatnim dniu pracy pracownika (23:59) system automatycznie dezaktywuje: konto AD, email, VPN, dostępy do systemów wewnętrznych (Jira, Confluence, GitHub). IT Admin otrzymuje raport, menedżer powiadomienie.

**User Story:**
> Jako Administrator IT, chcę aby dostępy odchodzącego pracownika były automatycznie odbierane, abym nie musiał pamiętać o każdym systemie i nie ryzykować wycieku danych.

**Kryteria Akceptacji:**

- **Given:** Pracownik Jan Kowalski ma ostatni dzień pracy 31.01.2025
- **When:** Nastaje 31.01.2025, godzina 23:59
- **Then:** System automatycznie wyłącza konto AD, odbiera dostęp do email, dezaktywuje VPN, odbiera dostępy do systemów wewnętrznych
- **And:** IT Admin otrzymuje raport z listą odebranych dostępów
- **And:** Menedżer otrzymuje powiadomienie

**Refinement:**

- *Techniczny:* Integracja z Active Directory (LDAP/LDAPS) - biblioteka python-ldap lub ldap3
- *Techniczny:* Scheduler (Celery/APScheduler) dla automatycznych zadań o 23:59
- *Techniczny:* Adapter pattern dla różnych systemów (GitHub API, Jira API, VPN)
- *Techniczny:* Audit log wszystkich operacji dezaktywacji
- *Techniczny:* Rollback mechanism w przypadku błędów
- *Organizacyjny:* Mapowanie wszystkich systemów wymagających dezaktywacji
- *Organizacyjny:* Ustalenie SLA z IT na integracje

---

#### STORY-23: Lista kontrolna offboardingu (checklist)

| Pole | Wartość |
|------|---------|
| **Tytuł** | Lista kontrolna offboardingu (checklist) |
| **Priorytet** | High |
| **Story Points** | 8 |

**Opis wymagań:**
Przy rozpoczęciu offboardingu system generuje checklistę zadań: zwrot sprzętu, przekazanie obowiązków, exit interview, lista dostępów do odebrania. Możliwość przypisania zadań do odpowiednich osób z śledzeniem wykonania.

**User Story:**
> Jako HR Admin, chcę mieć checklistę offboardingu z przypisanymi zadaniami, abym miał pewność że nic nie zostanie pominięte.

**Kryteria Akceptacji:**

- **Given:** Pracownik złożył wypowiedzenie
- **When:** Rozpoczynam proces offboardingu
- **Then:** System generuje checklistę: zwrot sprzętu, przekazanie obowiązków, exit interview, dostępy do odebrania
- **And:** Mogę przypisać zadania do odpowiednich osób (IT, menedżer, HR)
- **And:** System śledzi wykonanie i przypomina o zaległych zadaniach

**Refinement:**

- *Techniczny:* Model OffboardingChecklist z relacją do OffboardingTask
- *Techniczny:* Konfigurowalne szablony checklist per stanowisko/dział
- *Techniczny:* Notifications engine dla przypomnień
- *Techniczny:* Dashboard z progress tracking
- *Organizacyjny:* Zdefiniowanie standardowej checklisty z HR i IT

---

#### STORY-24: Exit interview (ankieta online)

| Pole | Wartość |
|------|---------|
| **Tytuł** | Exit interview (ankieta online) |
| **Priorytet** | Medium |
| **Story Points** | 5 |

---

#### STORY-25: Raport offboardingu dla IT

| Pole | Wartość |
|------|---------|
| **Tytuł** | Raport offboardingu dla IT |
| **Priorytet** | Medium |
| **Story Points** | 3 |

---

#### STORY-26: Archiwizacja konta (nie usuwanie)

| Pole | Wartość |
|------|---------|
| **Tytuł** | Archiwizacja konta (nie usuwanie) |
| **Priorytet** | Medium |
| **Story Points** | 3 |

---

## EPIC-5: Infrastruktura i Bezpieczeństwo

**Cel:** Fundamenty techniczne systemu: autentykacja, autoryzacja, bezpieczeństwo RODO, infrastruktura.

### Zadania (Tasks)

| ID | Tytuł | Priorytet | Story Points |
|----|-------|-----------|--------------|
| TASK-1 | Setup projektu i repozytorium | High | 2 |
| TASK-2 | Konfiguracja CI/CD pipeline | High | 3 |
| TASK-3 | Setup bazy danych PostgreSQL | High | 2 |
| TASK-4 | Implementacja autentykacji JWT | High | 5 |
| TASK-5 | System ról i uprawnień (RBAC) | High | 5 |
| TASK-6 | Konfiguracja HTTPS/TLS 1.3 | High | 2 |
| TASK-7 | Implementacja rate limiting API | Medium | 3 |
| TASK-8 | Szyfrowanie danych w spoczynku (AES-256) | High | 3 |
| TASK-9 | Audit logging zdarzeń bezpieczeństwa | High | 5 |
| TASK-10 | Mechanizm zgód RODO | High | 5 |
| TASK-11 | Endpoint eksportu danych użytkownika | Medium | 3 |
| TASK-12 | Endpoint usunięcia danych (prawo do bycia zapomnianym) | Medium | 5 |
| TASK-13 | Konfiguracja Elasticsearch dla wyszukiwania | Medium | 5 |
| TASK-14 | Setup Redis dla cache | Medium | 2 |
| TASK-15 | Konteneryzacja Docker + docker-compose | High | 3 |
| TASK-16 | Monitoring i alerty (Prometheus + Grafana) | Medium | 5 |

---

## Podsumowanie backlogu

| Typ | Ilość | Story Points |
|-----|-------|--------------|
| Epiki | 5 | - |
| Historyjki (Stories) | 26 | 147 |
| Zadania (Tasks) | 16 | 55 |
| **RAZEM** | **47** | **202 SP** |

## Backlog w Jira

![Backlog w Jira](./images/backlog.png)

### Historyjki szczegółowe (z pełnymi opisami)

1. STORY-1: Parsowanie CV z ekstrakcją danych (8 SP)
2. STORY-2: Scoring dopasowania kandydata (5 SP)
3. STORY-6: Tworzenie i publikacja ofert pracy (8 SP)
4. STORY-9: Dashboard moich aplikacji (8 SP)
5. STORY-10: Powiadomienia o zmianie statusu (8 SP)
6. STORY-13: Rejestracja i logowanie kandydata (5 SP)
7. STORY-16: Podpisanie umowy elektronicznie (13 SP)
8. STORY-17: Automatyczne generowanie umów (8 SP)
9. STORY-22: Automatyczna dezaktywacja kont (13 SP)
10. STORY-23: Lista kontrolna offboardingu (8 SP)

---

---

# Dokumentacja Projektowa: Silnik Scoringowy HRflow (PoC)
### Powiązana historyjka (US) – zakres PoC

**User Story:** Jako rekruter, chcę widzieć procentowe dopasowanie kandydata do oferty, abym mógł szybko priorytetyzować najlepszych kandydatów.

**Skrót wymagań:** System oblicza score dopasowania (0–100%) na podstawie CV i wymagań oferty z rozbiciem na kategorie oraz wizualizacją spełnionych/niespełnionych wymagań.

### Szczegóły US w Jira

![Szczegóły historyjki – scoring dopasowania](./images/jira_us_scoring.png)


## 1. Opis Proof of Concept (PoC)
**Cel:** Weryfikacja technicznej wykonalności automatycznego dopasowania kandydatów do ofert pracy przy użyciu technologii NLP (Natural Language Processing) oraz ocena trafności algorytmu scoringowego.

### 1.1 Hipoteza Badawcza
Jesteśmy w stanie zaimplementować algorytm (Matching Engine), który na podstawie analizy semantycznej dostarczy wynik procentowy o trafności na poziomie minimum 80% w porównaniu do subiektywnej oceny rekrutera. Zastosowanie warstwy cache (Redis) powinno zredukować czas odpowiedzi dla powtarzalnych zapytań o co najmniej 70%.

### 1.2 Model Matematyczny (Baseline)
Wstępny model scoringowy opiera się na ważonej sumie składowych z uwzględnieniem kar za brak wymagań krytycznych:

$$Score = \left( \sum_{i=1}^{n} w_i \cdot s_i \right) - P$$

Gdzie:
* $w_i$ – waga danej kategorii (technologie, doświadczenie, edukacja),
* $s_i$ – stopień dopasowania w danej kategorii (0.0 - 1.0),
* $P$ – kara (penalty) za brak kompetencji typu "Must-have".

---

## 2. Planowanie Sprintu 1 (PoC)

### 2.1 Cel Sprintu (Sprint Goal)
**Cel:** Potwierdzić w ciągu 2 tygodni, że automatyczny scoring CV oparty na NLP osiąga trafność >80% względem oceny ludzkiej, aby zminimalizować ryzyko inwestycji w rozwój pełnego modułu ATS.

### 2.2 Definition of Done (DoD)
Kryteria ukończenia dla każdego zadania w sprincie:
1. **Kod:** Przejrzysty, sformatowany (PEP8/ESLint), bez hardcodowanych sekretów.
2. **Testy:** Testy jednostkowe napisane i przechodzące na zielono (min. 80% pokrycia dla core logiki).
3. **Review:** Code Review zatwierdzone przez min. 1 inną osobę z zespołu.
4. **Dokumentacja:** Zaktualizowana dokumentacja techniczna (README, Swagger).
5. **Wdrożenie:** Funkcjonalność uruchomiona na środowisku developerskim (lub lokalnym w przypadku PoC).

### 2.3 Tablica Sprintu 1 w Jira

![Tablica Sprintu 1 w Jira](./images/sprint1_board.png)

---

## 3. Backlog Sprintu 1 (Zaktualizowany)

### T1. Research: Analiza bibliotek NLP i ekstrakcji cech
* **Priorytet:** Highest | **Estymacja:** 3 SP
* **DoD:** Wybrana biblioteka (np. spaCy/NLTK), stworzony snippet kodu z ekstrakcją encji, dokumentacja wyboru.

### T2. Research: Metody analizy podobieństwa semantycznego
* **Priorytet:** Highest | **Estymacja:** 2 SP
* **DoD:** Wybrany model (np. Cosine Similarity), opis algorytmu w formie pseudokodu, testy na parach fraz.

### T3. Implementacja: Rdzeń algorytmu scoringowego (Core Engine)
* **Priorytet:** Highest | **Estymacja:** 8 SP
* **DoD:** Funkcja zwraca wynik 0.0-1.0, uwzględnia wagi z pliku JSON, pokrycie testami min. 80%.

### T4. Analiza: Eksperyment walidacyjny i testy akceptacyjne PoC
* **Priorytet:** Highest | **Estymacja:** 3 SP
* **DoD:** Arkusz porównawczy "System vs Człowiek", analiza min. 3 błędów, weryfikacja czasów odpowiedzi API.

### T5. Projekt: Model wagowy algorytmu scoringowego
* **Priorytet:** High | **Estymacja:** 3 SP
* **DoD:** Plik konfiguracyjny JSON z wagami, zdefiniowana logika stażu pracy i kar za brak "must-haves".

### T6. Architektura: Projekt kontraktu API i struktur JSON
* **Priorytet:** High | **Estymacja:** 3 SP
* **DoD:** Plik swagger.yaml w repozytorium, zdefiniowane typy danych i przykłady payloadów.

### T7. Implementacja: Parser struktur danych wejściowych
* **Priorytet:** High | **Estymacja:** 5 SP
* **DoD:** Implementacja czyszczenia tekstu (PEP8), mechanizm null-safety, testy jednostkowe normalizacji.

### T8. Analiza: Przygotowanie zbiorów testowych (Persona Mocks)
* **Priorytet:** High | **Estymacja:** 2 SP
* **DoD:** 10 plików JSON z profilami (w tym "brudne" dane), 2 oferty pracy wgrane do repozytorium.

### T9. Architektura: Projekt warstwy cache i polityki Redis
* **Priorytet:** Low | **Estymacja:** 2 SP
* **DoD:** Schemat kluczy, zdefiniowany TTL, opisana strategia failover.

### T10. Implementacja: Moduł integracji z Redis Cache
* **Priorytet:** Low | **Estymacja:** 3 SP
* **DoD:** Middleware zapisu/odczytu z Redis, potwierdzenie "Cache Hit" w logach.

### T11. [PoC] Final Review, Dokumentacja Techniczna i Decyzja Go/No-Go
* **Priorytet:** Highest | **Estymacja:** 2 SP
* **Relacje:** Blokowany przez T1-T10.
* **DoD:** Raport końcowy (HLA, Performance Report, lista długu technicznego), oficjalna rekomendacja Go/No-Go.

---

## 4. Analiza Pre-Mortem (Zaktualizowana)

### 4.1 Identyfikacja przyczyn porażki (Analiza zagrożeń)
* **Niewydolność algorytmiczna (NLP):** Model nie rozpoznaje kontekstu (np. myli "Project Manager" w IT z budownictwem).
* **Luki w bezpieczeństwie:** Przechowywanie danych wrażliwych (PII) w Redisie bez anonimizacji.
* **Podatność na manipulację:** "Keyword stuffing" pozwala słabym kandydatom sztucznie zawyżyć wynik.
* **Błąd integracji (API mismatch):** Backend zwraca strukturę niezgodną z ustalonym kontraktem, co uniemożliwia konsumpcję danych przez inne moduły systemu.
* **Nierealistyczne dane testowe (laboratory bias):** Parser polega na "brudnych" danych z realnych CV (literówki, nietypowe formaty).
* **Brak zaufania do wyniku:** Użytkownicy końcowi odrzucają system, bo algorytm jest "czarną skrzynką" bez uzasadnienia oceny.
* **Niestabilność wag (overfitting):** Wagi ustawione „pod mocki” nie działają poprawnie dla nowych ofert.
* **Brak rozróżnienia krytyczności:** Kandydat bez kluczowej umiejętności (must-have) nadal otrzymuje wysoki wynik ogólny przez nadmiar skilli pobocznych.

### 4.2 Plan zapobiegawczy (Mitygacja)

| Identyfikowane zagrożenie | Działanie zapobiegawcze (mitygacja) | Ref. Task |
| :--- | :--- | :--- |
| **Słaba jakość NLP** | Implementacja normalizacji tekstu oraz słownika synonimów technicznych. | **T2, T7** |
| **Wyciek danych** | Redis przechowuje wyłącznie `candidate_id` i wyniki; brak surowego tekstu CV. | **T9, T10** |
| **Keyword stuffing** | Limity zagęszczenia słów kluczowych i flagowanie anomalii w parserze. | **T7** |
| **API mismatch** | Jedno źródło prawdy: `swagger.yaml` i ścisła walidacja typów danych. | **T6** |
| **Brudne dane** | Uwzględnienie w mockach CV z błędami i skrótami dla testu odporności. | **T8** |
| **Brak zaufania** | Rozszerzenie kontraktu API o pole z uzasadnieniem (spełnione/brakujące wymogi). | **T6** |
| **Niestabilność wag** | Ustalenie wag bazowych i walidacja na co najmniej 2 różnych profilach stanowisk. | **T5** |
| **Brak must-have** | Implementacja twardych kar punktowych w modelu matematycznym. | **T3, T5** |

### 4.3 Sygnały ostrzegawcze (Early Warning Indicators)
Jeśli do połowy sprintu wystąpią poniższe zjawiska, zespół zawęża zakres:
- Brak zamrożonego kontraktu API (ryzyko blokady przyszłych prac frontendowych).
- Niskie zróżnicowanie mocków testowych w T8 (ryzyko błędnego poczucia sukcesu).
- Brak powtarzalności wyników algorytmu (niedeterministyczność przy tych samych wagach).

---

## 5. Plan awaryjny (Pivot)
Jeśli NLP okaże się nieskuteczne w zakładanym czasie:
1. Przechodzimy na model **TF-IDF** jako baseline.
2. Skupiamy się na czytelnej liście wymagań (Checklist), by rekruter mógł sam ocenić jakość.
3. Ograniczamy semantykę do twardego słownika relacji dla 20 najczęstszych technologii.

---

## 6. Ryzyka projektowe i decyzje „co dalej” (Output PoC)



Po zakończeniu sprintu zespół prezentuje raport T5, który determinuje dalsze losy projektu:
* **Go:** Ranking jest trafny, wynik uzasadniony, architektura skalowalna.
* **Go z korektą:** Wymagana poprawa wag lub rozbudowa słownika synonimów.
* **No-Go:** Algorytm jest niestabilny, a złożoność naprawy przekracza zakładane korzyści biznesowe.

**Finalny produkt PoC:**
- Dokumentacja HLA (High Level Architecture),
- Performance Report (opóźnienia cold/warm start),
- Lista długu technicznego do spłacenia w fazie MVP.

---

## Załączniki

- Link do projektu w Jira: [HRflow Jira](https://student-team-o0pbmzdv.atlassian.net/jira/software/projects/HR/boards/1)