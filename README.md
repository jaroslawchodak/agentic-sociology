# Agentic Sociology — warsztat

Półwarsztat (75 minut) dla pracowników naukowych i doktorantów nauk społecznych i humanistycznych — początkujących w obszarze AI. Pokaz „od czatu do systemu agentowego" z pełną demonstracją na danych European Social Survey (ESS).

📖 **Wersja online (Quarto Book):** [jaroslawchodak.github.io/agentic-sociology](https://jaroslawchodak.github.io/agentic-sociology)

## Zawartość repozytorium

| Plik / folder | Co to |
|---|---|
| `_quarto.yml` | Konfiguracja Quarto Book |
| `index.qmd` | Strona startowa książki |
| `01-wprowadzenie.qmd` … `08-zamkniecie.qmd` | Rozdziały książki (kolejność wynika z numeru) |
| `new-plan.md` | Plan warsztatu (75 min) — agenda, cele edukacyjne, opis pokazu |
| `ESS-demo/` | Folder demonstracyjny do analizy ESS: `AGENTS.md`, `CONTEXT.md`, `WORKFLOW.md`, `prompt-wykonawczy.md` |

## Struktura książki

```
Przedmowa                       index.qmd
1. Wprowadzenie                 01-wprowadzenie.qmd
2. Czym jest agent              02-czym-jest-agent.qmd
3. Krajobraz narzędzi           03-krajobraz.qmd
4. Jak rozmawiać z agentem      04-jak-rozmawiac.qmd
5. Case Study ESS               05-case-study-ess.qmd
6. Zastosowania w socjologii    06-zastosowania.qmd
7. Friction — etyka i napięcia  07-friction.qmd
Zamknięcie                      08-zamkniecie.qmd
```

## Wymagania

- [Quarto](https://quarto.org/docs/get-started/) ≥ 1.4
- Przeglądarka z obsługą JavaScript (do podglądu)

Diagramy Mermaid i motyw Bootswatch `litera` renderują się natywnie przez Quarto — nic dodatkowo nie trzeba instalować.

## Lokalne renderowanie

```bash
git clone https://github.com/jaroslawchodak/agentic-sociology.git
cd agentic-sociology

# render całej książki do _book/
quarto render

# podgląd na żywo (z autorefresh)
quarto preview
```

Po `quarto render` w katalogu `_book/` powstaje cała strona z `index.html`, plikami rozdziałów i lewym sidebarem TOC.

## Publikacja na GitHub Pages

```bash
quarto publish gh-pages
```

Quarto zarządza gałęzią `gh-pages` samodzielnie. Po pierwszej publikacji w **Settings → Pages** ustaw źródło na `gh-pages` → `/ (root)`. Strona będzie dostępna pod:

```
https://jaroslawchodak.github.io/agentic-sociology/
```

## Aktualizacja repozytorium

Po wprowadzeniu zmian w plikach `.qmd`:

```bash
git add .
git commit -m "Opis zmiany"
git push                            # źródła do main
quarto publish gh-pages             # wyrenderowana wersja do gh-pages
```

## Licencja

Materiały dydaktyczne — do swobodnego użytku akademickiego z zachowaniem atrybucji autora.
