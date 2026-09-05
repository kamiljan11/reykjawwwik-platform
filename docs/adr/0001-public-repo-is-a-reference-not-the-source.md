# ADR-0001 — Ten publiczny repo to referencja, nie źródło aplikacji

Data: 2026-09-05 | Status: przyjęte (widoczne w historii repo od pierwszego commita "Showcase README")

**Kontekst:** `reykjawwwik-platform` jest publiczne na GitHubie (portfolio/audyt), ale sama
platforma (SaaS na `reykjawwwik.is`) ma cennik, umowy klientów i logikę CRM, których Kamil nie
chce trzymać w publicznym repo.

**Decyzja:** `reykjawwwik-platform` zawiera wyłącznie dokumentację (README, ARCHITECTURE, ADR,
RUNBOOK, GLOSSARY) — zero `package.json`, zero `src/`. Rzeczywisty kod platformy żyje w osobnym
repo `spirit-way-bloom` i jest nazwany wprost w sekcji "Source" README, opisany jako
"proprietary and private" (commit `docs: sprostowanie sekcji Source`, 2026-08-10) — **stan
zweryfikowany 2026-09-05: `github.com/kamiljan11/spirit-way-bloom` zwraca 404 bez autoryzacji,
czyli faktycznie prywatne** (w przeciwieństwie do analogicznych repo `homehug-services` /
`maskalkulator` przy `quickfix-iceland` / `mas-group`, które w tej samej chwili są publiczne —
patrz ich odpowiednie `docs/quality/BACKLOG.md`).

**Rozważone alternatywy:**
- *Umieścić kod platformy w tym samym publicznym repo* — odrzucone: platforma ma cennik,
  konkretne umowy klientów i dane CRM, których Kamil nie chce publicznie widocznych.
- *Prywatne monorepo bez żadnej publicznej wizytówki* — odrzucone: portfolio/audyt potrzebuje
  czegoś konkretnego do pokazania bez proszenia o dostęp za każdym razem.
- *Nazwać repo źródłowe, ale nie potwierdzać jego widoczności* — odrzucone tutaj: skoro dało się
  łatwo zweryfikować (żądanie HTTP bez autoryzacji), lepiej napisać w README fakt sprawdzony niż
  hedge ("access may be restricted"), jak zrobiono to w `quickfix-iceland`/`mas-group`.

**Konsekwencje:**
- CI w tym repo (`quality.yml`) sprawdza tylko treść dokumentacji (gitleaks, Semgrep) — kroki
  npm (lint/typecheck/test/build) pomijają się przez `hashFiles('package.json')`, bo nie ma czego
  budować. Zielona bramka oznacza "brak sekretów w docs", nie "platforma działa".
- Jedyny wiarygodny "smoke test" tego repo to zewnętrzny `curl -I` na cztery domeny (patrz
  `docs/RUNBOOK.md`) — nie lokalny test frameworka.
- Ten repo NIE ma osobistego podpisu (imienia) w README/LICENSE — właściciel wskazany jako
  "MAS Group" (patrz `docs/RUNBOOK.md`, sekcja Kontakty; zgodne z commitem `chore: remove
  personal attribution and contact from public files`, 2026-08-04). Nie dopisuj z powrotem
  osobistego imienia/linku w plikach publicznych tego repo bez świadomej decyzji Kamila.

**Pułapki dla przyszłego siebie:**
- Nie dopisuj tu kodu "tymczasowo, żeby coś pokazać" — jeśli platforma kiedyś ma być publiczna,
  to osobna, świadoma decyzja (i osobny ADR), nie commit poboczny.
- Widoczność `spirit-way-bloom` może się zmienić — jeśli kiedyś stanie się publiczne, zaktualizuj
  README (usuń/przeformułuj "and private") zamiast zostawić nieaktualne zapewnienie.
