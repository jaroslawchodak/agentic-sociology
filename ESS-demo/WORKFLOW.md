# WORKFLOW.md

## Workflow: podstawowa analiza ESS

Ten workflow służy do demonstracyjnej analizy indywidualnych danych European Social Survey.

Pytanie badawcze:

> Czy osoby o wyższym zaufaniu społecznym, lepszym zdrowiu, wyższym dochodzie i wyższym poziomie edukacji deklarują wyższe zadowolenie z życia?

Model demonstracyjny:

```text
stflife = ppltrst + health + hinctnta + eduyrs + agea + gndr + cntry
```

## Zmienne

| Zmienna | Rola | Znaczenie |
|---|---|---|
| `stflife` | zależna | zadowolenie z życia |
| `ppltrst` | niezależna | zaufanie do ludzi |
| `health` | niezależna | samoocena zdrowia |
| `hinctnta` | niezależna | dochód gospodarstwa domowego w decylach |
| `eduyrs` | niezależna | lata edukacji |
| `agea` | kontrolna | wiek |
| `gndr` | kontrolna | płeć |
| `cntry` | kontrolna | kraj |

## Procedura

### 1. Przygotuj projekt

1. Przeczytaj `AGENTS.md`, `CONTEXT.md` i `WORKFLOW.md`.
2. Sprawdź lub utwórz foldery: `data_raw/`, `data_clean/`, `scripts/`, `outputs/`, `agent_logs/`.
3. Nie zmieniaj ani nie nadpisuj danych źródłowych.

### 2. Sprawdź dane ESS

1. Sprawdź, czy w `data_raw/` jest plik ESS.
2. Jeśli pliku nie ma, zapisz instrukcję pobrania w `agent_logs/instrukcja-pobrania-ess.md`.
3. Jeśli plik jest, sprawdź format i obecność wymaganych zmiennych.
4. Zapisz źródło danych, rundę ESS i nazwę pliku w logu decyzji.

### 3. Oczyść dane

1. Zachowaj tylko potrzebne zmienne.
2. Rozpoznaj kody braków danych na podstawie dokumentacji.
3. Przekoduj braki na standardowe wartości brakujące.
4. Sprawdź zakresy wartości zmiennych.
5. Przygotuj wariant complete-case do korelacji i regresji.
6. Zapisz oczyszczony plik w `data_clean/`.

W logu zapisz:

- liczbę obserwacji przed czyszczeniem;
- liczbę obserwacji po czyszczeniu;
- braki danych dla każdej zmiennej;
- zastosowane reguły czyszczenia.

### 4. Przygotuj opis danych

W raporcie pokaż:

- opis zmiennych;
- liczebność próby;
- liczbę krajów;
- tabelę braków danych;
- podstawowe statystyki opisowe dla zmiennych liczbowych;
- krótki opis `gndr` i `cntry`.

### 5. Wykonaj analizę

Wykonaj trzy elementy:

1. Korelacja między `stflife` i `ppltrst`.
2. Prosty wykres: najlepiej `ppltrst` vs `stflife` z linią trendu albo średnie `stflife` dla poziomów `ppltrst`.
3. Regresja OLS:

```text
stflife = ppltrst + health + hinctnta + eduyrs + agea + gndr + cntry
```

Traktuj `gndr` i `cntry` jako zmienne kategoryczne, jeśli wymaga tego narzędzie analityczne.

### 6. Zinterpretuj wyniki

Interpretacja ma być krótka i ostrożna. Oddziel:

- wynik statystyczny;
- możliwą interpretację socjologiczną;
- ograniczenia.

Nie pisz, że zależności są przyczynowe.

### 7. Zapisz wyniki

Zapisz:

```text
outputs/raport-ess-stflife.md
agent_logs/decyzje-ess-stflife.md
```

Jeśli powstanie wykres, zapisz go w `outputs/`, np.:

```text
outputs/wykres-stflife-ppltrst.png
```

## Struktura raportu

Raport `outputs/raport-ess-stflife.md` ma zawierać:

1. Tytuł.
2. Pytanie badawcze.
3. Dane i źródła.
4. Zmienne.
5. Czyszczenie danych i braki.
6. Tabela opisowa.
7. Korelacja `stflife` i `ppltrst`.
8. Wykres.
9. Regresja OLS.
10. Krótka interpretacja.
11. Ograniczenia.
12. Co sprawdzić przed użyciem wyników w publikacji.

## Struktura logu decyzji

Log `agent_logs/decyzje-ess-stflife.md` ma zawierać:

- datę wykonania;
- użyte pliki;
- źródło i rundę ESS;
- użyte zmienne;
- decyzje dotyczące braków danych;
- informację o wagach;
- decyzje dotyczące zmiennych kategorycznych;
- ograniczenia;
- kroki wymagające ręcznej kontroli.

## Kryteria ukończenia

Zadanie jest ukończone, gdy istnieją:

- oczyszczony plik danych w `data_clean/` albo instrukcja pobrania danych;
- raport w `outputs/`;
- log decyzji w `agent_logs/`;
- jasna informacja, których kroków nie udało się wykonać i dlaczego.
