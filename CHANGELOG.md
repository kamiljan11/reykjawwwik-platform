# Changelog

Format: [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), wersjonowanie: [SemVer](https://semver.org/).
Kazdy PR dopisuje zmiany do [Unreleased]; przy release przenosimy pod numer wersji z data.

## [Unreleased]
### Added
- Pipeline jakosci: CI (build/lint/typecheck/test/semgrep/audit/licencje), Claude review na PR, szablony dokumentacji
- `docs/ARCHITECTURE.md`, `docs/adr/0001-public-repo-is-a-reference-not-the-source.md`, `LICENSE`, `docs/GLOSSARY.md`, `.github/pull_request_template.md`

### Changed
- README: badge CI, sekcja "what this repository is", healthcheck curl na wszystkie 4 domeny (reykjawwwik.is + 3 client buildy, wszystkie zweryfikowane 200)
- `docs/RUNBOOK.md` wypelniony realnymi danymi — zachowany istniejacy wlasciciel "MAS Group" (bez imienia, zgodnie z commitem z 2026-08-04)

### Fixed
- `e2e/smoke.spec.ts` usuniety — byl martwy (wymagal `@playwright/test`, ktorego repo bez `package.json` nie ma; nigdy nie mogl sie uruchomic)
