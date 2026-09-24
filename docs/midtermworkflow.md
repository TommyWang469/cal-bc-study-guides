# Midterm 1 Study Guide Workflow

This workflow is for the cumulative Calculus BC Midterm 1 guide. It replaces the weekly question-selection rules in [WORKFLOW.md](WORKFLOW.md) where the rules below differ.

## 1. Scope

- Use the exact worksheet named **26-27** in `sources/course-calendar/Calendar BC 2019 and on-2.xlsx` (path relative to the repository root).
- The midterm entry is dated September 28, 2026 and says “MidTerm 1 (2.1 - 4.4).”
- Cover every numbered section from 2.1 through 4.4, including 2.2 and 3.5 even though those two labels do not appear in the 26-27 calendar.
- Treat 3.9 as the Chapter 3 review section represented by the supplied 3.9 pages.
- The calendar also refers to a separate WS 2.5b on composition of limits. It is not a numbered textbook section and its worksheet is not in this folder, so it is outside the three-question-per-section build unless that worksheet is supplied.

## 2. Question count

For each section from 2.1 through 4.2:

1. Choose two complete textbook exercises.
2. Choose one question from the supplied AP packet that tests the same section's skill.
3. Count a multi-part textbook exercise as one question.

For 4.3 and 4.4:

- Do not use the three-question rule.
- Carry over every 4.3 and 4.4 textbook exercise already transcribed in `guides/4.3-4.6/study-guide-4.3-4.6.tex`.
- This produces three exercises from 4.3 and six from 4.4.

After selecting the original midterm questions, append every supplied Section Quiz screenshot question to its matching section. Keep the screenshot order within each section. If a screenshot contains a graph, redraw it clearly in black and white or crop the graph without the Schoology interface.

The finished guide therefore has 99 questions:

- 32 newly selected textbook exercises for 2.1-4.2
- 16 AP packet questions for 2.1-4.2
- 9 required textbook exercises for 4.3-4.4
- 42 Section Quiz questions from the supplied screenshots

Do not add Tommy's Questions or any other original problems.

## 3. Excluding spreadsheet questions

Read the entire 26-27 worksheet, not another school year. For each section, combine every numbered problem appearing under Solve, Recommended Continued Practice, Opener, Challenge, and IP. If any part of an exercise appears, exclude the whole exercise number.

The exclusion sets used for this guide are:

| Section | Excluded textbook exercises |
|---|---|
| 2.1 | 1, 5, 9, 12, 13, 14, 16, 17, 21, 25, 31, 33, 35, 37, 38, 41, 44 |
| 2.3 | 13, 25, 29, 35, 37, 39, 45, 49, 55, 62, 63, 68 |
| 2.4 | 5, 7, 8, 9, 15, 21, 22, 23, 35, 39, 40 |
| 2.5 | 1, 3, 7, 8, 10, 13, 20, 23, 24, 27, 28, 33, 43, 50, 55, 60 |
| 3.1 | 1, 3, 7, 8, 9, 11, 15, 17, 19, 22, 26 |
| 3.2 | 1, 5, 11, 13, 21, 23, 27, 29, 32, 33, 34, 39, 41, 43, 50, 51, 53 |
| 3.3 | 1, 9, 15, 27, 34, 51, 53, 55, 56, 57, 61, 65, 66, 67, 68 |
| 3.4 | 1, 7, 9, 15, 22, 23, 25, 28, 29, 31, 34, 35, 38, 45, 49 |
| 3.6 | 5, 9, 15, 17, 27, 29, 31, 39, 49, 54, 55, 59, 65, 73, 81, 83, 87 |
| 3.7 | 1, 3, 7, 10, 13, 17, 21, 23, 24, 27, 31, 32, 34, 40 |
| 3.8 | 1, 5, 7, 9, 13, 14, 15, 17, 18, 21, 23, 26, 27, 28, 38, 39, 45, 46 |
| 3.9 | 5, 6, 15, 17, 26, 38, 39, 49, 65, 72 |
| 4.1 | 1, 3, 5, 7, 9, 10, 21, 23, 27, 33, 37, 38, 43, 45, 50, 51 |
| 4.2 | 1, 3, 8, 9, 14, 15, 20, 21, 23, 25, 26, 28, 30, 33, 35, 37, 40, 41 |

Sections 2.2 and 3.5 have no calendar entries, so their supplied textbook pages provide the eligible pool. The 4.3-4.4 carry-over rule overrides the spreadsheet exclusion rule.

## 4. Source handling

1. Find sources under `sources/textbook/`, `sources/ap-packets/`, `sources/section-quizzes/`, and `sources/course-calendar/`. The quiz screenshots are also combined in `sources/section-quizzes/section-quizzes-2.1-4.4.pdf`; the textbook screenshot supplement is in `sources/textbook/textbook-screenshot-supplement.pdf`. Run markitdown on every PDF, spreadsheet, and screenshot first.
2. If a scan has no text layer, render it at readable resolution and inspect the image.
3. Transcribe the full exercise, including all parts and necessary conditions.
4. Preserve mathematical meaning while removing textbook exercise ranges and theorem numbers from the student-facing question.
5. Use the AP packet filename/page and handwritten AP identifier in the final source list.
6. Never invent a missing expression, choice, graph value, or answer.

## 5. Student-facing layout

- Separate every section's question group with a plain black horizontal rule and a section/topic heading, such as “Section 3.8: Related Rates.”
- Within each section, place a “Section Quizzes” subheading after the original questions and append that section's screenshot questions one by one.
- Number the complete guide continuously from 1 through 99.
- Do not print textbook problem numbers or source labels on the practice or answer pages.
- Put blank work space after every question.
- Keep multiple-choice answer choices with the question.
- Put the answer key after all questions.
- Put the source list last, after the SOURCELIST marker.
- The source list must map every guide number to its textbook section/exercise or AP packet page/question.

## 6. Answer verification

- Check algebraic limits, derivatives, extrema, and numerical values with SymPy.
- For theorem questions, separately verify hypotheses and interval restrictions.
- For graph-construction questions, verify that at least one stated example satisfies every value, derivative-sign, differentiability, and concavity condition.
- For AP multiple choice, solve the problem independently before recording the letter.
- Correct source-guide claims that are stronger than the conditions. For example, 4.4 exercise 37 permits a period-two arch pattern but does not uniquely force that function, so the key should say “one valid graph.”

## 7. Final checks

1. From the repository root, run `cd guides/midterm-1`, then compile with `tectonic midterm1-study-guide-2.1-4.4.tex`.
2. Confirm that the rendered question and answer numbers both run from 1 through 99 with no gaps.
3. Confirm exactly one workspace macro follows each question.
4. Confirm the source list has exactly one entry for every question.
5. Recheck every eligible textbook selection against the 26-27 exclusion sets.
6. Search everything before the source-list marker for leaked source labels or exercise numbers.
7. Render every PDF page and inspect it for clipping, overlap, missing glyphs, orphan pages, and unreadable math.
8. Extract page text and flag any page with unusually little text for manual review.

## 8. Files delivered

- `guides/midterm-1/midterm1-study-guide-2.1-4.4.tex`
- `guides/midterm-1/midterm1-study-guide-2.1-4.4.pdf`
- `docs/midtermworkflow.md`
