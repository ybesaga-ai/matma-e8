# Matma E8

Practice app for the egzamin ósmoklasisty in math (11 May 2027, 125 min, 30 pts). The interface is in Polish.

## How to open
- **On this computer:** double-click `index.html`. It opens in any browser and needs no installation. The fonts need internet; without it the app still works with system fonts.
- **As a link:** the same file is published as a private claude.ai page that you can share.

Progress (solved tasks, mock exam scores) is saved in the browser. A different browser or device starts from zero.

## What's inside
- **Ćwiczenia** (topic drills): 120 original tasks in 13 topics, written in CKE task formats (A–D, prawda/fałsz, dobieranie, open numeric answers, open written tasks). Each task has step-by-step hints and a worked solution. Wrong answers go to the "Do powtórki" list.
- **Egzamin próbny** (mock exam): a random paper with 15 closed tasks (1 pt each) plus open tasks worth 15 pts, so 30 pts in total. It runs on a 125-minute timer with pause. Numeric answers are checked automatically. Written tasks are self-scored against the examiner's criteria.
- Links to the official CKE materials, in the suggested study order.

## Adding tasks
Tasks live in the `BANK` array inside `index.html`. Copy an existing task of the same `type` and give it a new unique `id`:
- `abcd`: `o` (4 options), `a` ('A'–'D')
- `pf`: `st` (2 statements), `a` (['P','F'])
- `match`: `g` (two option groups), `a` (e.g. ['A','2'])
- `num`: `a` (number), `p` (points), optional `unit`
- `open`: `crit` (one line per point)

Every task also needs `t` (topic id), `q` (question), `h` (hints) and `s` (solution). Use `f(a,b)` for fractions and `rt(x)` for square roots.

## Official materials
- Informator (PDF): https://zspptaszkowa.gminagrybow.pl/files/53/informator-matematyka.pdf
- Past papers: https://cke.gov.pl/egzamin-osmoklasisty/arkusze/
- Revision task sets: https://www.cke.gov.pl/egzamin-osmoklasisty/materialy-dodatkowe/zestawy-zadan-powtorkowych/
- Practice papers: https://www.gov.pl/web/edukacja/arkusze-do-egzaminu-probnego-dla-osmoklasisty--matematyka
