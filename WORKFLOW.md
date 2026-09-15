# Weekly Study Guide — Workflow

How to build one of these from scratch. Written after the 2.1–2.5 guide (August 2026), which
is the working example — copy that `.tex` as the starting template every week.

---

## 1. What I need from Tommy

| Input | Why |
|---|---|
| Photo of the **Recommended Continued Practice** table | Tells me which problems, and how they cluster |
| Photos of **every textbook page** those problems live on | I transcribe from these; a missing page = a missing problem |
| Photos of any **figures** referenced (graphs) | Graph problems can't be transcribed, they get cropped out as images |
| Any **AP packet** pages the teacher wants folded in | These are scanned PDFs; render at 300 dpi and read them, they have no text layer |

The practice table groups sections into **two clusters** (e.g. `2.1 + 2.3` in one box, `2.4 + 2.5`
in the other). That grouping matters — it decides the two original questions (see §3).

If a page is missing, say so and build everything else. Never invent a problem to fill a hole.

---

## 2. The teacher's rules — non-negotiable

These came directly from the teacher after seeing the first draft. **Students must not be able to
tell where a question came from while they are solving it.** Sources appear in exactly one place:
the source list on the final page (§4). Nowhere else in the document — not in a heading, not in a
margin, not in the answer key.

- ❌ No section headings (`Exercises 2.1`, `Exercises 2.3`, …)
- ❌ No textbook problem numbers (`33.`, `45.`, …)
- ❌ No `Exer. 11–24:` prefixes on instruction lines — keep the instruction, drop the range
- ❌ No textbook theorem numbers — `the intermediate value theorem (2.26)` → `the intermediate value theorem`
- ❌ Nothing that says "from the textbook" in the prose
- ✅ Questions numbered **1, 2, 3 … N** in one continuous run
- ✅ Answer key uses the **same numbering**
- ✅ **Blank work space** after every question — students solve on the sheet itself

### Plain practice layout

These formatting rules apply to every guide, including topic-specific and midterm guides,
unless Tommy explicitly requests a different format.

- **Use plain black text on white paper.** No colored headings, highlighted panels, shaded
  backgrounds, or question-number boxes. Use simple bold numbers such as `1.` and `2.`.
- **Keep figures grayscale.** Preserve all labels and distinctions needed to solve the problem;
  verify that curves or regions remain distinguishable without color.
- **Start directly with practice questions and blank work space.** A short title or header and
  name/date line are fine; do not add a separate cover or introduction page.
- **Do not add instructional sections** such as “A reliable setup,” “Recognize the model,”
  “Before you finish,” formula summaries, strategy tables, worked examples, or review notes
  before or between the practice questions.
- Keep instructions, conditions, supplied formulas, and diagrams that belong to the question
  itself. Do not add solution hints to the practice pages.
- Keep the document order: **practice questions → answer key → source list**. The answer key
  and source list each start on a new page. “Just questions for practice” removes introductory
  teaching material; it does not remove the workflow's answer key or source list unless requested.

`related-rates-study-guide.tex` is the current example of this plain, questions-first layout.
If an older template uses color or introductory material, remove it when creating a new guide.

The number map (`8 = 2.1 #17`, …) is no longer a hidden comment block — it renders, once, as the
source list on the last page. One copy only: a comment-block map *plus* a printed list is two
copies of the same data and they drift.

---

## 3. Tommy's Questions

Every guide ends with a section called **Tommy's Questions**: three original problems Tommy and I
write. They form a difficulty ramp, and each is built differently on purpose (Tommy's call, from
the 3.4–3.9 guide):

- **Tommy 1 — one problem with parts (a)–(d)**, covering the first cluster of the practice
  table. Breadth. Every part should be gettable.
- **Tommy 2 — a single question, no parts, as hard and creative as it can be made**, covering
  the second cluster. Depth.
- **Tommy 3 — a single question, harder still.** The ceiling of the set.

Label them `Tommy 1.` / `Tommy 2.` / `Tommy 3.` — **no** "(Sections 2.1 and 2.3)", that leaks
the source.

For Tommy 2 and Tommy 3, model each on a *math Integration Bee* problem: it looks impossible,
brute force genuinely does not terminate, and one slick observation collapses it to a clean exact
answer. What the 3.4–3.9 guide used:

- *Tommy 2* — the infinitely nested radical $y=\sqrt{\sec x+\sqrt{\sec x+\cdots}}$. Seeing that
  the tail **is** $y$ turns the tower into $y^2=\sec x+y$; one implicit differentiation finishes
  it. Trap: keeping the extraneous negative root.
- *Tommy 3* — $f(x)=x/\sqrt{1+x^2}$ composed with itself 100 times. Composing twice shows
  $f_n(x)=x/\sqrt{1+nx^2}$, so the tower of 100 chain rules collapses to one product rule.
  Trap: reaching for the chain rule immediately — the composition must be *simplified* first.

Keep Tommy 2 and 3 inside the unit's toolkit — the difficulty comes from the idea, never from a
technique the class has not been taught. Give each a genuinely different way in, so a student who
misses one still has a shot at the other.
- **Never write framing or a hint into the question.** No "this one is meant to be hard," no
  "there is a short way in," no "if you find yourself doing X, stop." Every one of those hands
  over the observation the problem exists to test, and on Tommy 2 the observation *is* the whole
  problem. State the setup, state what to find, stop. The only text allowed alongside a question
  is a condition it needs to be well-posed (e.g. "which you may assume converges") — that is
  mathematics, not a steer. All explanation lives in the answer key.
  *(I got this wrong on the first 3.4–3.9 draft; Tommy cut it.)*
- Build Tommy 1 as one problem with parts rather than four unrelated questions.
  What worked in the 2.1–2.5 guide:
  - *Tommy 1* — four different attacks on the same point `x = 3`: factor-and-cancel, conjugate
    multiply, one-sided limits with absolute value, sandwich theorem.
  - *Tommy 2* — one function `f(x) = (x²−4)/(x²−x−6)` carried through all four parts: classify
    its discontinuities, one-sided infinite limits, limits at ±∞ and asymptotes, then IVT.
- **Build in one trap worth teaching.** Tommy 2 has a hole at `x = −2` that is a discontinuity but
  *not* a vertical asymptote — the exact thing students get wrong when both sections are tested
  together.
- In the answer key these get **full worked steps**. The textbook problems get **answers only**.

---

## 4. The file

**One file, not two.** Questions and answer key live in the same `.tex` — one thing to paste into
Overleaf, one PDF to track, and no way for the two halves to drift out of sync.

```
study-guide-<range>.tex    questions + TikZ figures + work space
                           \clearpage
                           answers only for 1…N, then Tommy's full solutions
                           \clearpage
                           % === SOURCELIST ===
                           where each question came from
```

Each part starts on its own page (`\clearpage`) so the question pages can still be printed and
handed out alone. The old `answer-key-<range>.tex` split is retired — the 2.1–2.5 pair is still
the content template, but paste the key into the bottom of the guide when copying it forward.

### The source list — last page

**Every guide ends with the list of where its questions came from**, so a student who wants more
practice on the one thing they got wrong can find it in the book. Without it the guide is a dead
end: a student knows they missed #14 and has no way to look up its neighbours.

- Section, then problem number, in the guide's own numbering: `14 — 2.4 #23`.
- Group by section so the clusters are visible at a glance — that's what makes it usable for
  finding *more* problems, not just the one.
- `Tommy 1` and `Tommy 2` are listed as **original — not in the textbook**, so nobody hunts for
  a problem that doesn't exist.
- Graph problems reused across sections (§7) get **both** locations listed.
- Open the list with one line naming the sections covered, e.g. *"These questions come from
  Sections 2.1, 2.3, 2.4 and 2.5. Try the surrounding problems for more practice."*

The `% === SOURCELIST ===` marker on the line above it is what the leak grep (§6) cuts at — it
must stay, or the grep starts reporting the source list as a leak and gets ignored.

Shared preamble pieces worth copying forward:

- `\gaxes{xmin}{xmax}{ymin}{ymax}` — draws axes with ticks for a graph problem
- `hole` / `fdot` / `cline` tikz styles — open circle, filled dot, curve
- `\prob{n}` + the `probs` list — the numbered-question layout
- `\headnote{...}` — the italic instruction line above a group
- `\wsS \wsM \wsL \wsG` — the four work-space sizes, **defined together near the top so all
  spacing can be rescaled by editing four numbers**

Work-space sizing that felt right:

| Macro | Size | For |
|---|---|---|
| `\wsS` | 3 cm | one- or two-step limits |
| `\wsM` | 4.5 cm | messier algebra, or parts (a)(b)(c) |
| `\wsL` | 6.5 cm | sketch a graph, long argument |
| `\wsG` | 2 cm | short answers beside a printed graph (the paper right of the figure is already blank) |

Use `\vspace*` (starred!) so a blank is never silently swallowed at a page break.

---

## 5. Steps

1. **Read the practice table.** Write the list out; note the two clusters.
2. **Transcribe every problem from the page photos.** Crop and zoom rather than squinting — see §7.
3. **Crop graph problems out of the source photo and save them as PNGs** in the repo folder,
   named `fig-q<n>.png`, then `\includegraphics` them. Do not describe a graph in words; the
   student can't solve from prose. Crop tight to the axes — leave the textbook's problem number
   and the neighbouring problems' text outside the crop, or the figure leaks the source.
   (TikZ redraws are no longer required; the old `\gaxes` / `hole` / `fdot` / `cline` styles in
   the 2.1–2.5 file still work if a figure ever needs to be drawn from scratch.)
4. **Renumber 1…N** and strip all source references (§2). Apply the plain practice layout:
   black text, grayscale figures, and questions first with no introductory review material.
5. **Write the two Tommy questions** (§3).
6. **Write the answer key** after `\clearpage` in the *same file*, same order — answers only for
   1…N, full steps for Tommy's.
7. **Write the source list** on the last page (§4) — built from the transcription in step 2, not
   reconstructed afterwards from memory.
8. **Verify** (§6) — this is not optional.
9. **Tommy compiles in Overleaf** and sends the PDF back; I render and check it (§6).

---

## 6. Verification — never skip

**`tectonic` is installed** (`/opt/homebrew/bin/tectonic`) — `tectonic study-guide-<range>.tex`
compiles in place, no Overleaf round trip needed. Compile it myself, render the pages, and look
at them *before* sending anything (that is how the stray blank page after Tommy 3 was caught in
the 4.3–4.6 guide). `pdflatex` is still absent; don't reach for it. The rest of the checks:

**Check every answer with sympy, not by eye:**
```python
import sympy as sp
x = sp.symbols('x')
sp.limit((x**2-x-6)/(x**2-9), x, 3)      # 5/6
sp.limit(f, x, 3, '-')                    # one-sided
```
Every numeric answer in the key must come from a computation, never from mental arithmetic
typed straight into the document.

**Cross-check the two halves agree** (same file now, so both greps read it):
```sh
grep -o '\\prob{[0-9]*}'    study-guide-*.tex | sed 's/[^0-9]//g' | tr '\n' ' '
grep -o '\\ansitem{[0-9]*}' study-guide-*.tex | sed 's/[^0-9]//g' | tr '\n' ' '
```
Same numbers, same order, or something got dropped.

**Scan for source leaks before shipping** — everything *above* the source list, which is the one
place sources are allowed:
```sh
sed '/SOURCELIST/,$d' study-guide-*.tex | grep -v '^\s*%' \
  | grep -nE 'Exer\.|Exercises|Sections|\(2\.[0-9]+\)'
```
Must return nothing.

**Check the source list is complete:** it needs one entry per `\prob{}`, `1…N` with no gaps, plus
the two Tommy entries. A student looking up the problem they missed and finding it absent is the
failure this list exists to prevent.

**Confirm every problem has work space:** count `\prob{}` against `\ws[SMLG]` occurrences.

**Check the practice layout:** the first page must contain Question 1, with no introductory
review page. Inspect the TeX and rendered PDF for colored text, shaded boxes, colored figures,
and added teaching sections. Confirm that required question instructions and figure labels
remain readable, and that the answer key and final source list are still present.

**Check the compiled PDF by rendering it** (PyMuPDF is installed, poppler is not):
```python
import pymupdf
d = pymupdf.open('file.pdf')
for i, p in enumerate(d): p.get_pixmap(dpi=110).save(f'p{i+1}.png')
```
Then actually look at the pages — that's how the layout problems and the `TA` → `Tommy` rename
mismatch were caught.

**Catch orphan blank pages by page text length**, not by eye — a trailing `\wsL \wsL` that
overflows produces a page holding nothing but its page number, which reads as a misprint:
```python
print([i+1 for i, p in enumerate(d) if len(p.get_text().strip()) < 60])
```
Must be empty. The fix is a `\clearpage` before the block that overflowed, not less work space.

---

## 7. Gotchas learned the hard way

**Reading the photos**
- macOS screenshot filenames contain a **narrow no-break space** (U+202F) before `AM`/`PM`.
  A literal path string fails; glob it instead: `glob.glob('.../Screenshot 2026-08-20 at 8.47*.png')`.
- Some photos are stored rotated. If PIL shows sideways text, `Image.rotate(90, expand=True)`;
  `ImageOps.exif_transpose` does nothing when there's no EXIF.
- To read small print, crop the region and upscale: `im.crop(box).resize((w*4, h*4), Image.LANCZOS)`.
- To settle "is there a curve there or not," count pixels instead of guessing — that's how the
  missing left branch in the `x → 0⁻` graph was confirmed.

**Figure filenames must carry the guide's section range**
- `fig-<range>-q<n>.png`, e.g. `fig-4.3-4.6-q17.png` — never bare `fig-q17.png`. All the guides
  live in one flat folder, question numbers restart at 1 every week, so two guides that both
  have a figure on question 17 will overwrite each other. That is not hypothetical: building the
  4.3–4.6 guide destroyed the 3.4–3.9 guide's `fig-q17.png` this way, and it was unrecoverable
  (no Trash copy, source screenshots already deleted, no compiled PDF to pull it back out of).
- Before writing any figure, check whether the name is already taken: `ls fig-*` first.

**Textbook structure**
- **The book reuses figures across sections.** In chapter 2, the 2.5 graph problems are the same
  pictures as 2.1 #31–40. Define each figure once as a `\newcommand` and call it from both places.
- That reuse shows up in the final guide as the same graph appearing under two different numbers.
  It's correct (the questions asked differ) but looks like a misprint — flag it to Tommy each time.

**The book's own headnotes are sometimes wrong**
- Exercises 4.3 #35–40 are headed *"Sketch the graph of a **differentiable** function…"* while
  #35 itself states `f'(0) is undefined`. The 4.4 version of the same exercise type says
  *continuous*, which is what the conditions actually require. I used "continuous" and flagged
  the change to Tommy. Transcribe faithfully, but when a headnote contradicts the problem under
  it, say so instead of copying the contradiction onto the worksheet.

**Answers read off a graph**
- Any answer that depends on reading a picture gets **flagged for Tommy to confirm against the
  actual book**, with the specific doubt named. Three were flagged in the 2.1–2.5 guide; he
  confirmed two and corrected one. That exchange is cheap and catches real errors.
- Never invent a value to fill a gap. Say what the figure does and doesn't show.

**Keeping copies in sync**
- Tommy edits in Overleaf; those edits do **not** come back to the local `.tex` automatically.
  The `TA's Questions` → `Tommy's Questions` rename lived only in his Overleaf copy for a while.
  After he sends a PDF, diff what it says against the local file and sync.

---

## 8. Quick checklist

- [ ] Plain black text, simple question numbers, no shaded boxes, and readable grayscale figures
- [ ] Question 1 starts on the first page; no cover, setup tutorial, formula summary, or review section
- [ ] Practice questions first, then answer key, then source list; key and sources start on new pages
- [ ] Practice table read; both clusters identified
- [ ] Every listed problem transcribed; missing pages reported
- [ ] Graph problems cropped to `fig-q<n>.png` in the repo folder, cropped tight enough not to
      show the textbook problem number, and listed for Tommy to upload to Overleaf
- [ ] Numbered 1…N; zero section/exercise/theorem references above the `SOURCELIST` marker
- [ ] Source list on the last page: every 1…N entry, grouped by section, Tommy 1/2 marked original
- [ ] Work space after every question, `\vspace*`, four sizes
- [ ] Tommy 1 and Tommy 2 written, one per cluster, with a real trap in one of them
- [ ] Answer key in the same `.tex` after `\clearpage`: same numbering, answers-only for 1…N,
      full steps for Tommy's
- [ ] Every answer verified by sympy
- [ ] Leak grep clean; guide ↔ key numbering matches
- [ ] Graph-based answers flagged to Tommy for confirmation
- [ ] PDF rendered and eyeballed after he compiles
