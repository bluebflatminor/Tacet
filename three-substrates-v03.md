# TACET v0.3 — Three Substrates

**Testing whether the loss belongs to rendering or to English**
Solbakken Research Initiative · CC0

---

## The problem this addresses

Tacet v0.1–v0.2 was built on English semantics and presented as though the design were
neutral. It wasn't. English does not grammaticalize evidentiality, so making it
obligatory was a stipulation — and the exhibit's force depended on that stipulation
holding.

If the loss under rendering is a property of *rendering*, it should appear on any
substrate. If it only appears on English, it was a property of English, and the
argument collapses.

Three builds follow. Same test, three languages.

---

## Tacet-E (English) — evidentiality on enharmonic spelling

**Obligatory category (stipulated):** witnessed vs. reported
**Silent channel:** enharmonic spelling of the root's first note
**Exhibit:** A♯–B♯–D♯ vs. B♭–C–E♭ · *I saw the boat sink* / *I am told the boat sank*

**Status of the obligation:** invented. English speakers can and constantly do make
statements without marking source. The exhibit works, but the compulsoriness is mine.

---

## Tacet-J (Japanese) — register on clef

**Obligatory category (native):** addressee honorification. You cannot produce a
Japanese sentence without selecting a register. There is no neutral form.

**Silent channel:** clef.

| Clef | Register |
|---|---|
| treble | plain (だ / である) |
| alto | polite (です / ます) |
| bass | humble-respectful |

Clef is a whole-utterance transform. Every note occupies a different position on the
staff, the page looks entirely unlike itself — and every sounding pitch is unchanged.
This is a stronger silent channel than enharmonic spelling, because the *entire glyph
layout* differs rather than one accidental.

**Exhibit J:** *The teacher is coming.*
COME = (−7, +5), rooted on G4 → C4 → F4.

```lilypond
\version "2.24.0"

comeJ = { g'8 c' f' r4. }

\score { \new Staff { \clef treble \comeJ } \header { piece = "plain" } }
\score { \new Staff { \clef alto   \comeJ } \header { piece = "polite" } }
\score { \new Staff { \clef bass   \comeJ } \header { piece = "humble" } }
```

Three visually distinct scores. One audio file.

**And this is where Tacet-J beats Tacet-E.** In English, dropping evidentiality
produces a sentence that is merely less specific. In Japanese, dropping register
produces **no sentence at all** — an unmarked-for-politeness Japanese utterance is not
a vaguer utterance, it is ungrammatical. So the rendered form isn't a lossy version of
the original. It is not a well-formed utterance in the substrate.

That is a materially stronger claim than v0.1 made, and I did not see it until the
substrate changed.

*Complication worth stating:* in spoken Japanese, register **is** audible — 行く vs.
行きます are different sounds. Tacet-J relocates a normally-audible obligatory category
into a silent channel. That's a design choice, not a discovery about Japanese, and it
should be labelled as such wherever this is published.

---

## Tacet-M (Malagasy) — trigger on beaming

Malagasy breaks the v0.2 grammar outright, which is the useful part.

**Word order is VOS and fixed.** Metrical position therefore cannot assign case — the
entire §3 case system of v0.2 was accusative Indo-European thinking wearing a musical
costume.

**Obligatory category (native):** voice/trigger. Austronesian alignment requires the
verb to select which argument is the pivot. Not optional, not stylistic.

**Silent channel:** beaming group on the verb root. With equal durations, beaming is
purely visual.

| Beaming | Trigger |
|---|---|
| ♪♪♪ beamed as 3 | actor-topic |
| ♪♪ + ♪ | theme-topic |
| ♪ + ♪♪ | circumstantial-topic |

**Exhibit M:** same three notes, same durations, same audio; three different sentences
depending on which argument is pivot. Beaming is the only difference on the page.

**Asymmetry found here:** Malagasy reduplication (productive, marks attenuation) maps
naturally onto repeat signs — but a repeat expands into actual repeated sound. So that
category is **Tier 1**, unavoidably. Not every obligatory category can be relocated to
the silent layer. Which languages have relocatable obligations and which don't is now
an open research question, and it wasn't visible from inside English.

---

## What the three-way comparison establishes

| | Obligatory category | Native or stipulated? | Silent channel | Rendered form is |
|---|---|---|---|---|
| Tacet-E | evidentiality | stipulated | enharmonic spelling | vaguer |
| Tacet-J | register | **native** | clef | **ungrammatical** |
| Tacet-M | voice/trigger | **native** | beaming | **ambiguous between 3 readings** |

The loss appears on all three. It is a property of rendering, not of English.

But the *severity* varies, and the variation is the more interesting result:

- English loses **specificity** — the rendered sentence still means something.
- Malagasy loses **determinacy** — the rendered sentence has three readings.
- Japanese loses **well-formedness** — the rendered sentence isn't one.

A benchmark scoring rendered output would report all three as passing. It would be
wrong three different ways, and it has no channel through which to discover any of
them.

---

## Revised claim

v0.1 said: *rendering deletes information.*

v0.3 says: **the severity of what rendering deletes is invisible from inside the
rendered space, and varies by a property of the source that the render cannot report.**

That's the paper. The English version alone could not have produced it.

---

## Open items added at v0.3

- [ ] The v0.2 metrical-case system is English-shaped and should be presented as
      Tacet-E-specific, not as Tacet's grammar
- [ ] Which obligatory categories are relocatable to a silent channel, and which
      (like Malagasy reduplication) are not
- [ ] A fourth substrate with no obvious relocatable obligation would be the real test
      — a negative case. Persian is a candidate: its compound-verb system suggests
      cadential figures for the light verbs, but I have not found an obligatory
      category there that a silent channel could carry
- [ ] All three exhibits still require the MIDI byte-identity check. None has been run.

---

*No claim here has passed a gate. The typological descriptions above are from general
knowledge and have not been verified against a reference grammar — that is the first
thing to fix before this is published anywhere.*
