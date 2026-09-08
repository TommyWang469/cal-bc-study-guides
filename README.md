# Cal BC Study Guides

Weekly LaTeX practice sheets for a Calculus BC class — questions, work space, answer key, and a
source list, all in one file per week.

## What's here

| File | Sections | Notes |
|---|---|---|
| `study-guide-4.3-4.6.tex` | 4.3–4.6 | Current template. 18 problems + three original problems, four screenshot figures |
| `study-guide-3.4-3.9.tex` | 3.4–3.9 | First guide in the one-file layout. Has the AP-packet and multiple-choice layouts |
| `study-guide-2.1-2.5.tex` | 2.1–2.5 | Predates the one-file layout; keeps the TikZ figure macros |
| `answer-key-2.1-2.5.tex` | 2.1–2.5 | Retired split answer key, kept for reference |
| `WORKFLOW.md` | — | How a guide gets built, start to finish. The spec |

Figures are named `fig-<sections>-q<n>.png` — the guide they belong to, then the question number
they carry in it. They must sit beside the `.tex` when it is compiled.

> **Missing file:** `fig-3.4-3.9-q17.png` is not in this repo. It was lost on 2026-09-08 when the
> 4.3–4.6 guide wrote its own `fig-q17.png` over it, back when figures used flat `fig-q<n>.png`
> names and the two guides collided at 17. Names are namespaced per guide now, so it cannot
> recur. To restore it, copy `fig-q17.png` out of the 3.4–3.9 Overleaf project and save it here
> under the new name. Until then `study-guide-3.4-3.9.tex` will not compile.

## Building

```sh
tectonic study-guide-4.3-4.6.tex
```

Produces the PDF in place. Any LaTeX toolchain works; the documents use only `geometry`,
`amsmath`, `amssymb`, `enumitem`, `graphicx` and `multicol`.

## Structure of a guide

```
questions + figures + work space
\clearpage
Tommy's Questions          three original problems, easy → hard
\clearpage
answer key                 answers only for the numbered problems,
                           full worked solutions for the original ones
\clearpage
% === SOURCELIST ===
where each question came from
```

Problems are renumbered `1…N` and every textbook reference is stripped, so a student solving the
sheet can't tell which section a question came from. Sources appear in exactly one place: the
list on the final page, so anyone who misses a problem can look up its neighbours for more
practice.

`WORKFLOW.md` has the rest — the work-space macros, the verification steps, and the gotchas
worth not rediscovering.

## Note on sources

The numbered problems are transcribed from a course textbook and the figures are cropped from
its pages; they are reproduced here for classroom practice. Rights to that material belong to
its publisher. The problems under **Tommy's Questions**, the answer keys and `WORKFLOW.md` are
original.
