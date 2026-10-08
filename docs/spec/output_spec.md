# Output Specification

## 1. Purpose

This document defines how the Sermon Research Assistant transforms sermon state into usable outputs.

The output system is responsible for producing clear, faithful, traceable, audience-appropriate sermon material while preserving the distinction between:

* Scripture
* research
* theological interpretation
* evidence
* claims
* sermon structure
* application
* generated language

The output system must not introduce new substantive claims that are not supported by the sermon state.

This specification operationalizes `sermon_output.md`.

---

# 2. Governing Authority

Output generation is subordinate to the following authority hierarchy:

1. `constitution.md`
2. `theological-profile.yaml`
3. `theology.md`
4. `research_policy.md`
5. `scripture_policy.md`
6. `sermon_style.md`
7. `sermon_structure.md`
8. `sermon_development.md`
9. `sermon_evaluation.md`
10. `sermon_revision.md`
11. `sermon_output.md`
12. `agent_spec.md`
13. `state_model.md`
14. `output_spec.md`

Where conflicts exist, higher-level governing documents take precedence.

---

# 3. Output Principles

The output system must:

1. Preserve biblical faithfulness.
2. Preserve theological consistency.
3. Preserve the intended sermon thesis.
4. Preserve traceability to source material.
5. Distinguish sourced material from generated language.
6. Avoid fabricated quotations, facts, citations, stories, statistics, or references.
7. Preserve uncertainty where the underlying evidence is uncertain.
8. Follow the requested output type.
9. Respect requested audience, tone, length, and format.
10. Avoid unnecessary verbosity.
11. Preserve the preacher's ownership of the sermon.
12. Make important source relationships understandable.
13. Avoid silently changing approved sermon content.
14. Avoid introducing unsupported interpretation during formatting.
15. Produce material that can be reviewed by a human before public use.

The output system is a transformation layer, not an independent theological or research engine.

---

# 4. Output Requests

An output request may specify:

* output type
* audience
* intended use
* length
* tone
* formatting
* level of detail
* delivery style
* Scripture translation
* citation requirements
* whether research notes should be included
* whether provenance should be visible
* whether the output should be polished or intentionally rough
* whether the output should preserve existing wording

If the request is underspecified, the agent should use the current sermon state and established project defaults.

The agent should not ask unnecessary clarification questions when the requested output can reasonably be generated from existing state.

---

# 5. Output Types

The system should support multiple output types.

## 5.1 Sermon Outline

A structured representation of the sermon.

Typical components:

* title
* primary text
* thesis
* introduction
* major movements
* supporting points
* Scripture references
* explanation
* application
* conclusion

An outline should prioritize structure over prose.

---

## 5.2 Sermon Manuscript

A complete written sermon intended for preparation, editing, or delivery.

The manuscript should include:

* title
* primary Scripture
* introduction
* sermon development
* transitions
* explanation of Scripture
* supporting evidence where appropriate
* application
* conclusion

The manuscript should sound like a sermon rather than a research report.

Research should support the sermon rather than overwhelm it.

---

## 5.3 Preaching Notes

Condensed material intended to assist live preaching.

Preaching notes may include:

* main idea
* key Scripture references
* movement headings
* important phrases
* transitions
* illustrations
* application prompts
* emphasis points
* conclusion

Preaching notes should not unnecessarily reproduce the full manuscript.

---

## 5.4 Research Brief

A research-oriented output containing relevant findings supporting sermon development.

A research brief may include:

* research question
* sources
* findings
* relevant quotations
* historical context
* theological context
* interpretive observations
* areas of disagreement
* confidence
* relevance to sermon claims

Research output must preserve source attribution.

---

## 5.5 Scripture Study

A focused examination of the biblical text.

It may include:

* passage context
* literary observations
* key terms
* surrounding context
* relevant cross-references
* interpretive considerations
* theological implications
* uncertainties or legitimate interpretive disagreements

The agent must distinguish textual observations from interpretive conclusions.

---

## 5.6 Evaluation Report

A structured assessment of the current sermon.

It may include:

* strengths
* findings
* severity
* affected sections
* evidence
* recommendations
* unresolved issues
* revision priorities

Evaluation output should explain problems rather than merely assign scores.

---

## 5.7 Revision Summary

A summary of changes made between sermon versions.

It may include:

* changed sections
* resolved findings
* unresolved findings
* theological changes
* structural changes
* research changes
* application changes
* remaining questions

The summary should make meaningful changes visible without reproducing the entire sermon.

---

## 5.8 Sermon Package

A complete preparation package may contain:

1. sermon overview
2. primary Scripture
3. thesis
4. outline
5. research notes
6. manuscript
7. preaching notes
8. application
9. evaluation summary
10. unresolved questions
11. source information

The package should only include components requested by the user or required by the selected workflow.

---

# 6. Output Readiness

The agent should evaluate whether sufficient sermon state exists before producing an output.

Readiness depends on the output type.

For example:

### Outline

Requires sufficient:

* Scripture
* intent
* thesis or developing central idea
* structural information

### Manuscript

Requires sufficient:

* Scripture
* sermon intent
* thesis
* structure
* development
* application
* evaluation sufficient to avoid known critical problems

### Research Brief

Requires:

* research questions
* completed or partially completed research
* source records
* findings

### Evaluation Report

Requires:

* sufficient sermon material to evaluate
* relevant supporting state

### Sermon Package

Requires sufficient state for every requested component.

The system must not manufacture missing state simply to satisfy an output request.

---

# 7. Partial Outputs

The agent may produce partial outputs when the user explicitly requests them or when partial output is useful.

Examples:

* developing outline
* preliminary thesis
* partial manuscript
* research snapshot
* incomplete sermon draft

Partial outputs must clearly communicate their status when that status matters.

The agent should not present unfinished work as finalized sermon material.

---

# 8. Source Preservation

When output contains information derived from external research, the system must preserve source provenance in the underlying state.

Where appropriate, output should expose:

* source name
* author
* publication
* date
* URL or identifier
* relevant quotation
* relationship to sermon claim

The level of visible citation should depend on the requested output.

A polished sermon manuscript does not necessarily need research citations embedded throughout the spoken text.

A research brief generally should.

The underlying state must retain provenance even when the visible output does not.

---

# 9. Scripture Handling

Scripture references must be preserved accurately.

The output system must:

* preserve the intended passage
* preserve references to biblical books, chapters, and verses
* follow `scripture_policy.md`
* follow the selected translation where applicable
* avoid fabricating quotations
* avoid presenting paraphrases as direct quotations
* distinguish Scripture from commentary
* avoid silently changing the meaning of cited passages

If exact Scripture wording is required and the system does not possess reliable text for the requested translation, it should not invent the wording.

---

# 10. Attribution

Claims originating from identifiable sources should remain attributable where attribution is necessary for intellectual or factual integrity.

Examples include:

* quotations
* statistics
* historical claims
* scholarly interpretations
* distinctive arguments
* research findings

Attribution may be:

* inline
* footnoted
* parenthetical
* listed in research notes
* represented through internal provenance

depending on the output type.

Attribution must not be fabricated or implied when the source relationship does not exist.

---

# 11. Generated Language

The agent may generate connective and rhetorical language including:

* transitions
* introductions
* explanations
* illustrations
* applications
* summaries
* conclusions
* rhetorical questions
* phrasing improvements

Generated language must not create unsupported factual, theological, historical, or biblical claims.

The agent may improve expression without changing substantive meaning unless revision of the underlying content was explicitly requested.

---

# 12. Evidence Boundaries

The output system must preserve the distinction between:

```text
Source
   ↓
Finding
   ↓
Evidence
   ↓
Claim
   ↓
Sermon language
```

A generated sentence should not be treated as evidence merely because the sentence sounds authoritative.

Similarly:

* an illustration is not historical evidence unless it actually is
* an interpretation is not a quotation
* a paraphrase is not a direct quotation
* a theological inference is not an explicit biblical statement
* an unsupported assumption is not research

---

# 13. Uncertainty

Where sermon state contains uncertainty, output must not silently convert uncertainty into certainty.

Examples:

* disputed historical claims
* competing interpretations
* uncertain authorship
* unclear chronology
* scholarly disagreement
* incomplete research

Appropriate language may include:

* "Some interpreters understand..."
* "One common interpretation is..."
* "The evidence is uncertain..."
* "This passage has been understood in several ways..."

The specific wording should follow the project's theological and stylistic policies.

---

# 14. Audience Adaptation

Output may be adapted for:

* church congregation
* small group
* youth
* children
* leadership
* teaching environment
* personal study
* preaching preparation

Audience adaptation may change:

* vocabulary
* explanation depth
* illustration selection
* pacing
* application framing
* assumed background knowledge

Audience adaptation must not change theological commitments or biblical meaning merely to make the sermon more appealing.

---

# 15. Length and Pacing

The system should treat length as a constraint rather than a goal.

When a target length is specified, the agent should prioritize:

1. biblical faithfulness
2. thesis clarity
3. structural coherence
4. necessary explanation
5. necessary application
6. supporting material
7. rhetorical polish

When content must be reduced, peripheral material should generally be removed before essential sermon development.

The system should avoid padding output to reach a requested word count.

---

# 16. Style Application

Output must follow `sermon_style.md`.

Style controls expression, not truth.

The system may adjust:

* sentence length
* rhythm
* tone
* rhetorical density
* transitions
* vocabulary
* repetition
* conversational quality

Style must not override:

* Scripture
* theology
* evidence
* research integrity
* approved sermon intent

---

# 17. Structural Integrity

The output must preserve the approved sermon structure unless restructuring is explicitly requested.

A manuscript generated from an approved outline should correspond to that outline.

The system should not:

* remove major movements without authorization
* introduce unrelated sections
* reorder major theological arguments without reason
* bury the thesis
* create redundant sections
* weaken the intended progression

If the agent identifies a structural problem while producing the output, it should surface the issue rather than silently redesigning the sermon.

---

# 18. Application Integrity

Application should emerge from the sermon rather than being appended arbitrarily.

The output system should preserve the relationship:

```text
Text
  ↓
Meaning
  ↓
Theological significance
  ↓
Human implication
  ↓
Application
```

Application should not:

* contradict the text
* introduce unrelated moral demands
* become generic motivational content
* claim biblical authority for a merely personal preference

Where application depends on an interpretive judgment, that dependency should remain visible in the underlying state.

---

# 19. Illustrations

Illustrations may be:

* user-provided
* researched
* historical
* contemporary
* hypothetical
* generated

The output must not present hypothetical or generated illustrations as factual events.

If an illustration depends on a real person's experience, historical event, statistic, or documented story, its factual basis must be preserved.

Generated illustrations should be clearly distinguishable from factual anecdotes when that distinction matters.

---

# 20. Output Formatting

The output system should produce clean, predictable formatting.

Formatting should support the intended use.

Possible structures include:

### Sermon Manuscript

```text
Title

Primary Text

Thesis

Introduction

Point 1
  Explanation
  Scripture
  Illustration
  Application

Point 2
  Explanation
  Scripture
  Illustration
  Application

Conclusion
```

### Research Brief

```text
Research Question

Key Findings

Sources

Evidence

Interpretive Considerations

Conflicting Views

Confidence

Sermon Relevance
```

### Evaluation

```text
Overall Assessment

Strengths

Critical Findings

Major Findings

Moderate Findings

Minor Findings

Recommendations

Unresolved Questions
```

Actual formatting should follow the selected output mode.

---

# 21. Versioning

Outputs must correspond to a specific sermon state or version.

The system should preserve the relationship:

```text
Sermon State Version
        ↓
Evaluation
        ↓
Revision
        ↓
New Sermon State Version
        ↓
Output
```

A new output should not overwrite the historical relationship between previous versions and their generated outputs.

Where persistence is implemented, outputs should retain:

* sermon identifier
* state/version identifier
* output type
* generation timestamp
* relevant request parameters
* provenance references

---

# 22. Regeneration

The user may request regeneration of an output.

Regeneration should use the current sermon state unless the user explicitly requests an earlier version.

The system should distinguish:

* regenerated wording
* substantive revision
* new research
* structural revision

Regeneration alone should not be interpreted as substantive sermon development.

---

# 23. Output Validation

Before finalizing an output, the agent should validate:

### Biblical

* Scripture references are valid within available state.
* Quotations are not fabricated.
* Paraphrases are not presented as quotations.
* Interpretation does not contradict established constraints.

### Theological

* Output follows the theological profile.
* No prohibited theological assumptions were introduced.
* Doctrinal claims remain traceable.

### Research

* External claims have appropriate provenance.
* Sources are not misrepresented.
* Uncertainty is preserved.
* Fabricated citations are absent.

### Sermon

* Thesis remains clear.
* Structure remains coherent.
* Development supports the thesis.
* Application follows from the sermon.
* Conclusion resolves the sermon appropriately.

### Communication

* Requested audience is respected.
* Requested length is respected.
* Style is consistent.
* Output is usable for its intended purpose.

---

# 24. Output Failure Conditions

The agent must stop or qualify the output when it cannot safely satisfy the request.

Examples:

* missing critical Scripture information
* unavailable required source material
* unsupported factual claims
* unresolved critical theological conflict
* requested quotation cannot be verified
* requested output depends on information not present in state
* source provenance has been lost
* output would require fabrication

The agent should identify what is missing and provide the maximum useful output that can be produced safely.

---

# 25. User Control

The preacher remains the owner of the final sermon.

The agent should not silently:

* change theological positions
* change the sermon thesis
* remove Scripture
* add controversial claims
* alter intended application
* replace the preacher's voice
* present generated material as user-authored

The user may accept, reject, modify, or request regeneration of generated material.

---

# 26. Output Transparency

When useful, the system should allow the user to understand:

* where important claims came from
* which material is Scripture
* which material is research
* which material is generated
* which areas remain uncertain
* which findings remain unresolved
* which revisions changed the sermon

Transparency should not make normal sermon output unnecessarily cumbersome.

The system should expose complexity primarily when it helps the user make an informed decision about the sermon.

---

# 27. Separation of Preparation and Presentation

The agent should distinguish between material intended for preparation and material intended for presentation.

For example:

### Preparation

May contain:

* detailed research
* competing interpretations
* source notes
* theological analysis
* evaluation findings
* unresolved questions

### Presentation

Should generally contain:

* sermon language
* Scripture
* necessary explanation
* illustrations
* application
* transitions
* conclusion

Research should inform the sermon without automatically appearing in the sermon.

---

# 28. Output Pipeline

The conceptual output pipeline is:

```text
User Output Request
        ↓
Determine Output Type
        ↓
Load Relevant Sermon State
        ↓
Check Readiness
        ↓
Resolve Output Constraints
        ↓
Select Relevant Evidence
        ↓
Generate Output
        ↓
Apply Style
        ↓
Validate Biblical Integrity
        ↓
Validate Theological Integrity
        ↓
Validate Research Integrity
        ↓
Validate Structural Integrity
        ↓
Validate Communication Requirements
        ↓
Return Output
```

Validation occurs after generation and before final delivery.

---

# 29. Relationship to Evaluation

Evaluation identifies problems.

Output generation must respect those findings.

If a critical or major finding remains unresolved, the output system should not silently hide it when doing so would materially affect the integrity of the output.

Depending on the output type, the system may:

* surface the finding
* qualify the output
* produce a partial output
* recommend revision before finalization

Evaluation and output are separate responsibilities.

---

# 30. Relationship to Revision

Revision changes sermon state.

Output reflects sermon state.

Therefore:

```text
Evaluation
    ↓
Revision
    ↓
Updated State
    ↓
Output
```

The output system should not perform substantive revision merely because the requested output format would be easier to produce that way.

If substantive changes are necessary, they belong in the revision workflow.

---

# 31. Output Completion Contract

An output is complete when:

1. The requested output type has been produced.
2. The output is based on the current applicable sermon state.
3. Required source relationships are preserved.
4. Scripture handling requirements are satisfied.
5. Theological constraints are satisfied.
6. Research integrity requirements are satisfied.
7. Known critical issues are not silently concealed.
8. Requested audience, length, and format are respected.
9. The output has passed applicable validation.
10. The output is usable for its intended purpose.

Completion does not mean the sermon is objectively perfect.

It means the requested transformation has been completed without violating the system's governing constraints.

---

# 32. Non-Goals

The output system is not responsible for:

* deciding what the preacher should believe
* replacing theological study
* replacing pastoral judgment
* independently inventing doctrine
* fabricating supporting evidence
* hiding uncertainty
* optimizing sermons for popularity
* maximizing emotional response at the expense of faithfulness
* replacing human ownership of the sermon

---

# 33. Guiding Principle

The output system exists to turn accumulated sermon work into usable communication without losing the integrity of the work that produced it.

**The agent should make the sermon clearer and more usable without making it less faithful, less traceable, or less human-owned.**
