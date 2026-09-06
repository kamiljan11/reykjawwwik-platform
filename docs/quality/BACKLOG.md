# Quality backlog — reykjawwwik-platform

Świadomie odłożone przy PG v3 github-ready (2026-09-05). Nie blokuje merge'a tego PR.

| # | Co | Dlaczego odłożone | Ryzyko jak zostanie |
|---|---|---|---|
| 1 | `eslint.config.mjs` (strict baseline) dodany przez bootstrap, ale nie ma żadnego pliku JS/TS do lintowania | Repo nie ma kodu — placeholder na wypadek, gdyby kiedyś tu wylądował kod | Zerowe — plik jest bierny |
| 2 | Stack platformy (React/Supabase/Vercel) nie zweryfikowany z kodu | Kod jest w `spirit-way-bloom`, prywatne — ten agent nie miał dostępu (poza zakresem) | Niskie — `docs/ARCHITECTURE.md` oznacza to wprost jako niezweryfikowane |

## Co NIE jest długiem (świadomie tak zostaje)
- Brak `package.json`/testów/builda — to repo nie ma kodu z założenia (patrz ADR-0001).
- Brak osobistego podpisu (imienia) w README/LICENSE/RUNBOOK — świadoma decyzja z 2026-08-04 (`chore: remove personal attribution and contact from public files`), nie przeoczenie. Nie "poprawiaj" tego dodając imię z powrotem.
