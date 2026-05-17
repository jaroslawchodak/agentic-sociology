# Nowy warsztat socjologa — Systemy agentowe AI w procesie badawczym

**Podtytuł:** Od rozmowy z czatem do delegowania zadań — co każdy socjolog powinien wiedzieć o agentach AI, nie znając ani jednej linijki kodu.

> Nie musisz być programistą. Nie musisz instalować terminala. Nie musisz rozumieć, jak działają sieci neuronowe. Ten półwarsztat jest po to, żebyś wyszedł z sali z jasnym obrazem: **co te narzędzia robią, do czego się nadają, gdzie leżą granice i od czego zacząć jutro rano.** Jeśli potrafisz otworzyć folder na komputerze i napisać pytanie po polsku — jesteś przygotowany.

---

## Grupa docelowa, format i czas

| Parametr | Wartość |
|---|---|
| **Grupa docelowa** | Pracownicy naukowi i doktoranci nauk społecznych i humanistycznych. Poziom: początkujący w obszarze AI (znają ChatGPT/Claude w przeglądarce, nie znają systemów agentowych). |
| **Czas trwania** | 75 minut (z 5–10 min buforem na pytania = 80–90 min). |
| **Format** | Półwarsztat / wykład inspiracyjny z pokazem na żywo. Bez live codingu, bez instalacji u uczestników. |
| **Wymagania uczestnika** | Ciekawość. Laptop niekonieczny. |
| **Pokaz** | Jedno **case study ESS (European Social Survey)** wykonane wcześniej z agentem, pokazane jako screencast + komentarz. |

---

## Cele edukacyjne

Po warsztacie uczestnik:

1. **Rozróżnia** LLM, czat w przeglądarce i system agentowy — i rozumie, dlaczego ta różnica zmienia sposób pracy badawczej.
2. **Zna nazwy i przeznaczenie** głównych narzędzi z rodziny *Agentic AI* (Claude Code, Codex, OpenCode) oraz wie, czym są edytory/terminale z obsługą agentów (Zed, Warp).
3. **Rozumie nowy paradygmat**: pracę na projekcie z plikami kontekstowymi (`CLAUDE.md`, `AGENTS.md`, `CONTEXT.md`, `WORKFLOW.md`) zamiast „zaczynania rozmowy od zera".
4. **Widzi konkretne, namacalne zastosowanie** — pełną demonstrację pracy agenta na danych European Social Survey (pobranie → czyszczenie → analiza → wykres → raport).
5. **Wie**, kiedy wybrać model komercyjny, a kiedy lokalny — i dlaczego ma to znaczenie dla danych wrażliwych.
6. **Jest świadomy/-a napięć etycznych** i zna obowiązkową formułę *AI Disclosure Statement*.

---

## Agenda (75 minut)

| Blok | Czas | Co się dzieje |
|---|---:|---|
| **0. Otwarcie** | 3 min | Po co tu jesteśmy. Co to NIE jest (kurs Pythona, warsztat terminala). Co to JEST (mapa nowego krajobrazu narzędzi). |
| **1. LLM ↔ Czat ↔ Agent** | 8 min | Trzy pojęcia, jedna analogia: **mózg bez rąk → rozmówca → pracownik**. Agent = LLM + pamięć + narzędzia + pętla działania. |
| **2. Zmiana paradygmatu: od rozmowy do projektu** | 7 min | Stara praca: okno czatu, kopiuj-wklej. Nowa: folder badawczy, agent widzi pliki, zostawia ślad. Reguła trzech rozmów: *jeśli wpisujesz to trzeci raz — zrób z tego skill*. |
| **3. Krajobraz narzędzi** | 6 min | Claude Code, Codex, OpenCode + edytory/terminale (Zed, Warp). Analogia: **OpenCode to pracownik, Zed to biuro**. |
| **4. Modele: komercyjne vs lokalne** | 4 min | Schemat decyzyjny: dane wrażliwe → lokalnie (Ollama); literatura, granty → chmura. |
| **5. Pliki kontekstowe, Skills, MCP** | 8 min | Trzy poziomy „pamięci": prompt → projekt → pliki kontekstowe (.md). Skills jako szablony powtarzalnych zadań. MCP jako uniwersalne wtyczki do baz (OpenAlex, Zotero, PubMed). Mini-przykład pliku `.md` na slajdzie. |
| **6. POKAZ: Case Study ESS** | 18 min | **GŁÓWNA DEMONSTRACJA.** Pełny pipeline na danych European Social Survey: agent pobiera dane → standaryzuje zmienne → liczy korelacje → robi regresję OLS → generuje wykres → pisze raport w Markdownie + zostawia audit log. Patrz sekcja *„Opis pokazu"* niżej. |
| **7. Zastosowania w socjologii — galeria 360°** | 6 min | Mapa „od pytania badawczego do publikacji": literatura, planowanie, dane jakościowe (transkrypcja, anonimizacja, kodowanie), dane ilościowe, pisanie, granty, recenzowanie. |
| **8. Friction: etyka i napięcia** | 8 min | Dwa głosy: Stanford 2026 („the most exciting moment ever to be a PhD student") vs 419 badaczy jakościowych odrzucających GenAI w *reflexive thematic analysis*. Nature Reviews Bioengineering: *writing is thinking*. |
| **9. Zaawansowane — tylko zajawka** | 3 min | CrewAI, LangChain/LangGraph, LlamaIndex/ChromaDB, fine-tuning. „Tam można dojść — dziś tylko zaglądamy przez szybę". |
| **10. AI Disclosure + Q&A** | 4 min | Wręczenie formuły disclosure. Pytania z sali. |

**Razem: ~75 min** + bufor 5–10 min na Q&A.

---

## Opis pokazu: Case Study ESS (blok 6, 18 min)

To **pokaz wcześniej wykonany** (screencast z pauzami i komentarzem) — nie próbujemy odtwarzać razem z salą. Uczestnicy patrzą i widzą, że to nie jest science fiction.

**Folder demo:**

```text
ess-demo/
  AGENTS.md         # konstytucja agenta (rola, zasady, audyt)
  CONTEXT.md        # opis projektu i pytanie badawcze
  WORKFLOW.md       # procedura analizy ESS
  prompt-wykonawczy.md
  data_raw/         # surowe dane ESS
  data_clean/       # po czyszczeniu
  scripts/          # skrypty pomocnicze (napisane przez agenta)
  outputs/          # raport + wykres
  agent_logs/       # ślad decyzji metodologicznych
```

**Pytanie badawcze:**

> Czy osoby o wyższym zaufaniu społecznym, lepszym zdrowiu, wyższym dochodzie i wyższym poziomie edukacji deklarują wyższe zadowolenie z życia?

**Model:** `stflife ~ ppltrst + health + hinctnta + eduyrs + agea + gndr + cntry`

**Etapy pokazu:**

1. **Punkt wyjścia (1 min)** — Otwieramy folder. Pokazujemy `AGENTS.md`, `CONTEXT.md`, `WORKFLOW.md`. Komunikat: „Te pliki to nie kod. To brief po polsku, jak dla nowego pracownika."
2. **Krok 1 — Agent czyta kontekst (1 min)** — Uruchamiamy prompt wykonawczy. Agent sam mówi, w jakim badaniu siedzi i co zamierza zrobić.
3. **Krok 2 — Pobieranie / sprawdzenie danych (2 min)** — Agent szuka pliku ESS w `data_raw/`, jeśli go nie ma, zapisuje **instrukcję pobrania**. Komunikat: „Agent zna swoje granice — nie wymyśla danych."
4. **Krok 3 — Standaryzacja i czyszczenie (3 min)** — Agent pisze skrypt Pythona, który: zachowuje 8 zmiennych, rekoduje braki ESS (`77, 88, 99`) na `NaN`, sprawdza zakresy, robi wariant complete-case. Pokazujemy tabelę braków. **Slajd uspokajający:** *„Nie musisz tego napisać — to agent zaprojektował skrypt na podstawie WORKFLOW.md"*.
5. **Krok 4 — Analiza (3 min)** — Korelacja `stflife ↔ ppltrst`, regresja OLS z `cntry` jako efektem stałym. Pokazujemy tabelę współczynników.
6. **Krok 5 — Wizualizacja (2 min)** — Agent generuje wykres (`outputs/wykres-stflife-ppltrst.png`) — średnie `stflife` dla poziomów `ppltrst`.
7. **Krok 6 — Raport + audit log (3 min)** — Otwieramy `outputs/raport-ess-stflife.md` (gotowy Markdown z 12 sekcjami: pytanie, dane, zmienne, czyszczenie, opis, korelacja, wykres, regresja, interpretacja, ograniczenia). Następnie `agent_logs/decyzje-ess-stflife.md` — agent zostawia ślad: jakie pliki czytał, jakie skrypty uruchomił, co wyprodukował. **Komunikat: „To jest nasza polisa ubezpieczeniowa dla recenzentów."**
8. **Komentarz końcowy (3 min)** — Co w tym pokazie jest *socjologicznie* ważne: agent NIE pisze interpretacji za nas, NIE formułuje wniosków przyczynowych z danych przekrojowych, sam zaznacza ograniczenia (wagi ESS, skale porządkowe traktowane jako liczbowe, `cntry` jako proste FE zamiast modelu wielopoziomowego). „Agent zna metodologię, bo my mu ją wpisaliśmy w `AGENTS.md`."

**Klucz dydaktyczny:** uczestnik widzi *cały* proces od pustego folderu do publikowalnego raportu — bez ani jednej linijki kodu napisanej przez prowadzącego.

---

## Dobre praktyki — minimum sanitarne

1. **Nie wymyślaj. Pokazuj źródła.** Każde twierdzenie agenta musi mieć cytat z konkretnego dokumentu/danych.
2. **Zostaw ślad pracy.** Agent zapisuje, co czytał, co uruchamiał, co wyprodukował (`agent_logs/`).
3. **Chroń dane respondentów.** Wywiady → lokalna anonimizacja przed chmurą. Ollama jest tu wymogiem etycznym, nie luksusem.
4. **Oddzielaj cytat, streszczenie, interpretację.**
5. **Pracuj na kopiach.** Agent nie nadpisuje danych źródłowych.

### AI Disclosure Statement (obowiązkowy)

> This manuscript was developed through a human-AI collaborative writing process. The conceptual framework, core arguments, theoretical choices, and analytical judgments are the sole intellectual contribution of the author. AI tools were used to assist with drafting, organization, and citation management. The author takes full responsibility for all claims and any errors.

---

## Co uczestnik wynosi z sali

- Mapę pojęciową: LLM → Czat → Agent.
- Konkretny dowód, że agent może wykonać pełen pipeline analizy danych ESS — od pobrania do raportu.
- Wiedzę, że punkt wejścia to plik `.md`, nie kurs Pythona.
- Listę głównych narzędzi i kiedy po nie sięgać.
- Formułę *AI Disclosure*.
- Świadomość, że pytania, interpretacja i odpowiedzialność zostają po jego stronie.
