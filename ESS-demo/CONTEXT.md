# CONTEXT.md

## Cel projektu

Projekt służy jako demonstracja pracy z agentem AI w analizie prostych danych publicznych. Głównym celem nie jest stworzenie pełnej publikacji naukowej, lecz pokazanie uczestnikom warsztatu, jak agent może pomóc w uporządkowanym procesie analizy danych.

## Temat demonstracji

Analiza dotyczy zadowolenia z życia w danych European Social Survey.

Pytanie badawcze:

> Czy osoby o wyższym zaufaniu społecznym, lepszym zdrowiu, wyższym dochodzie i wyższym poziomie edukacji deklarują wyższe zadowolenie z życia?

## Wariant analizy

Wykonujemy wariant podstawowy:

- tylko dane ESS;
- poziom indywidualny respondentów;
- prosta analiza zależności;
- korelacja i regresja OLS;
- raport w Markdown.

Eurostat może zostać wspomniany jako możliwe rozszerzenie, ale nie jest potrzebny w tej analizie podstawowej.

## Model demonstracyjny

```text
stflife = ppltrst + health + hinctnta + eduyrs + agea + gndr + cntry
```

## Odbiorcy

Odbiorcami demonstracji są badacze społeczni, doktoranci i humaniści początkujący w pracy z AI. Wyjaśnienia mają być proste, przejrzyste i metodologicznie ostrożne.

## Zakładany rezultat

Agent powinien przygotować:

- opis zmiennych;
- informację o danych i brakach danych;
- tabelę opisową;
- korelację `stflife` i `ppltrst`;
- prosty wykres;
- regresję OLS;
- krótki raport w Markdown;
- log decyzji metodologicznych.

## Najważniejsze ograniczenia

Wyniki są demonstracyjne. Nie należy z nich wyprowadzać mocnych wniosków przyczynowych.

Szczególnie trzeba odnotować:

- problem wag ESS;
- ograniczenia danych przekrojowych;
- uproszczenie związane z traktowaniem skal jako liczbowych;
- fakt, że `cntry` jako kontrola kraju nie zastępuje modelu wielopoziomowego;
- konieczność ręcznej kontroli wyników przez badacza.
