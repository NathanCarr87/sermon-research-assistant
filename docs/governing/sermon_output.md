# Sermon Output

## 1. Purpose

`sermon_output.md` defines how the sermon agent transforms a developed and evaluated sermon into its final deliverable.

The output layer is responsible for **presentation**, not discovery.

By the time the agent reaches this stage, the sermon should already have:

* A defined purpose
* A primary biblical text
* A defensible interpretation
* A coherent theological claim
* A central idea
* A deliberate structure
* Appropriate application
* A defined landing point
* Completed evaluation
* Necessary revisions

The output stage should not introduce major theological or structural discoveries unless the final formatting process exposes a genuine problem.

---

# 2. Output Principle

The final output should be:

**Faithful, usable, readable, speakable, and complete.**

The agent should optimize for the preacher's ability to take the output and actually use it.

The output should not contain unnecessary information simply because the agent discovered it during research.

Research supports the sermon.

The research dump is not the sermon.

---

# 3. Output Types

The agent may produce different forms of sermon output depending on the user's request.

Supported output forms include:

```text id="9t4d2k"
Sermon Concept
Sermon Brief
Sermon Outline
Sermon Notes
Full Manuscript
Preaching Manuscript
Condensed Preaching Notes
Study Notes
Revision Draft
```

The agent should produce the requested form rather than automatically generating a full manuscript.

---

# 4. Sermon Concept

A sermon concept should be concise.

It should normally contain:

* Working title
* Primary text
* Central idea
* Sermon purpose
* Intended response

The concept should communicate the sermon clearly enough to determine whether development should continue.

---

# 5. Sermon Brief

A sermon brief should provide the preacher with the sermon's conceptual foundation.

Recommended components:

```text id="ljgq6b"
Title
Primary Text
Sermon Purpose
Central Idea
Human Tension
Theological Claim
Desired Response
Sermon Movement
Key Applications
```

The brief should remain concise.

It is a planning artifact, not a manuscript.

---

# 6. Sermon Outline

The outline should expose the architecture of the sermon.

It should normally include:

* Title
* Primary text
* Central idea
* Introduction
* Major movements
* Supporting Scripture
* Exposition
* Application
* Transitions
* Conclusion
* Landing point

The outline should contain enough substance to preach or draft from without becoming a disguised manuscript.

---

# 7. Full Manuscript

When a full manuscript is requested, the agent should produce a complete sermon intended for spoken delivery.

The manuscript should generally contain:

1. Title
2. Primary text
3. Introduction
4. Sermon development
5. Biblical exposition
6. Theological development
7. Application
8. Appropriate gospel / redemptive context
9. Conclusion
10. Final landing point

The manuscript should not expose internal development artifacts unless specifically requested.

---

# 8. Preaching Manuscript

A preaching manuscript should prioritize usability while speaking.

It should use:

* Clear paragraph breaks
* Shorter spoken sentences
* Natural transitions
* Deliberate repetition
* Clearly identifiable Scripture
* Emphasis where appropriate
* Logical movement
* Breathing room around major ideas

The manuscript should not read like an academic paper.

---

# 9. Condensed Preaching Notes

When condensed notes are requested, preserve:

* Central idea
* Major movements
* Key Scripture
* Essential explanations
* Critical transitions
* Applications
* Conclusion
* Landing point

Remove:

* Redundant prose
* Excessive explanation
* Nonessential illustrations
* Research details that do not need to be spoken

Condensed notes should help the preacher remember the sermon without requiring the manuscript.

---

# 10. Study Notes

Study notes may include material that does not belong in the preached sermon.

These may include:

* Historical background
* Interpretive questions
* Alternative interpretations
* Word studies
* Theological observations
* Cross-references
* Research findings
* Source notes
* Application considerations

The agent must clearly distinguish study material from sermon material.

---

# 11. Final Output Hierarchy

When presenting a sermon, prioritize:

```text id="7b6qk0"
Central Idea
    ↓
Biblical Text
    ↓
Sermon Movement
    ↓
Exposition
    ↓
Application
    ↓
Landing Point
```

Supporting material should serve this hierarchy.

Nothing should compete with the central idea.

---

# 12. Title

The title should accurately represent the sermon.

A title may be:

* Direct
* Thematic
* Narrative
* Poetic
* Provocative
* Question-based
* Derived from the biblical text

The title should not promise something the sermon does not deliver.

Avoid clickbait-style titles that distort the sermon merely to generate interest.

---

# 13. Scripture Presentation

When Scripture is included in the final sermon, the agent should:

* Identify the translation when relevant
* Preserve quotation accuracy
* Clearly distinguish Scripture from commentary
* Avoid silently modifying quoted text
* Avoid presenting paraphrase as direct quotation

Long Scripture readings should be handled according to the user's requested format and the relevant scripture policy.

---

# 14. Citations and Sources

When the sermon depends on external research, source information should be available when appropriate.

However, citations should not unnecessarily interrupt the spoken sermon.

The agent may separate:

```text id="y9x5ts"
Sermon
```

from:

```text id="6kq0b1"
Research / Source Notes
```

when useful.

The final spoken manuscript should remain readable.

---

# 15. Internal Reasoning Must Not Leak

The final sermon should not contain internal agent processes such as:

* "The agent determined..."
* "Research suggests..."
* "The evaluation identified..."
* "The model believes..."
* "This was generated from..."
* Development-stage uncertainty that has already been resolved

The user should receive the sermon artifact, not the machinery used to produce it.

If unresolved uncertainty materially affects the sermon, it should be expressed as appropriate scholarly or pastoral qualification—not as internal system commentary.

---

# 16. No Artificial AI Voice

The final sermon should avoid recognizable generic AI patterns.

Avoid excessive use of:

* "In today's fast-paced world..."
* "Let's dive in..."
* "Here's the thing..."
* Repetitive rhetorical questions
* Excessive three-part lists
* Constant "not this, but that" constructions
* Artificially dramatic declarations
* Generic inspirational conclusions
* Repeated phrases with no rhetorical purpose

These are not forbidden phrases individually.

The concern is **formulaic prose**.

The sermon should sound like a human preacher communicating something they genuinely believe is worth saying.

---

# 17. Spoken Naturalness

The final manuscript should be read aloud during quality evaluation when practical.

Look for:

* Sentences that are too long
* Abrupt transitions
* Unnatural phrasing
* Repeated words
* Dense paragraphs
* Tongue-twisting constructions
* Ambiguous references
* Places where the listener would lose the thread

Written correctness is insufficient.

The sermon must work when heard.

---

# 18. Paragraph Length

Paragraphs should generally represent meaningful spoken units.

Long paragraphs should be broken when:

* The idea changes
* A new movement begins
* Scripture is introduced
* Application begins
* An illustration begins
* A major conclusion is reached

Formatting should support comprehension rather than merely look polished.

---

# 19. Scripture and Commentary Separation

Where appropriate, distinguish visually between:

**Scripture**

and

**Sermon commentary.**

This helps the preacher and listener understand when the sermon is directly reading Scripture versus explaining it.

The exact formatting may vary by output medium.

---

# 20. Illustrations in the Final Output

Illustrations should appear where they perform their intended function.

The agent should not collect all illustrations into a separate section unless the user requests that format.

A story should normally occur where the sermon needs it.

The output should preserve the relationship:

```text id="wdj8q8"
Truth
→ Illustration
→ Meaning
```

rather than:

```text id="m1xx6s"
Truth
→ Random story
→ Back to sermon
```

---

# 21. Application in the Final Output

Application should be integrated naturally into the sermon unless the requested format calls for a separate application section.

The agent should avoid making application feel like:

> "Now here are five things you should do."

unless that structure genuinely fits the sermon.

Application may emerge throughout the sermon.

The final output should make the implications of the biblical truth clear.

---

# 22. Conclusion Formatting

The conclusion should be visibly and rhetorically distinct when appropriate.

It should:

* Return to the central idea
* Resolve the sermon
* Reinforce the intended response
* Provide appropriate hope or warning
* Reach the landing point

Do not append additional ideas simply because the conclusion feels too short.

---

# 23. Length

The final output should respect the requested length.

If no length is specified, the agent should use the natural length required by the sermon's purpose.

Do not:

* Pad a sermon to reach a word count
* Remove necessary reasoning merely to be short
* Add extra illustrations to make a sermon longer
* Repeat points to create artificial length

A sermon should be as long as necessary and no longer than necessary.

---

# 24. Output Completeness

Before delivering the final sermon, verify:

### Content

* Primary text is present
* Central idea is clear
* Major movements are complete
* Applications are present where appropriate
* Conclusion is complete

### Integrity

* Scripture is accurately represented
* Theology is coherent
* Claims are appropriately qualified
* Research-dependent claims are supported

### Communication

* Spoken language is natural
* Transitions are understandable
* Structure is visible
* Important ideas are emphasized

### Purpose

* The sermon accomplishes its intended objective
* The response is appropriate
* The landing point is clear

---

# 25. Output Modes Should Not Change the Message

A manuscript, outline, and preaching notes may look very different.

They should nevertheless communicate the same underlying sermon.

The agent should preserve:

```text id="2v8i9s"
Primary Text
Central Idea
Theological Claim
Sermon Movement
Application
Landing Point
```

across output formats.

Formatting may change.

The sermon should not.

---

# 26. User Requests Take Precedence

The user may request:

* A manuscript only
* An outline only
* A shorter version
* A longer version
* Notes
* A specific formatting style
* A sermon for a particular audience
* A particular preaching length
* Multiple versions

The agent should adapt the output accordingly.

User formatting preferences should be honored unless they conflict with the governing theological, scripture, research, or integrity policies.

---

# 27. Output Should Not Reopen Development Unnecessarily

Once the sermon has passed evaluation and revision, the output stage should not repeatedly reconsider settled decisions.

However, if formatting reveals a substantive problem, the agent should flag it rather than hiding it.

For example:

> The requested 10-minute version cannot preserve the essential exposition without removing the sermon's central theological argument.

In such cases, the agent should make the smallest necessary adjustment or explain the tradeoff.

---

# 28. Final Quality Gate

Before delivering a final sermon, ask:

### Faithfulness

Is it faithful to Scripture?

### Theology

Is it doctrinally coherent?

### Purpose

Does it accomplish its intended purpose?

### Structure

Does it move naturally?

### Clarity

Can it be understood when heard?

### Pastoral Integrity

Does it treat the listener responsibly?

### Application

Does it lead toward an appropriate response?

### Voice

Does it sound human and natural?

### Economy

Is unnecessary material removed?

### Landing

Does it finish where it should?

If the answer is yes, the sermon is ready for delivery.

---

# 29. Core Rule

The final output is not the place to demonstrate everything the agent knows.

It is the place to communicate **what the sermon needs to say**.

The agent should therefore deliver the strongest version of the sermon that emerged from the development, evaluation, and revision processes.

**The final artifact should disappear behind the message.**
