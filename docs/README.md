# Mandarin Anatomy Trainer — Vision, Learning Method & Build Guide

> **The source of truth for this app.** This is a long-term, expandable Mandarin-learning system, not a one-off vocabulary quiz. It begins with one tested character (`好`), the learner's initial **50 characters + 17 compounds**, and a carefully chosen **~100-character everyday-communication foundation**. It then grows into organized character families, phonetic series, and increasingly expressive spoken Chinese.
>
> **For every future assistant, developer, or coding session:** Read this README **before** modifying `docs/index.html`. Preserve the stated learning philosophy and grading rules. The existing running prototype is intentionally narrower than the ultimate vision.

## 1. The vision

Build a **mobile-first Chinese tutor** that teaches students to **read, hear, pronounce, understand, explain, remember, and write** Chinese characters by understanding how they were constructed.

The core insight is that Chinese writing should **not** be approached as thousands of arbitrary symbols memorized one at a time. A learner can develop transferable intuition by understanding:

1. **Useful building blocks:** master a small set of everyday characters and reusable words first.
2. **Combinatorics with grammar:** combine familiar pieces into many **natural, meaningful** Chinese sentences, not nonsensical permutations.
3. **Character anatomy:** identify *all the recognizable graphical components* of a character, what each originally depicted (where known), its standalone pronunciation/meaning when applicable, and its **role in the whole character**.
4. **Semantic vs. phonetic clues:** learn when a component hints at **meaning**, when it hints at **pronunciation**, when both are involved, and when the history is less certain.
5. **Families instead of random lists:** group new words by shared semantic components, phonetic series, historical pictures, meaningful compounds, and practical conversational situations.
6. **Two-way spoken practice:** listen to natural Mandarin, speak aloud, hear one's own recording, receive fair feedback on pronunciation and tones, and improve through repetition.
7. **Measured learning:** grade responses with partial credit, record attempts and weak spots, penalize peeking fairly, and continually remix learned material in cumulative exams.

**Desired outcome:** eventually recognize a new character's structure and make an *educated guess* about its semantic domain or pronunciation—while recognizing that these are clues, not guaranteed predictions.

## 2. Audience, platform, and scope

- First learner: an adult English speaker studying Mandarin on a **Samsung Galaxy Z Fold 7**, both folded and unfolded.
- Primary UI: simple, polished, touch-friendly **mobile web app** running over **HTTPS** in Chrome or Samsung Internet; ideally installable to the home screen as a PWA.
- Keep the original cards and testing experience available alongside the richer study engine. **Study definitions/anatomy first, test second.**
- Mandarin target: **Standard Mandarin / Putonghua**, with simplified Chinese as the default and traditional variants where pedagogically relevant; tone-marked Hanyu Pinyin throughout.
- Future: other learners, accounts, cloud sync, teachers, additional categories, potentially other languages—but do not overbuild before core study and recording work reliably.

## 3. Curriculum: foundation → useful expression → character families

### Phase A — Seed list: 50 characters and 17 multi-character words

Use the learner's original list of **50 unique characters and 17 compound words** as the initial data set. Preserve the staged schedule as a useful starting point, but allow the learner to remain on a day until mastered:

| Stage | New characters | Example compounds / themes |
| --- | ---: | --- |
| Day 1 | 13 | 爱你, 开心, 快乐, 最好, 天天; 我, 你, 是, 的 |
| Day 2 | 15 | 生日, 四季, 期待, 慢慢; numbers, dates, wishes |
| Day 3 | 11 | 遇到, 命运, 永远, 一起; 严, 靖, 雅, 餐 |
| Day 4 | 11 | 男人, 安排, 那么, 不只; 就, 老, 变 |

This is a **launch set, not the product ceiling**. All 50 characters and 17 compounds must ultimately be represented as separate testable units, cross-linked to their constituent characters and shared families.

### Phase B — ~100 high-utility characters for getting around in everyday life

The goal is roughly **100 especially productive characters** (overlapping the seed list, not necessarily 100 *additional* characters) from which we can build numerous useful words and everyday sentences. Choose the eventual set based on **frequency + communicative utility + combinatorial productivity**, not by blindly taking the top 100 corpus entries. Reassess the exact size after learning outcomes are measured.

Prioritize real situations: asking for or wanting something, getting somewhere, introductions, people, food/drink, numbers, dates, time, directions, payment, basic questions, negation, and essential grammar words/particles.

Examples of generative pieces:

- 我 (*wǒ*) = I; 你 (*nǐ*) = you
- 要 (*yào*) = want/need; 想 (*xiǎng*) = want to / think; 去 (*qù*) = go
- 水 (*shuǐ*) = water; 吃 (*chī*) = eat; 喝 (*hē*) = drink
- 是 (*shì*) = am/is/are; 不 (*bù*) = not; 吗 (*ma*) = yes/no question particle

Illustrative **natural** sentences as soon as those words are learned: `我要水` (I want water); `我想去` (I want to go); `你要喝水吗？` (Do you want to drink water?). A lesson may preview a useful whole phrase, but tests should normally rely on already-taught components or explicitly mark any new material.

**Important linguistic distinction:** a character is not always a word, and a multi-character word is more than a literal concatenation. Explicitly teach **word boundaries**, idiomatic meanings, grammatical roles, and tone changes, e.g., `一起` is commonly pronounced *yìqǐ*.

### Phase C — Systematic semantic-component / radical families

Study families that reuse a meaningful graphical element. Examples:

| Family | Representative characters | Learning question |
| --- | --- | --- |
| **氵 water** | 河 (*hé*, river), 海 (*hǎi*, sea), 洗 (*xǐ*, wash), 洋 (*yáng*, ocean) | How does the three-stroke water form cue a water-related domain? What are the **other** components doing? |
| **女 woman** | 好 (*hǎo*, good), 妈 (*mā*, mother), 姐 (*jiě*, older sister), 妹 (*mèi*, younger sister) | Which component contributes meaning? Which may give pronunciation? Why is 好 different from 妈? |
| **扌 hand** | 打 (*dǎ*, hit), 拉 (*lā*, pull), 推 (*tuī*, push) | What actions share a hand/action clue? |
| **讠 speech** | 说 (*shuō*, speak), 请 (*qǐng*, request/please), 语 (*yǔ*, language) | What do these actions or concepts have to do with speech? |
| **忄 heart/mind** | 情 (*qíng*, feeling), 怕 (*pà*, fear), 忙 (*máng*, busy) | How can a semantic component hint at emotional or mental domains? |

Categories should be **carefully curated**, not assumed to include every character containing a visual resemblance. In an individual card, distinguish the **dictionary indexing radical** from the **full structural decomposition** (these are not synonymous).

### Phase D — Phonetic series: infer possible pronunciation

Learn coordinated families where a shared component tends to supply a historical sound cue while a different component supplies a meaning cue. A flagship example is **青 (*qīng*)**:

| Character | Approximate modern sound | Meaning-related component | Shared sound clue |
| --- | --- | --- | --- |
| 清 | qīng | 氵 water | 青 |
| 请 | qǐng | 讠 speech | 青 |
| 情 | qíng | 忄 heart | 青 |
| 晴 | qíng | 日 sun | 青 |
| 蜻 | qīng | 虫 insect | 青 |

Teach explicitly that phonetic clues often suggest the **initial/final family** but not the exact tone, and historical sound shifts mean some modern members no longer sound alike. These are **heuristics with measurable success rates**, not guaranteed rules.

### Phase E — Expand indefinitely through connected networks

Further modules can focus on travel, restaurants, shopping, social life, science, relationships, time, geography, common verbs, and other interests. Categories may be organized by **use case**, **semantic component**, **phonetic series**, **historical construction**, **compound-word family**, or **grammar pattern**. A single character may belong to several overlapping groups.

## 4. Core learning flow

**Select level/category → Study its cards → Practice pronunciation and meaning → Take varied exams → Review weak items → Unlock additional material.**

A learner should never be forced onto Day 2 just because the calendar changed. Let mastery, preference, and review history drive progression. The user can always revisit a previous category or ask for a fresh cumulative exam.

### A. The two-sided interactive character card

**Front — answer before seeing the explanation**

- Show the **exact character**, lesson/category, and card number prominently.
- Field 1: enter **pinyin**, with tones (allow tone-marked and numbered input).
- Field 2: enter the **English meaning**; accept valid equivalents and context-specific definitions.
- Field 3: **optional** explanation of each component, its appearance/history, and how they relate to the whole.
- **Record my voice**: record a Mandarin attempt, stop, **replay the user's own voice**, and use an appropriate pronunciation evaluator when supported. Provide microphone diagnostics rather than a misleading score when unavailable.
- Buttons: **Grade answers** and **Peek at back**. Show number of pre-grading peeks and remaining maximum score.

**Back — full anatomy and learning narrative**

1. **Top row, always:** full **character**, correct **pinyin with tone**, primary **English meaning**, and a clearly labeled **play native Mandarin pronunciation** control.
2. **Every component** broken out in a logical graphical hierarchy, not merely an indexing radical. For each component: shape, modern name/meaning (when meaningful), **pronunciation** (when independently pronounceable), historical/pictographic development, present-day structural role (**semantic / phonetic / both / unknown**), and a playable pronunciation if appropriate.
3. **Why the picture looks that way.** For `好`, don't simply say `子 = child`: explain that early `子` shows a baby with a proportionally large head, small body, and outstretched arms. Explain `女` as a stylized kneeling human figure with crossed arms. Then explain the composition and identify which interpretations are traditional vs. well established.
4. **Deeper memory trick:** a vivid scene connecting the components to the actual word; tie the memory to how to *draw* the strokes. Separate a freely invented mnemonic from historical evidence.
5. Stroke count/order and optional animations; simplified vs. traditional forms when useful.
6. Linked compound words, other members of the semantic or phonetic family, and at least one **grammatically natural sentence**, with Mandarin audio and English translation.
7. Historical illustrations/ancient forms **where sourced and permitted**, and citations when etymology is uncertain or disputed. Never fabricate pictographic stories and label them historical fact.

For later multi-character **word cards**, show the complete word and natural pronunciation first; below it show each character's individual meaning, its role in the word, any tone sandhi, then an **idiomatic translation** and example sentence. Compound meaning need not equal the mechanical sum of constituent meanings.

### B. Audio and pronunciation

Required future experience:

- **Listen**: clear standard Mandarin for the whole word and each standalone pronounceable component; choose high-quality native recordings where available, with speech synthesis fallback clearly labeled.
- **Speak**: permission request on an **HTTPS** page, microphone status, tap to record/stop, user audio playback, optional replay of target for direct comparison.
- **Grade**: consonant/initial, vowel/final, syllable sequence, tone contour, and natural rhythm when the chosen engine can **actually measure** them. Provide per-dimension feedback and actionable correction; distinguish verified audio/acoustic assessment from merely matching an ASR transcript.
- The learner must be able to hear their **own voice**, not just see recognized text.
- Preserve accessibility and a useful text-only workflow when microphone access fails. Privacy should be clear: whether audio stays on-device, is transmitted to a speech provider, and how long it is retained.

**Current implementation caveat:** the initial prototype uses the browser microphone and optional browser speech-to-text with an **approximate transcript-derived score**. That **is not true acoustic tone grading**. Recording and recognition must be tested on the actual Fold browser. A future upgraded pronunciation service should be evaluated for Mandarin-specific feedback and privacy before integration.

## 5. Grading, fairness, and progress

The grade should reflect what the learner actually knows, not punish minor transcription slips or plausible alternative English definitions.

**Policy:**

- Pinyin exact syllable + correct tone: **full marks**. Correct letters with a missing tone should receive **most credit**; wrong tone but otherwise correct should still receive **substantial partial credit**. Near-correct spelling receives graded partial credit. Multiple syllables and tone sandhi must be handled explicitly.
- English meanings: semantic matching, accepted synonyms and contextual alternatives; permit manual corrections for ambiguous cases rather than strict string comparison.
- Historical/component explanation: partial credit for identifying components, explaining visual origin, distinguishing phonetic vs semantic role, and connecting the whole; this input is **optional** unless the exercise is specifically an etymology exam.
- Spoken response: partial marks for intelligible or partially correct pronunciation, **only to the precision genuinely supported by the audio evaluator**. If audio can't be evaluated, say *ungraded* and exclude it from the denominator—not 0%. Transcript matches alone cannot validate tones.
- Report component-level scores and total (example configurable starting weights: pinyin 40, meaning 35, explanation 15, speech 10). When optional/unavailable components are omitted, normalize the weights of assessed components so the learner is not penalized.
- **Peek penalty (explicit user requirement):** each time the learner peeks at the back **before submitting an attempt**, multiply **every awarded point and the final score by 0.5**. Zero peeks ×1; one peek ×0.5; two peeks ×0.25; three ×0.125. Record each peek. Reviewing after a grade is submitted should not incur additional penalties.
- Record **per-card attempts**, per-dimension marks, timestamps, number of peeks, cumulative/session/category/exam averages, recurrent mistakes, and trends. Keep the history when moving to another card or exam. Consider spaced-repetition scheduling and a mastery score that prioritizes consistent no-peek recall.
- Support viewing, reviewing, exporting and eventually syncing records; clearly distinguish **local-device** persistence from authenticated cross-device/cloud history and ChatGPT conversational memory. An assistant should never claim to see private in-browser answers unless the app explicitly shares an exported report or posts results via an authorized integration.

## 6. Exams and generative practice

Keep a selector at the top of the test interface:

1. **Exam 1 — New material only.** Characters, meanings, pinyin, tones, recognition and pronunciation for the current day/category.
2. **Exam 2 — Sentence remix.** Natural sentences built from the current and previously learned items, with varied speakers, word order and grammar patterns **that are valid Mandarin**, not random character permutations.
3. **Exam 3 — Cumulative challenge.** Mix all unlocked days/categories with character recognition, English ↔ Chinese translation, compound breakdown, listening, spoken response, and cloze/word-order tasks where appropriate.

Every exam can be **regenerated** with different questions and order; create as many valid combinations as the known vocabulary allows. Start from a curated library of proven **grammar templates** and validated sentences, then optionally extend with an AI generator plus language-quality checks. Don't silently introduce unlearned characters; display and explain exceptions.

Exams must produce an **average across graded questions and dimensions** with performance by type (pinyin, tones, meaning, anatomy, listening, speaking). Store attempt-level and exam-level history for longitudinal progress. Give more practice to missed and slow items; prevent repeated easy questions from hiding weak spots.

## 7. Content model for every learning item

Store content **separately from the interface**, preferably version-controlled JSON or structured data, so new chats can add hundreds of carefully researched cards without rewriting the app.

Suggested schema (illustrative, not yet implemented):

```json
{
  "id": "char_597d",
  "type": "character",
  "hanzi": "好",
  "pinyin": ["hǎo"],
  "meanings": ["good", "fine", "well"],
  "radical": "女",
  "strokes": 6,
  "components": [
    {"glyph": "女", "reading": "nǚ", "role": "semantic", "historical_shape": "kneeling woman with crossed arms", "evidence": []},
    {"glyph": "子", "reading": "zǐ", "role": "semantic", "historical_shape": "infant with large head and outstretched arms", "evidence": []}
  ],
  "etymology_notes": "Distinguish recorded evidence, interpretation, and mnemonic.",
  "mnemonic": "A kneeling mother and infant; recall two figures representing something cherished.",
  "audio": {"whole": null, "components": {}},
  "examples": [{"zh": "你很好。", "pinyin": "Nǐ hěn hǎo.", "en": "You're doing well."}],
  "categories": ["foundation", "woman-component", "semantic-compound"],
  "source_status": "requires editorial verification"
}
```

For word items, represent **all constituent characters**, idiomatic sense, pronunciation changes, grammatical behavior, and usage in authentic phrases. Maintain references for provenance of ancient glyphs, historical claims, and licensed audio.

## 8. Product architecture and quality standards

- **Data-driven curriculum:** editable per-character/per-word records; curriculum indexes; many-to-many relationships among components, families, and lessons.
- **Study engine:** rich, two-sided cards and audio playback/recording.
- **Assessment engine:** deterministic and explainable grading, optional components, peeks, exam aggregation, and adaptive review.
- **Content quality:** distinguish historical attestation, scholarly hypothesis, ordinary teaching shorthand, and invented mnemonic; no invented origins. Validate pinyin, tones, word meanings, example Mandarin, and component roles.
- **Mobile UX:** folded and unfolded Z Fold layout; large tap targets, dark/light, offline review when cached, readable cards with expandable sections, screen-reader labels.
- **Storage & privacy:** local-first progress and JSON export; optional future sync. Avoid publishing private recording or learner history to a public GitHub repository.
- **Testing:** automated tests for pinyin variants, tone partial credit, English synonyms, optional explanation, multiple peeks, exam averages, card navigation, data schema, and microphone states. Test microphone playback on real Android browsers before claiming device compatibility.
- **Maintainability:** preserve a working version while adding features, commit logical increments, and update docs/current status with each milestone.

## 9. Development roadmap and honest implementation status

| Milestone | Goal | Status |
| --- | --- | --- |
| **M0: 好 prototype** | Two-sided anatomy card; typed answers; pinyin/meaning partial-credit grading; optional explanation; audio controls; peek penalties; session scores; mobile browser recorder | **Implemented in `docs/index.html`; actual Fold microphone behavior needs verification** |
| **M1: robust mobile voice** | Reliable Android permissions, audio record/playback, intelligible diagnostics, correct persistence; native Mandarin examples | **Next priority** |
| **M2: seed curriculum** | All 50 individual characters + 17 compounds with detailed verified anatomy and component audio, Day 1–4 study selector | Planned |
| **M3: exams** | 3 exam modes per stage; grammar-safe randomized questions; cumulative exams; detailed grading history | Planned for standalone app (earlier interactive chat prototype exists) |
| **M4: essential 100** | Curated everyday foundation and productive real-world phrase templates | Planned |
| **M5: family learning** | Radicals/semantic components, phonetic series, etymological comparisons, character inference drills | Planned |
| **M6: advanced speech & sync** | Verified acoustic Mandarin tone assessment, longitudinal analytics, optional account sync, richer curricula | Exploratory |

**Deployment:** Source is currently in `docs/` of the public GitHub repo `Jony-GydeRnE/practice` on `master`. GitHub Pages is expected to be configured to publish from `master` → `/docs`, giving `https://jony-gyderne.github.io/practice/` **once enabled**. A GitHub commit alone does **not** verify that a public Pages URL is live. Use HTTPS for browser recording; Chrome and Samsung Internet are the first target browsers.

## 10. Acceptance criteria: don't call it ready until checked

For one polished card and for every new category, verify:

- Front **shows the tested character**, takes pinyin and meaning input, optional component explanation, and supports a usable speech workflow.
- Back has **character / pinyin / English in the top row**, its **entire meaningful component breakdown**, explanations of why ancient shapes represent their meanings, pronunciation for whole and pronounceable parts, an evidence-aware deeper mnemonic, and at least one sentence.
- A correct pinyin, missing tone, wrong tone, near-correct spelling, synonym, and partial anatomy explanation all receive appropriate and **test-verified different scores**.
- Peeks halve every score each time, and the count persists through the attempt. Reviewing after submission is free.
- Spoken audio can be replayed on target devices or the interface plainly states what is unavailable. **Never call transcript-only recognition tone-accurate.**
- After grading, moving to the next card or generating another exam preserves averages and history; reset behavior is deliberate, with export/recovery available before destructive actions.
- Cumulative exams use natural Mandarin and restrict unseen words according to lesson rules.
- Before claiming the release is ready, verify deployed HTTPS URL, microphone, recording playback, and scoring on a real Fold or transparently state what remains untested.

## 11. Handoff instructions for any future chat or coding assistant

If a future assistant is asked to continue this project:

1. Read **this file** and `docs/index.html`, then inspect the current code and most recent commits. Treat this README as the **product intent**, not as a statement that all features are implemented.
2. Do **not** replace the anatomical/etymological teaching approach with rote word lists, nor replace the three exam modes with a static quiz.
3. Implement the user's **specific requested next milestone** while preserving working controls. Explain any newly added, partial, untested, or unavailable feature explicitly.
4. Validate character origin claims and phonetic-vs-semantic roles; where uncertain, say so, and separate useful mnemonic stories from attested paleography.
5. Write automated or reproducible tests, test mobile screens, record limitations, and update the status table above. Avoid unsupported claims of microphone success or saved user progress.
6. Commit changes to the agreed GitHub branch and provide exact file/commit URLs. Keep personal results and recordings **out of the public repository**.

**Reusable chat prompt:**

> Continue my Mandarin Anatomy Trainer project. First read `https://github.com/Jony-GydeRnE/practice/blob/master/docs/README.md` and inspect `docs/index.html`. Follow the vision: foundational everyday Chinese (~100 productive characters), natural combinatorial sentence practice, deeply explained historical character anatomy, semantic/phonetic component families, native pronunciation and self-recording, fair partial-credit grading, cumulative random exams, strict peek penalties, and persistent progress. Show which features exist and which are still planned. Work on **[SPECIFIC NEXT TASK]** and update the README with tested status.

## 12. Current next action

**Verify the microphone-recording and playback workflow on the Z Fold 7 through the standalone HTTPS site** (Chrome or Samsung Internet), then preserve a functional one-card template. Only after that, scale the system to 50 characters and 17 compounds, then the essential-100 foundation and component/phonetic families.