# TACET v0.2 — Lexicon, Grammar, and the Minimal Contrast Set

**Solbakken Research Initiative · CC0**
Companion to *Tacet v0.1 Design Brief*. Build-order step 2.

---

## 1. Root Structure

A lexical root is **three notes in the top voice**, defined as a pair of directed
intervals in semitones. Roots are transposition-invariant: only the interval pair is
lexical. The starting pitch is free.

Interval alphabet: ±1, ±2, ±3, ±4, ±5, ±7 (twelve values; ±6 reserved, see §6).

## 2. Starter Lexicon (20 roots)

Antonyms and converses are **sign-inversions** of the interval pair. This is Solresol's
retrograde trick done as inversion instead — musically native, and it makes the
paradigm learnable in half the entries.

| Root | Intervals | Inverse | Root |
|---|---|---|---|
| GO | +7, −5 | −7, +5 | COME |
| GIVE | +2, −5 | −2, +5 | TAKE |
| DAY | +4, +3 | −4, −3 | NIGHT |
| KNOW | +1, +4 | −1, −4 | FEAR |
| BOAT | +2, +3 | −2, −3 | SHORE |
| SPEAK | +1, +2 | −1, −2 | LISTEN |
| HOUSE | +3, +4 | −3, −4 | SINK |
| BIRD | +5, +2 | −5, −2 | STONE |
| FIRE | +2, +5 | −2, −5 | WATER |
| SEE | +4, −1 | −4, +1 | HIDE |

SINK as the inverse of HOUSE is an accident of the grid and should be re-assigned in
v0.3 — the pairing carries an implication the language shouldn't make. Flagged, not
fixed.

## 3. Case by Metrical Position

Position of the root's **first note** within the bar assigns grammatical role. Voice
order is therefore free.

| Beat | Role |
|---|---|
| 1 | agent |
| 2 | verb |
| 3 | patient |
| 4 | oblique (instrument, locative, temporal) |

## 4. Vertical Morphology

| Voice | Carries | Realization |
|---|---|---|
| V1 (top) | lexical roots | the melodic line |
| V2 (inner) | **tense** | sustained interval below V1 at bar start |
| V3 (inner) | number | present = plural, absent = singular |
| V4 (bass) | discourse frame | reference pitch; modulation = topic shift |

**V2 tense inventory:**
minor 3rd = past · perfect 4th = present · perfect 5th = future · tritone = irrealis

## 5. Negation (proposal — open item from v0.1)

Negation is a **grace-note appoggiatura one semitone above the root's first note**.
Audible, therefore Tier 1. This is deliberate: negation is core propositional content
and must survive rendering, or the performed language is not a language.

I don't love it. It's an affix wearing a musical costume rather than something music
does natively. But it's testable, and "music has no primitive for *not*" may simply be
true — in which case this is the honest workaround rather than a failure.

## 6. Reserved

The tritone (±6) is reserved and carries no lexical value. It appears only as the V2
irrealis marker. This keeps one interval unambiguous across the whole system.

---

## 7. Tier 2 — Page-Only Assignments (the firewall)

| Contrast | Sharp / Up / Dotted | Flat / Down / Tied |
|---|---|---|
| Enharmonic spelling of root's first note | **witnessed** | **reported** |
| Stem direction | animate | inanimate |
| Duration spelling | perfective | imperfective |
| Beaming group | constituent bracketing (no default) | — |
| Clef | plain register | honorific register |

Spelling of notes 2 and 3 follows deterministically from note 1, so evidentiality is
marked once and propagates. **There is no unmarked form.** Every utterance is marked
for evidentiality, and rendering deletes the category entirely rather than degrading it.

---

## 8. The Exhibit

Two utterances. Same lexemes, same tense, same case assignment. Unmistakably distinct
on the page. **Bit-identical in audio.**

> **A.** *I saw the boat sink.*
> **B.** *I am told the boat sank.*

**Structure (both):** BOAT on beat 1 (agent) · SINK on beat 2 (verb) · V2 minor 3rd
below V1 (past).

**A — witnessed (sharp-side spelling):**
BOAT = A♯ → B♯ → D♯  ·  SINK = D♯ → B♯ → G♯

**B — reported (flat-side spelling):**
BOAT = B♭ → C → E♭  ·  SINK = E♭ → C → A♭

Every pitch is enharmonically equivalent. A♯=B♭, B♯=C, D♯=E♭, G♯=A♭. Rendered to any
equal-tempered synthesis path, the two files are identical. Read on the page, no fluent
reader could confuse them.

### LilyPond source

```lilypond
\version "2.24.0"

witnessed = \relative c' {
  \clef treble \time 4/4 \key c \major
  \omit Staff.KeySignature
  << { ais8 bis dis  dis bis gis  r4 r4 }
     \\ { fis2 s2 } >>
}

reported = \relative c' {
  \clef treble \time 4/4 \key c \major
  \omit Staff.KeySignature
  << { bes8 c ees  ees c aes  r4 r4 }
     \\ { ges2 s2 } >>
}

\score { \new Staff \witnessed \header { piece = "A — witnessed" } }
\score { \new Staff \reported  \header { piece = "B — reported"  } }
\score { \new Staff \witnessed \midi {} }
\score { \new Staff \reported  \midi {} }
```

**Verification step (do this before anything else):** render both MIDI outputs and
compare. If the byte streams differ, the exhibit has failed and Tier 2 has leaked
somewhere I haven't found. That check is cheap, it's falsifying, and it should happen
before a single further lexeme is written.

---

## 9. Three More Worked Utterances

**(i) The child gives water to the bird.** — present, witnessed, animate agent

CHILD¹ (beat 1) · GIVE (beat 2) · WATER (beat 3) · BIRD (beat 4)
V2 = perfect 4th (present) · stems up on CHILD and BIRD, down on WATER
Sharp-side spelling throughout.
¹ CHILD is not yet in the lexicon — v0.3.

**(ii) They did not see the fire.** — past, reported, plural

∅ (agent implied by V3) · SEE with appoggiatura (negation) on beat 2 · FIRE beat 3
V2 = minor 3rd (past) · V3 present (plural) · flat-side spelling (reported)

**(iii) If the boat comes, speak.** — irrealis then imperative

Bar 1: BOAT beat 1 · COME beat 2 · V2 = tritone (irrealis)
Bar 2: SPEAK beat 2, accent articulation · V4 modulates (new discourse frame)

---

## 10. Open Items

- [ ] HOUSE/SINK inverse pairing — re-assign
- [ ] CHILD, NAME, DIE, STONE, DAY not yet gridded against the inverse constraint
- [ ] **LilyPond auto-stems by default.** `\omit Staff.Stem_engraver` is wrong; needs
      explicit `\stemUp` / `\stemDown` on every root, and the engraver must be verified
      not to normalize. This is a live threat to Tier 2 integrity.
- [ ] Canonical rendering path undefined — which synthesizer counts as "performance"
- [ ] No serial control utterances written yet (required by K3 before any testing)
- [ ] Whether V4 modulation is recoverable by ear (if yes, it belongs in Tier 1)

---

*No claim here has passed a gate. The MIDI-identity check in §8 is the first thing in
this project that can actually fail, and it hasn't been run.*
