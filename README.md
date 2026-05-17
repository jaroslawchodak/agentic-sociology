# Agentic Sociology — warsztat

Półwarsztat (75 minut) dla pracowników naukowych i doktorantów nauk społecznych i humanistycznych, początkujących w obszarze AI. Pokaz „od czatu do systemu agentowego" z pełną demonstracją na danych European Social Survey (ESS).

## Zawartość repozytorium

| Plik / folder | Co to |
|---|---|
| `presentation.qmd` | Prezentacja Quarto (revealjs) — gotowa do renderowania |
| `new-plan.md` | Plan warsztatu (75 min) — agenda, cele edukacyjne, opis pokazu |
| `ESS-demo/` | Folder demonstracyjny: `AGENTS.md` (konstytucja agenta), `CONTEXT.md` (opis projektu), `WORKFLOW.md` (procedura analizy), `prompt-wykonawczy.md` |

## Wymagania

- [Quarto](https://quarto.org/docs/get-started/) ≥ 1.4
- Przeglądarka z obsługą JavaScript (do podglądu slajdów)

Diagramy Mermaid renderują się natywnie przez Quarto — nic dodatkowo nie trzeba instalować.

## Renderowanie prezentacji

```bash
git clone https://github.com/jaroslawchodak/agentic-sociology.git
cd agentic-sociology

# render do pojedynczego, samodzielnego pliku HTML
quarto render presentation.qmd

# podgląd na żywo (z autorefresh)
quarto preview presentation.qmd
```

Po wyrenderowaniu plik `presentation.html` zawiera wszystkie zasoby (CSS, JS, obrazki) wbudowane dzięki `embed-resources: true` — można go wysłać mailem albo wrzucić na dowolny hosting statyczny.

## Publikacja na GitHub Pages

Najprostsza ścieżka — Quarto sam zrobi gałąź `gh-pages`:

```bash
quarto publish gh-pages presentation.qmd
```

Po pierwszej publikacji w **Settings → Pages** repozytorium ustaw źródło na `gh-pages` → `/ (root)`. Slajdy będą dostępne pod adresem:

```
https://jaroslawchodak.github.io/agentic-sociology/presentation.html
```

### Wariant „ręczny" (bez `quarto publish`)

```bash
quarto render presentation.qmd --output-dir docs
git add docs/
git commit -m "Publish slides"
git push
```

W **Settings → Pages** wybierz źródło `main` → `/docs`. Jeśli wybierasz ten wariant, **odkomentuj** linię `/docs` w `.gitignore`.

## Struktura prezentacji

```
Wstęp                 → ramy, „co to NIE jest"
Część 1               → LLM ↔ Czat ↔ Agent (analogie, pętla działania)
Część 2               → krajobraz narzędzi + modele chmurowe vs lokalne
Część 3               → pliki kontekstowe, Skills, MCP, skrypty
Część 4 (showcase)    → Case Study ESS: pełny pipeline analityczny
Część 5               → galeria zastosowań w socjologii
Część 6               → friction: etyka, AI Disclosure
Zamknięcie            → trzy obserwacje + Q&A
```

## Licencja

Materiały dydaktyczne — do swobodnego użytku akademickiego z zachowaniem atrybucji autora.
