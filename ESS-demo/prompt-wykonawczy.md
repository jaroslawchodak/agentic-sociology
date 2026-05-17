# Prompt wykonawczy: podstawowa analiza ESS

Skopiuj i wklej agentowi pracującemu w folderze projektu.

```
text
Wykonaj demonstracyjną analizę ESS zgodnie z AGENTS.md, CONTEXT.md i WORKFLOW.md.

Pytanie badawcze:
Czy osoby o wyższym zaufaniu społecznym, lepszym zdrowiu, wyższym dochodzie i wyższym poziomie edukacji deklarują wyższe zadowolenie z życia?

Użyj wariantu podstawowego: tylko ESS, poziom indywidualny respondentów.

Model:
stflife = ppltrst + health + hinctnta + eduyrs + agea + gndr + cntry

Wykonaj:
1. sprawdzenie lub instrukcję pobrania danych ESS;
2. opis zmiennych;
3. czyszczenie danych i tabelę braków;
4. tabelę opisową;
5. korelację stflife z ppltrst;
6. prosty wykres;
7. regresję OLS;
8. krótką, ostrożną interpretację;
9. listę ograniczeń.

Zapisz wyniki:
- raport: outputs/raport-ess-stflife.md
- log decyzji: agent_logs/decyzje-ess-stflife.md
- wykres, jeśli powstanie: outputs/wykres-stflife-ppltrst.png

Na końcu odpowiedzi podaj, które pliki utworzono i których kroków nie udało się wykonać.

```
