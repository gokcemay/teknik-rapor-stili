# English technical report style

Based on the Google developer documentation style guide, adapted for technical
reports. Use American spelling and punctuation throughout.

Contents:
1. Voice, person, and tense
2. Sentence and paragraph construction
3. Word choice: replace these
4. Punctuation
5. Numbers, units, and dates
6. Headings, lists, tables, and figures
7. Code, filenames, and placeholders
8. References and links
9. Quick self-check

---

## 1. Voice, person, and tense

- **Active voice, named agent.** "The tribometer recorded the friction
  coefficient every 10 ms," not "The friction coefficient was recorded."
  Passive is acceptable when the agent is genuinely irrelevant or unknown, or
  when the object is the true topic of the sentence — but never use it to hide
  who did the work.
- **Person.** Reports are impersonal by default. Use "you" only in procedures,
  SOPs, and operating instructions, where the reader performs the action.
  Avoid "we" in results and discussion; if the research team must be named,
  "the authors" or the organization name is safer. Never use "I".
- **Tense.**
  - Completed work, experiments, and observed results → past tense.
    "Three specimens failed during run-in."
  - Standing facts, system behavior, what the data shows → present tense.
    "DLC coatings reduce adhesive wear on polymer substrates."
    "Figure 3 shows the wear track profile."
  - Never write future tense for product behavior or unreleased features. For
    planned work, name the phase or date: "Phase 2 covers PA6-GF specimens,"
    not "We will later test PA6-GF."
- **No anthropomorphism.** Software, machines, and data do not want, think,
  know, see, or decide. "The controller aborts the run" is fine;
  "the controller realizes the load is too high" is not.

## 2. Sentence and paragraph construction

- **Conditions first.** "If the surface roughness exceeds Ra 1.6 µm, repeat the
  polishing step." Not the reverse — the reader must not start acting before
  learning the condition applies.
- One idea per sentence. Target 15–25 words; break anything past ~30.
- Put the subject and verb close together and early. Avoid stacking three or
  more prepositional phrases before the main verb.
- Paragraphs: 3–5 sentences, one topic each, with the topic sentence first.
  A reader skimming only the first sentence of each paragraph should still get
  the argument.
- Avoid nominalization. "We measured" beats "measurement was performed";
  "decided" beats "made a decision regarding."

## 3. Word choice: replace these

| Avoid | Use |
|---|---|
| in order to | to |
| utilize, leverage | use |
| prior to, subsequent to | before, after |
| a number of, a variety of | several, or the actual number |
| is able to, has the ability to | can |
| allows you to, enables you to | lets you, or rewrite around the action |
| please, simply, just, easily, obviously | delete |
| note that, it should be noted that | delete and state the fact |
| e.g., i.e., etc., via | for example; that is; and so on; through |
| significant (without statistics) | state the measured change |
| robust, powerful, seamless, cutting-edge | describe the measurable property |
| and/or | pick one, or write "A, B, or both" |
| terminate, execute (for people-facing actions) | stop, run |
| desire, wish | want, need |

Other word rules:

- No contractions ("don't", "it's") in report register.
- No ampersand (&) as a conjunction, including in headings.
- Expand every abbreviation at first use: "diamond-like carbon (DLC)". After
  that, use the abbreviation consistently. Don't expand it again later.
- Don't add "(s)" for optional plurals — write the plural, or rewrite.
- Inclusive terms: allowlist/blocklist, primary/replica, placeholder name.
- Latin scientific names and *in situ*, *ex situ* stay italic.

## 4. Punctuation

- **Serial (Oxford) comma**: "coating thickness, hardness, and adhesion."
- Em dash — no spaces around it in American style — for a strong break.
  En dash for ranges only when a hyphen would be ambiguous; prefer words:
  "from 5 N to 20 N" rather than "5–20 N" in body text.
- Semicolons join two closely related independent clauses. Use sparingly.
- Colon introduces a list or an example; the text before it must be a complete
  sentence.
- Periods and commas go inside quotation marks; put end punctuation and
  quotation marks **outside** link text.
- Use quotation marks for short-work titles; italics for full-length works.
- Parenthetical asides should be short. If a parenthesis runs longer than a
  clause, make it its own sentence.

## 5. Numbers, units, and dates

- Spell out zero through nine in ordinary prose; use numerals for 10 and above.
  **Always use numerals with units, in tables, and in measurements**: "3 mm",
  "1 N", "5 specimens" in a results table.
- Decimal point is a period: `0.25`. Thousands separator is a comma: `12,500`.
  (This is the opposite of Turkish — see `tr-style.md`.)
- Put a nonbreaking space between value and unit: 100 m, 25 °C, 1.5 GPa.
  Exceptions: %, °, and angular units attach directly — 45°, 12%.
- Use SI units and the correct case: `N`, `mm`, `s`, `°C`, `Pa`. Not `mm.`
  or `MM`. Compound units with a middle dot or slash consistently:
  mm³/(N·m).
- Report significant figures consistently with instrument resolution. Don't
  copy every decimal the software prints.
- Give uncertainty explicitly: "0.42 ± 0.03 (n = 3, standard deviation)".
- Ranges: "from 20 °C to 80 °C". Don't mix "between 20 to 80".
- **Dates**: "August 18, 2026" in prose, or ISO 8601 (`2026-08-18`) in tables,
  logs, and filenames. Never `08/18/2026`.
- **Times**: 24-hour clock with time zone in logs (`14:30 UTC+3`); in prose,
  "2:30 p.m." is acceptable but be consistent.
- Version numbers: italicize the variable part — version 1.4.*x*.
- Mathematical variables italic, operators and units upright: *v* = 0.1 m/s.

## 6. Headings, lists, tables, and figures

**Headings**

- Sentence case: "Wear test results and discussion".
- Descriptive and standalone — a heading must make sense in a table of
  contents, without the surrounding text.
- Task headings use a gerund or imperative ("Preparing the specimens" /
  "Prepare the specimens"); conceptual headings use a noun phrase.
- Don't skip levels, and don't use a heading as the antecedent of the first
  sentence ("This is done by..." — say what "this" is).
- No terminal punctuation in headings; no numbers-only headings.

**Lists**

- Numbered for sequences and ranked items; bulleted otherwise; description
  lists for term–definition pairs.
- Introduce every list with a lead-in sentence ending in a colon.
- Keep items parallel: all noun phrases, or all imperatives — not mixed.
- Capitalize the first word of each item. Use a period only if any item is a
  full sentence; then punctuate all items the same way.
- 2–9 items is comfortable. If you exceed nine, group them or use a table.
- Don't bury a procedure inside a bulleted list — procedures are numbered.

**Tables**

- Caption above the table, numbered: "Table 3. Pin-on-disk test parameters."
- Every table must be referenced in the text before it appears.
- Column headers in sentence case; put units in the header, not in every cell:
  "Load (N)".
- Align numbers on the decimal point; keep the same number of decimals in a
  column. Use an em dash or "n/a" for missing data — never a blank cell whose
  meaning is ambiguous.
- Tables are for comparison. If a table has one column, it's a list.

**Figures**

- Caption below the figure, numbered: "Figure 2. Wear track profile of the
  as-printed ABS specimen."
- Provide alt text describing what the figure shows, not "chart" or "image".
- Include scale bars on micrographs and axis labels with units on plots.
- Don't rely on color alone to distinguish series; add markers or line styles.
- Prefer vector formats (SVG, PDF) or high-resolution raster.

## 7. Code, filenames, and placeholders

- Code font for filenames, paths, parameters, function and class names,
  commands, console output, HTTP status codes, and environment variables.
- Placeholders in all caps with underscores, in code font:
  `SPECIMEN_ID`, `OUTPUT_PATH`. Explain each placeholder right after the block.
- Introduce a code block with a sentence ending in a colon or period.
- Indicate omitted code with a language-appropriate comment, not an ellipsis.
- Show the command and, when it matters, the expected output — separately, so
  the reader can copy the command cleanly.
- Filenames: lowercase, hyphens between words, no spaces.

## 8. References and links

- Descriptive link text naming the destination; never "click here", "this
  link", or a bare URL in prose.
- Cite standards fully at first mention: "ASTM G99-23", "ISO 4287:1997".
- Cite the source, not a secondary summary of it, whenever available.
- Keep one citation style throughout the report and match the venue's
  requirement (IEEE, APA, journal template) if there is one.
- For internal cross-references, use the numbered element: "see Section 3.2",
  "Table 4", not "see above".

## 9. Quick self-check

Before delivering, verify:

1. Every claim has a number, a source, or is clearly framed as an inference.
2. No sentence exceeds ~30 words; no paragraph exceeds five sentences.
3. Every figure and table is numbered, captioned, and cited in the text.
4. Every abbreviation is expanded once, at first use.
5. Units, decimals, and dates follow one consistent convention.
6. No banned filler words (Section 3) survive.
7. Headings are sentence case and self-explanatory.
8. Nothing is stated in future tense as a promise.
9. Uncertainty and test conditions accompany every reported measurement.
