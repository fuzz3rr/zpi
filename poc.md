# Dokumentacja Projektowa: Silnik Scoringowy HRflow (PoC)

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

## 2. Backlog Sprintu 1

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

### T5. [PoC] Final Review, Dokumentacja Techniczna i Decyzja Go/No-Go
* **Priorytet:** Highest | **Estymacja:** 2 SP
* **Relacje:** Blokowany przez T1-T12.
* **DoD:** Raport końcowy (HLA, Performance Report, lista długu technicznego), oficjalna rekomendacja Go/No-Go.

### T6. Projekt: Model wagowy algorytmu scoringowego
* **Priorytet:** High | **Estymacja:** 3 SP
* **DoD:** Plik konfiguracyjny JSON z wagami, zdefiniowana logika stażu pracy i kar za brak "must-haves".

### T7. Architektura: Projekt kontraktu API i struktur JSON
* **Priorytet:** High | **Estymacja:** 3 SP
* **DoD:** Plik swagger.yaml w repozytorium, zdefiniowane typy danych i przykłady payloadów.

### T8. Implementacja: Parser struktur danych wejściowych
* **Priorytet:** High | **Estymacja:** 5 SP
* **DoD:** Implementacja czyszczenia tekstu (PEP8), mechanizm null-safety, testy jednostkowe normalizacji.

### T9. Analiza: Przygotowanie zbiorów testowych (Persona Mocks)
* **Priorytet:** High | **Estymacja:** 2 SP
* **DoD:** 10 plików JSON z profilami (w tym "brudne" dane), 2 oferty pracy wgrane do repozytorium.

### T10. Implementacja: Frontend - Komponenty wizualizacji scoringu
* **Priorytet:** Medium | **Estymacja:** 5 SP
* **DoD:** Komponenty Score Circle i Checklist wyświetlające dane z API, obsługa stanów ładowania.

### T11. Implementacja: Frontend - Layout i szkielet Dashboardu
* **Priorytet:** Medium | **Estymacja:** 3 SP
* **DoD:** Responsywny szkielet aplikacji w React, zaimplementowany routing.

### T12. Architektura: Projekt warstwy cache i polityki Redis
* **Priorytet:** Low | **Estymacja:** 2 SP
* **DoD:** Schemat kluczy, zdefiniowany TTL, opisana strategia failover.

### T13. Implementacja: Moduł integracji z Redis Cache
* **Priorytet:** Low | **Estymacja:** 3 SP
* **DoD:** Middleware zapisu/odczytu z Redis, potwierdzenie "Cache Hit" w logach.

---

## 3. Strategia Zarządzania Zakresem (Scope Management)

W przypadku presji czasu zespół stosuje zasadę **"Core over Scale"**:
1. **Niezbędne (T1-T4, T6-T9):** Muszą zostać dowiezione, aby PoC miał wartość merytoryczną.
2. **Możliwe do pominięcia:** Rezygnacja z Redisa (T12-T13) oraz wizualizacji frontendowej (T10-T11) na rzecz prezentacji wyników w Postmanie/Konsoli.

---

## 4. Analiza Pre-Mortem (Zaktualizowana)



### 4.1 Identyfikacja przyczyn porażki (Analiza zagrożeń)
* **Niewydolność algorytmiczna (NLP):** Model nie rozpoznaje kontekstu (np. myli "Project Manager" w IT z budownictwem).
* **Luki w bezpieczeństwie:** Przechowywanie danych wrażliwych (PII) w Redisie bez anonimizacji.
* **Podatność na manipulację:** "Keyword stuffing" pozwala słabym kandydatom sztucznie zawyżyć wynik.
* **Błąd integracji (API mismatch):** Frontend i backend różnie zinterpretowały kontrakt JSON, powodując błędy 500.
* **Nierealistyczne dane testowe (laboratory bias):** Parser polega na "brudnych" danych z realnych CV (literówki, nietypowe formaty).
* **Brak zaufania do wyniku:** Rekruterzy odrzucają system, bo nie widzą uzasadnienia oceny.
* **Niestabilność wag (overfitting):** Wagi ustawione „pod mocki” nie działają poprawnie dla nowych ofert.
* **Brak rozróżnienia krytyczności:** Kandydat bez kluczowej umiejętności (must-have) nadal otrzymuje wysoki wynik ogólny.

### 4.2 Plan zapobiegawczy (Mitygacja)
| Identyfikowane zagrożenie | Działanie zapobiegawcze (mitygacja) |
| :--- | :--- |
| **Słaba jakość NLP** | Normalizacja (T8), lematyzacja i słownik synonimów kompetencji (T2). |
| **Wyciek danych** | Redis przechowuje wyłącznie `candidate_id` i wyniki; brak surowego tekstu CV. |
| **Keyword stuffing** | Limity zagęszczenia słów kluczowych i flagowanie anomalii w danych. |
| **API mismatch** | Jedno źródło prawdy: `swagger.yaml` (T7) + walidacja typów po obu stronach. |
| **Brudne dane** | W T9 dodajemy CV z błędami i skrótami, by przetestować odporność parsera. |
| **Brak zaufania** | Rozszerzenie API o listę spełnionych/niespełnionych wymagań + uzasadnienie (T10). |
| **Niestabilność wag** | Ustalenie wag bazowych i test na 2 różnych rolach; dokumentacja decyzji (T6). |
| **Brak must-have** | Zasada „kompetencje krytyczne” i wysokie kary punktowe w modelu (T6). |

### 4.3 Sygnały ostrzegawcze (Early Warning Indicators)
Jeśli do połowy sprintu wystąpią poniższe zjawiska, zespół zawęża zakres:
- Brak zamrożonego kontraktu API (ryzyko API mismatch).
- Niskie zróżnicowanie mocków testowych (ryzyko biasu).
- Brak powtarzalności wyników algorytmu (niedeterministyczność).
- Problemy z wydajnością NLP blokujące frontend.

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