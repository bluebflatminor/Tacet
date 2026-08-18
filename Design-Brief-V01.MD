# TACET — A Read-Primary Musical Language

**Design Brief, Phonology, and Notation Firewall**
Version 0.1 · Solbakken Research Initiative · CC0

*"Tacet" is the notation instruction that a part is present in the score and silent in
performance. That is exactly what this language's evidential channel is.*

*Naming history: this project was called "Recto" through v0.3. Renamed at v0.4 — **musica recta** is established terminology for the un-inflected notes of the Guidonian gamut, opposed to **musica ficta**, the notes requiring accidentals. Since Tacet's entire mechanism is accidental spelling, the collision sat directly in the semantic domain and would have misled any musicologist reading the title. Caught in external review, not by the author.*

---

## 1. Purpose

Tacet is a constructed language whose primary channel is musical notation and whose
secondary channel is performance. It is designed as a **test instrument**, not as an
auxiliary language.

The claim it is built to test:

> Benchmarks computed on rendered output cannot adjudicate comprehension, because
> rendering is a lossy projection and the loss is not visible from inside the rendered
> space.

Tacet makes this demonstrable rather than arguable. It carries grammatical categories
that are unambiguously distinct on the page and **provably identical in audio**. An
evaluator working from performance — human or machine — cannot recover them. Not
because the task is hard, but because the information is not present.

This is instrument substitution exhibited as an artifact.

---

## 2. Pre-Registered Kill Conditions

Stated before any design decision below can be motivated by them.

**K1 — Human legibility.** If fluent notation readers (n ≥ 8, conservatory-level or
equivalent) cannot recover Tier-2 categories from unseen page utterances at ≥ 80%
after ≤ 6 hours of structured training, the read-primary claim fails. The project
stops or the inventory is rebuilt.

**K2 — Firewall integrity.** If any evaluator recovers a Tier-2 category from
*audio alone* above chance, the firewall has leaked. That is a design defect, not a
finding, and the offending contrast is removed from Tier 2.

**K3 — Diagnosticity.** If models fail the matched serial control language (§6) at
rates comparable to their failure on Tacet, the result measures unfamiliarity, not
parallel structure. The finding is void.

K3 is the one most likely to fire. It is the reason the control exists.

---

## 3. Two Tiers, Strictly Separated

The whole argument lives in the gap between these. They are never conflated, never
averaged, and never reported as a single score.

### Tier 1 — Audible Layer
Survives rendering. Present in page and performance alike.

| Parameter | Inventory | Carries |
|---|---|---|
| Interval from reference | 12 chromatic classes | lexical root |
| Duration class | 5 (𝅘𝅥𝅯 𝅘𝅥𝅮 𝅘𝅥 𝅗𝅥 𝅝) | lexical vowel-analogue |
| Voice count | 1–4 simultaneous | phrase-level scope |
| Metrical position | 4 positions per bar | grammatical case |
| Articulation | staccato / legato / accent | illocutionary force |

Pitch is **relative**, never absolute. Any utterance is valid at any transposition.
Absolute pitch is ~1 in 10,000; relative pitch is near-universal, and Solresol's
fixing to absolute solfège tokens was a design error worth not repeating.

### Tier 2 — The Tacet Layer (the firewall)
Distinct on the page. **Identical under any rendering.**

| Contrast | Page form | Audio form | Carries |
|---|---|---|---|
| Enharmonic spelling | G♯ vs A♭ | identical | **evidentiality** |
| Stem direction | ↑ vs ↓ | identical | animacy |
| Duration spelling | 𝅘𝅥. vs 𝅘𝅥‿𝅘𝅥𝅮 | identical | aspect (perfective / imperfective) |
| Tie across barline | tied vs single long note | identical | clause boundary |
| Beaming group | 4+4 vs 3+3+2 | identical (equal durations) | constituent bracketing |
| Voice assignment at unison | crossed vs uncrossed | identical | topic continuity |
| Clef | treble vs alto at same sounding pitch | identical | register / honorific |

**Evidentiality on enharmonic spelling is the load-bearing feature.** Sharp-spelling
marks witnessed; flat-spelling marks reported. Many natural languages grammaticalize
evidentiality obligatorily, so this is not an invented category — it is a real one,
placed in a channel that audio cannot carry. Two utterances meaning *I saw the boat
sink* and *I am told the boat sank* are visually unmistakable and acoustically
indistinguishable.

That pair is the exhibit. Everything else is scaffolding around it.

---

## 4. Well-Formedness Constraints

1. **Transposition invariance.** No utterance's meaning depends on absolute pitch.
2. **Enharmonic obligatoriness.** Every lexical root must be spelled, therefore every
   utterance is marked for evidentiality. There is no unmarked form. (This is what
   makes the loss under rendering total rather than partial.)
3. **Voice ceiling of four.** Beyond four simultaneous voices, reading collapses to
   serial scanning; four is the ceiling attested by fluent chorale readers and by
   prompt-book practice.
4. **No Tier-2 contrast may be recoverable from Tier-1 distribution.** If sharp-spelled
   roots correlate with any audible parameter, K2 has fired.
5. **Metrical position assigns case**, which buys free voice-order the way inflection
   buys free word-order.

---

## 5. Morphology in the Vertical

Speech is strictly serial. Notation is not. This is the affordance no spoken language
has, and Tacet is built on it.

- **Top voice** — lexical content. The melodic line.
- **Inner voices** — grammatical morphology: tense, number, negation.
- **Bass voice** — discourse frame. Modulation marks topic shift, quoted speech,
  counterfactual mood.

A four-voice chord is one glyph, taken in a single fixation. Whether this is genuine
parallel holding or fast interleaving is an **open empirical question** — it is the
question Kivy treated as a disanalogy and that Churchill's overlap notation, the
theatrical prompt book, and the Vilna Talmud page suggest is wrong. Tacet is partly
built to settle it.

---

## 6. The Matched Serial Control

Required by K3. Same lexicon, same grammar, same information content — but:

- One voice, strictly serial.
- Tier-2 categories marked by explicit inline diacritics rather than by spelling,
  stem, or beam.
- Identical utterance set, identical test items.

If evaluators handle the control and fail Tacet, the finding is about parallel
structure. If they fail both, the finding is about unfamiliarity and is worthless.

---

## 7. Build Order

Spine first. At every stage something exists that can fail.

1. Inventory freeze (Tier 1 + Tier 2) — **this document**
2. Minimal contrast set: 12 evidentiality-paired utterances, page + rendered audio
3. Matched serial control for the same 12
4. Human baseline (K1)
5. Firewall audit (K2)
6. Closed test corpus, 100 novel utterances, pre-registered scoring
7. Lexicon expansion — unbounded, and only after 1–6 pass

Full scope is the destination. Steps 1–6 are the instrument, and they are what
prevents this from becoming a beautiful document that never passed a gate.

---

## 8. Known Risks

- **K3 is the likely failure.** Unfamiliarity is a strong confound and the control may
  not fully absorb it.
- **Acquisition.** Nothing survives that is not acquired. Solresol died childless.
  Tacet does not solve this and does not claim to — it is an instrument, not an
  auxiliary language, and its lifespan is the lifespan of the test.
- **Semantic cost.** Adding reference to music may kill what made music worth using.
  Solresol's antonym-by-retrograde is elegant *because* it exploits musical structure,
  and it is also the moment the system stops being music and becomes a code wearing
  music. Tacet will face the same boundary. The question to hold is not "does it
  parse" but **"what had to be killed to make it parse."**
- **Human baseline first.** If fluent readers cannot do it either, the model result
  measures nothing.

---

## 9. Open Items

- [ ] Lexical root inventory — target size for v0.2
- [ ] Negation. There is no obvious musical primitive for *not*. Candidate: retrograde
      of the inner voice. Unresolved.
- [ ] Whether stem-direction animacy survives engraving-software normalization
      (LilyPond will re-stem by default — a real threat to Tier 2 integrity)
- [ ] Rendering spec: which synthesis path counts as canonical performance
- [ ] Whether the control language should also be page-based or text-based

---

*No claim in this document has passed a gate. No citation here has been DOI-verified.
This is v0.1 of a design, not a result.*
