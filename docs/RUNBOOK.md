# RUNBOOK — operacje i awarie

Ten repo nie hostuje niczego — jest dokumentacją. "Awaria" tutaj oznacza awarię PLATFORMY
(`reykjawwwik.is` i client buildy), nie tego repo. To repo samo w sobie nie może "spaść".

## Podstawy
- Produkcja: https://reykjawwwik.is
- Client buildy: https://cars.reykjawwwik.is · https://tours.reykjawwwik.is · https://beauty.reykjawwwik.is
- Kod aplikacji: osobne, prywatne repo [`spirit-way-bloom`](https://github.com/kamiljan11/spirit-way-bloom) (patrz README → Source)
- Ten repo: github.com/kamiljan11/reykjawwwik-platform (tylko dokumentacja)
- Sekrety: nie dotyczy tego repo (brak kodu, brak env)

## Deploy
Nie dotyczy tego repo. Deploy platformy opisany (jeśli w ogóle) w `spirit-way-bloom`.

## Healthcheck
```bash
curl -I https://reykjawwwik.is
curl -I https://cars.reykjawwwik.is
curl -I https://tours.reykjawwwik.is
curl -I https://beauty.reykjawwwik.is
```
200 na wszystkich = platforma i client buildy wstają. Jeśli któryś nie odpowiada: problem jest
w `spirit-way-bloom` / hostingu, nie tutaj.

## Typowe awarie
| Objaw | Pierwszy krok |
|---|---|
| `reykjawwwik.is` lub client build nie odpowiada | Sprawdz hosting/DNS platformy — poza tym repo. Zacznij od `spirit-way-bloom`. |
| README tego repo mówi co innego niż strona | Zaufaj stronie (zweryfikuj `curl`/przeglądarką), popraw README w PR |
| Ktoś pyta o kod/cennik/CRM | Nie tutaj — `spirit-way-bloom` jest prywatne, potwierdź czy pytający ma mieć dostęp |

## Kontakty
- Wlasciciel: MAS Group, mountainallservice@gmail.com
- Klient: [imie, kontakt, SLA jesli jest]
