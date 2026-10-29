# Matma E8

Practice app for the egzamin ósmoklasisty in math, set up for a student now in grade 7 (exam in May 2028, 125 min, 30 pts). The interface is in Polish.

**Exam date:** CKE publishes the exact 2028 date around August 2027. When it does, update `EXAM_DATE` in `index.html` and set `EXAM_DATE_FINAL=true`. The home page then drops the "ok." (approximately) label.

## How to open
- **On this computer:** double-click `index.html`. It opens in any browser and needs no installation. The fonts need internet; without it the app still works with system fonts.
- **As a link:** the same file is published as a private claude.ai page that you can share.

Progress (solved tasks, mock exam scores) is saved in the browser. A different browser or device starts from zero.

## What's inside
- **10 minut dziennie** (daily practice): 5 tasks a day, including up to 2 from "Do powtórki". The rest are new tasks, easier ones and weaker topics first. Finishing all 5 adds a day to the streak; missing a day resets it.
- **Przerobione w szkole** (covered at school): tick the topics already covered in class. The daily set and the mock exam then use only those topics. Other topics can still be practised. If too few topics are ticked to build a 30-point paper, the mock exam says so.
- **Ćwiczenia** (topic drills): 250 original tasks in 17 topics (9–18 per topic). Topics that usually span grades 7 and 8 are split, so a grade-7 student can tick only what was covered: Graniastosłupy / Ostrosłupy, Statystyka / Kombinatoryka i prawdopodobieństwo, Pola wielokątów / Koło i okrąg, Układ współrzędnych / Symetrie. Tasks in other topics that need the Pythagorean theorem only appear once that topic is ticked. All tasks are written in CKE task formats (A–D, prawda/fałsz, dobieranie, open numeric answers, open written tasks). Each task is marked łatwe / średnie / trudne (easy / medium / hard). A topic starts with the easy ones and can be filtered by level. Each task has step-by-step hints and a worked solution. Wrong answers go to the "Do powtórki" list.
- **Nowe liczby** (new numbers): 74 computational tasks can generate fresh numbers, with hints, solution and answer options recalculated. A task shows its original numbers the first time; after that, and on "Spróbuj jeszcze raz", it gets new ones, so answers can't just be remembered. The mock exam also uses new numbers.
- **Egzamin próbny** (mock exam): a random paper with 15 closed tasks (1 pt each) plus open tasks worth 15 pts, so 30 pts in total. It runs on a 125-minute timer with pause. Numeric answers are checked automatically. Written tasks are self-scored against the examiner's criteria.
- Links to the official CKE materials, in the suggested study order.

## Adding tasks
Tasks live in the `BANK` array inside `index.html`. Copy an existing task of the same `type` and give it a new unique `id`:
- `abcd`: `o` (4 options), `a` ('A'–'D')
- `pf`: `st` (2 statements), `a` (['P','F'])
- `match`: `g` (two option groups), `a` (e.g. ['A','2'])
- `num`: `a` (number), `p` (points), optional `unit`
- `open`: `crit` (one line per point)

Optional `need` (e.g. `['pitagoras']`) hides the task until those topics are ticked as covered. To give a task new numbers, add a function to `GEN` (see the examples there): it returns the changed `q`, `a`, `h`, `s`, and for A–D tasks `o` with the correct answer first and `a:'A'`. Add the task's difficulty (1–3) to the `LVL` map below the bank; without it, it counts as 2. Every task also needs `t` (topic id), `q` (question), `h` (hints) and `s` (solution). Use `f(a,b)` for fractions and `rt(x)` for square roots.

## Official materials
- Informator (PDF): https://zspptaszkowa.gminagrybow.pl/files/53/informator-matematyka.pdf
- Past papers: https://cke.gov.pl/egzamin-osmoklasisty/arkusze/
- Revision task sets: https://www.cke.gov.pl/egzamin-osmoklasisty/materialy-dodatkowe/zestawy-zadan-powtorkowych/
- Practice papers: https://www.gov.pl/web/edukacja/arkusze-do-egzaminu-probnego-dla-osmoklasisty--matematyka
