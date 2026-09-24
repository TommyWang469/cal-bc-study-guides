# Calculus BC Study Guides

Practice guides, class source materials, and the workflows used to prepare them.

## Study guides

Each folder keeps the guide's TeX source, available PDF, and required figures together.

| Guide | Files |
|---|---|
| Midterm 1: Sections 2.1–4.4 | [PDF](guides/midterm-1/midterm1-study-guide-2.1-4.4.pdf) · [TeX](guides/midterm-1/midterm1-study-guide-2.1-4.4.tex) |
| Related rates | [PDF](guides/related-rates/related-rates-study-guide.pdf) · [TeX](guides/related-rates/related-rates-study-guide.tex) · [Overleaf ZIP](guides/related-rates/related-rates-overleaf.zip) |
| Sections 4.3–4.6 | [PDF](guides/4.3-4.6/study-guide-4.3-4.6.pdf) · [TeX](guides/4.3-4.6/study-guide-4.3-4.6.tex) |
| Sections 3.4–3.9 | [TeX and available figure](guides/3.4-3.9/) |
| Sections 2.1–2.5 | [TeX and legacy separate answer key](guides/2.1-2.5/) |

**Existing missing figure:** `guides/3.4-3.9/fig-3.4-3.9-q17.png` was already missing before this reorganization. That guide cannot compile until the figure is restored from the old Overleaf project. The other figures remain beside their TeX files.

## Source materials

| Folder | Contents |
|---|---|
| [Section quizzes](sources/section-quizzes/) | [Combined 42-page PDF](sources/section-quizzes/section-quizzes-2.1-4.4.pdf), with section bookmarks; renamed originals in `screenshots/` |
| [Textbook](sources/textbook/) | Homework PDFs by section; [9-page screenshot supplement](sources/textbook/textbook-screenshot-supplement.pdf) for sections 2.2, 3.5, 4.1, and 4.2; renamed originals in `screenshots/` |
| [AP packets](sources/ap-packets/) | Original AP packet PDFs, retaining their source filenames |
| [Course calendar](sources/course-calendar/) | Calendar workbook and a September–October screenshot from the 2026–2027 sheet |

Quiz screenshot names use the section and the question number displayed in Schoology, for example `section-2.1-quiz-question-02.png`. Numbering gaps reflect the supplied screenshots; no missing questions were invented. Textbook screenshot names use the section and an ordered screenshot number, not a printed textbook page number.

The combined PDFs preserve every original screenshot at full resolution, one image per page. All original PNGs are retained. [File move history](docs/file-moves.csv) records every old filename, new location, and original SHA-256 checksum.

## Workflows and building

- [Weekly study-guide workflow](docs/WORKFLOW.md)
- [Midterm 1 workflow](docs/midtermworkflow.md)

Compile from the guide's own folder so relative figure paths resolve:

```sh
cd guides/4.3-4.6
tectonic study-guide-4.3-4.6.tex
```

For Overleaf, upload the TeX and figures from the same guide folder, or use the related-rates ZIP. New guides should follow the current workflow's questions → answer key → source list layout; older guides retain their original content.

Source exercises and figures are reproduced for classroom practice; rights remain with their respective publishers.
