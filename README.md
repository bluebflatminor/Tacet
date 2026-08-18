# Tacet

**A constructed language written in musical notation, where an obligatory grammatical
category cannot be recovered from performance.**

Solbakken Research Initiative · CC0 · v0.5, August 2026

---

> **tacet** *(Latin, "it is silent")* — the notation instruction that a part is present in
> the score and produces no sound. In this project, the name of a language whose evidential
> marking is exactly that: printed, obligatory, and absent from every performance.

---

## What this is

Tacet is a small constructed language in staff notation. Evidentiality — whether a claim
is **witnessed** or **reported** — is carried entirely by enharmonic spelling. Sharp-side
spelling marks witnessed; flat-side marks reported. The marking is obligatory: every
utterance is marked, and there is no neutral form.

The consequence is that rendering does not *degrade* the category. It deletes it.

| | Page | Audio |
|---|---|---|
| **A.** *I saw the boat sink.* | `A#4 B#4 D#5 \| D#5 B#4 G#4` | `[70, 72, 75, 75, 72, 68]` |
| **B.** *I am told the boat sank.* | `Bb4 C5 Eb5 \| Eb5 C5 Ab4` | `[70, 72, 75, 75, 72, 68]` |

Unmistakably distinct to any reader. Byte-identical as files.

Tacet is a **test instrument**, not an auxiliary language. It is not designed to be
learned, spoken, or adopted. It exists to make a claim about measurement demonstrable
rather than arguable: *a scorer working from rendered output reports these as the same
sentence, is wrong, and has no channel through which to discover it.*

---

## Results

**1. The mechanism holds.** Both utterances map to identical MIDI note numbers over a
sustained 66. Written to standard MIDI files and hashed: byte-identical. Verified —
`midi_diff2.py`, with the pitch mapping asserted against 13 known values before any
comparison is run.

**2. A leak was found in the canonical render.** MIDI carries a key-signature meta-event
(`FF 59`) encoding sharps versus flats as a signed byte. An engraver that infers a key
from spelling produces divergent files with no audio involved. Suppressing the *printed*
key signature does not suppress the meta-event. The canonical render therefore cannot be
MIDI; it must be raw audio.

**3. The firewall is a temperament artifact.** Enharmonic identity is a property of
twelve-tone equal temperament, not of sound. In meantone or just intonation the comma is
real and audible, and a flexible-pitch performer renders A and B differently. **The loss
is continuously tunable by rendering convention** — total under one, nil under another,
everything else held fixed.

Result 3 is the part that appears to be new. Not that rendering loses information, which
is a truism, but that the size of the loss is a dial rather than a fact.

---

## What is stipulated, and what is not

Stipulated, and therefore evidence of nothing: that evidentiality is obligatory, that
spelling carries it, that 12-TET is canonical, the lexicon, the case system. A constructed
system can be built to fail in any chosen way. **Demonstrating a failure you designed
proves nothing.**

Not stipulated:

- the MIDI meta-event, a property of a format nobody here designed
- the syntonic comma, which is acoustics
- **Dutch.** Verb pairs such as *wieden* / *wiedden* are homophonous, and readers recover
  tense from orthography alone at no additional cost.
  Brysbaert, M., Grondelaers, S., & Ratinckx, E. (2000). *Acta Psychologica* 105(1),
  31–56. [doi:10.1016/s0001-6918(00)00047-0](https://doi.org/10.1016/s0001-6918(00)00047-0)
  — DOI resolved 17 Aug 2026.

A natural language already carries an obligatory grammatical category in a channel speech
cannot reach. Tacet only makes the loss adjustable. **Dutch is the finding; Tacet is the
illustration.**

---

## Progression

### CoNexus / 3D volumetric computing (October 2025) — closed
Not part of Tacet, but its methodological ancestor. A white paper and its own falsification
document were written in the same month. The practice of writing the kill condition
alongside the proposal starts there, and every gate in this repository descends from it.

### Recto v0.1 (design brief)
Purpose, tier structure, and pre-registered kill conditions **written before** any design
decision could be motivated by them. K1 human legibility, K2 firewall integrity, K3
diagnosticity. Negation flagged as unsolved.

### Recto v0.2 (lexicon and grammar)
Twenty roots on an interval-pair grid, with antonyms falling out as sign-inversions —
GO/COME, GIVE/TAKE, DAY/NIGHT. Metrical position assigns case. Tense in the inner voice.
The exhibit pair constructed in full with LilyPond source. Negation proposed as a
grace-note appoggiatura and simultaneously flagged as an affix in costume — music does not
appear to have a native primitive for *not*.

### Recto v0.3 (three substrates)
Built on English, then rebuilt on Japanese and Malagasy to test whether the loss belonged
to rendering or to English. It belongs to rendering — but the **severity varies**:

| Substrate | Obligatory category | Rendered form is |
|---|---|---|
| English | evidentiality (stipulated) | vaguer |
| Malagasy | voice/trigger (native) | ambiguous between three readings |
| Japanese | register (native) | **not a well-formed utterance** |

A benchmark scoring rendered output reports all three as passing, and is wrong three
different ways. Malagasy's fixed VOS order also broke the v0.2 case system, exposing it as
accusative Indo-European assumption presented as neutral design.

### v0.4 — first gate run
`midi_diff2.py` executed. Result 1 passed; Result 2 (the meta-event leak) found. The
first run of the script reported a **false failure** caused by a bug in the author's own
accidental parser (B♭4 computed as 69 rather than 70). It was caught by inspecting the
numbers rather than the verdict. The script now asserts its pitch mapping before testing
anything.

### v0.5 — renamed, external review
**Recto → Tacet.** *Musica recta* is established terminology for the un-inflected notes of
the Guidonian gamut, opposed to *musica ficta*, the notes requiring accidentals. Since this
project's entire mechanism is accidental spelling, the collision sat squarely in the
semantic domain and would have misled any musicologist reading the title. Caught in
external review.

---

## External review log

The one-page probe was circulated to two other language models. **Their agreement is
recorded here as approximately one signal, not two** — both searched the same indexed web,
both read a framing written by a third model, and neither ran a test. Correlated
instruments do not constitute independent confirmation. What follows is logged for the
specific items each returned, not for its verdict.

**DeepSeek** — caught the *musica recta* / *musica ficta* collision, which the drafting
model missed. Directly responsible for the rename.

**Kimi** — surfaced **Ithkuil** as the nearest miss: a morpho-phonemic script in which many
characters are purely morphological and carry no set phonological value. The distinction
holds — Ithkuil remains pronounceable and its script is primary for concision, not for
withholding — but it should have been found earlier. Also proposed **graphematics** as a
disciplinary home, which turns out to be correct and consequential (below).

**What neither did:** challenge the premise. Neither questioned the circularity of
demonstrating a designed failure, nor asked what Tacet proves that Dutch does not. Both
accepted the drafting model's framing of the prior-art question as adequate. Fluent
elaboration on a supplied premise is the characteristic failure mode of these instruments
and it is visible in both responses.

---

## Disciplinary home

Grapholinguistics, not conlanging. The field has a live foundational argument — whether
writing is a secondary representation of speech or a semiotic system in its own right —
running through Prague School functionalism and Vachek's dual-level model, and framed as
**dependency vs. autonomy**.

Tacet is a constructed limit case for the autonomy side. Natural languages supply partial
evidence that writing is *relatively* independent of speech. Tacet supplies a system where
one grammatical category is provably non-derivable from the spoken form, with the
derivability tunable by a physical parameter.

Reading: Meletis & Dürscheid (2022), *Writing Systems and Their Use*; Neef on modular
theory; Vachek (1989); Weingarten on comparative graphematics.

---

## Contents

```
tacet-one-page.pdf                  one-page probe, for circulation
tacet-v0.1-design-brief.md          purpose, tiers, kill conditions
tacet-v0.2-lexicon-and-grammar.md   lexicon, morphology, the exhibit
tacet-v0.3-three-substrates.md      English / Japanese / Malagasy
tacet-plain-language-note.md        general-audience explainer
midi_diff2.py                       the firewall test, with asserted mapping
A_witnessed.mid  B_reported.mid     byte-identical output
```

---

## Open, and not yet run

- **K1 has not been tested.** No human has attempted to read Tacet.
- **K1 needs a production arm.** In Dutch, *reading* these forms is efficient while
  *spelling* them is the largest known difficulty in the orthography. Comprehension and
  production must be gated separately.
- **A caveat that cuts against the design:** cues of this kind are most safely ignored
  when they encode only abstract grammatical information — which is precisely what
  evidentiality is.
- **Raw-audio render** replacing MIDI: specified, not run.
- **Typology unverified.** The Japanese and Malagasy claims in v0.3 have not been checked
  against reference grammars.
- **K3 remains the likely failure.** If models fail the matched serial control at rates
  comparable to their failure on Tacet, the result measures unfamiliarity and is void.
- **Prior art** has been searched only in indexed sources. CONLANG listserv archives,
  print musicology, and dissertations remain unchecked.

---

## Disclosure

Machine-drafted, human-directed, human-verified. Drafted in collaboration with Claude
(Anthropic); reviewed by DeepSeek and Kimi as logged above. All technical judgments,
and all errors, are the author's.

Released CC0. Take it, break it, and say where it broke.
