# Research Specification

## 1. Purpose

The Research Specification defines how the Sermon Research Assistant performs, evaluates, records, and applies research during sermon development.

It translates `research_policy.md` into an operational process.

Research exists to establish reliable information that can support sermon development.

The agent should research **to answer meaningful questions**, not simply to accumulate information.

---

# 2. Research Principles

Research must follow these principles:

1. Research must serve the sermon.
2. Sources must be identifiable.
3. Claims must be distinguishable from interpretations.
4. Important factual claims should be supported by appropriate evidence.
5. Scripture and external research must remain distinct.
6. Conflicting evidence should be preserved rather than hidden.
7. Uncertainty should be represented explicitly.
8. The agent must not fabricate sources, quotations, findings, or citations.
9. Research should stop when additional research is unlikely to materially improve the sermon.
10. Research findings must be stored in sermon state so they can be reused.

---

# 3. Research Entry Conditions

Research may begin when:

* The user explicitly requests research.
* The sermon requires factual or historical context.
* Scripture interpretation requires contextual research.
* The agent identifies an important unanswered question.
* Evaluation identifies an unsupported claim.
* The user provides a claim that requires verification.

Research should not automatically begin for every sermon request.

If sufficient evidence already exists in the sermon state, the agent should reuse it.

---

# 4. Research Questions

Research should begin with explicit questions.

A research question should identify:

```text
Question
Purpose
Importance
Related sermon element
```

Conceptually:

```yaml
research_question:
  id:
  question:
  purpose:
  importance:
  related_element_id:
  status:
```

Possible statuses:

```text
open
researching
answered
partially_answered
unresolved
not_needed
```

---

# 5. Research Planning

Before conducting substantial research, the agent should determine:

1. What needs to be known?
2. Why does it matter?
3. What type of source can answer the question?
4. How much evidence is necessary?
5. When should research stop?

Research planning should prevent unnecessary searches.

For example:

```text
Sermon Claim
    ↓
Research Question
    ↓
Required Evidence
    ↓
Source Strategy
```

---

# 6. Research Categories

The agent should classify research according to its purpose.

Possible categories include:

### Biblical Context

Research related to:

* Historical setting
* Cultural setting
* Literary context
* Geography
* Authorship
* Audience
* Original-language questions
* Related biblical material

### Historical Context

Research related to:

* Historical events
* People
* Institutions
* Cultural practices
* Political circumstances
* Social conditions

### Theological Research

Research related to:

* Interpretive traditions
* Doctrinal questions
* Historical theological positions
* Major interpretive disagreements

### Cultural Research

Research related to:

* Contemporary culture
* Social trends
* Common experiences
* Definitions
* Relevant statistics

### Illustrative Research

Research used to establish factual examples that may be useful as illustrations.

### Claim Verification

Research used to determine whether an existing claim is adequately supported.

---

# 7. Source Strategy

The agent should select sources according to the question being researched.

Source selection should consider:

* Authority
* Relevance
* Primary vs secondary status
* Publication quality
* Date
* Context
* Specificity
* Corroboration

The most authoritative available source should generally be preferred when directly relevant.

However, source authority must be evaluated relative to the question.

A primary historical document may be preferable to a secondary summary when establishing what a historical figure actually said.

A scholarly secondary source may be more useful when evaluating competing interpretations.

---

# 8. Source Types

Sources may include:

* Biblical texts
* Primary historical documents
* Academic publications
* Scholarly books
* Established reference works
* University resources
* Museums and archives
* Government sources
* Reputable organizations
* Established journalism
* Specialist publications

The agent should avoid treating every internet page as equivalent evidence.

---

# 9. Source Record

Each source should be represented in research state.

Conceptually:

```yaml
source:
  id:
  title:
  author:
  publisher:
  source_type:
  url:
  publication_date:
  accessed_at:
  relevance:
  authority_notes:
```

Additional metadata may be added by the implementation.

The source record should identify the source sufficiently for later verification.

---

# 10. Source Evaluation

A source should be evaluated against the research question.

The agent should consider:

### Relevance

Does the source actually address the question?

### Authority

Does the source have appropriate expertise or primary-source status?

### Specificity

Does it provide evidence for the particular claim being investigated?

### Reliability

Are there reasons to question its accuracy?

### Corroboration

Is the finding supported by other independent sources?

### Currency

Does publication date matter for this question?

Currency should not automatically outweigh historical or foundational sources.

---

# 11. Search Process

The research process should generally follow:

```text
Research Question
      ↓
Initial Search
      ↓
Candidate Sources
      ↓
Source Evaluation
      ↓
Evidence Extraction
      ↓
Corroboration
      ↓
Finding
```

The agent should progressively narrow searches as understanding improves.

Broad searches should generally be followed by targeted searches.

---

# 12. Search Iteration

The agent may perform multiple searches for one research question.

A useful progression is:

```text
Broad Question
    ↓
Identify Concepts
    ↓
Identify Relevant Sources
    ↓
Target Specific Claim
    ↓
Verify
```

The agent should not repeatedly search the same question without a reason.

Each subsequent search should have a purpose.

---

# 13. Evidence Extraction

The agent should extract findings from sources rather than treating entire sources as evidence.

A finding should contain:

```yaml
finding:
  id:
  source_id:
  statement:
  evidence:
  relevance:
  confidence:
```

The exact structure may evolve during implementation.

The finding should represent what the source actually supports.

---

# 14. Source vs Finding vs Claim

The system must maintain a distinction between:

```text
SOURCE
The document or resource.

FINDING
What the source provides.

CLAIM
What the sermon asserts.
```

For example:

```text
Source
  ↓
Finding: historical fact
  ↓
Claim: sermon interpretation/application
```

The agent must not treat the sermon claim as though the source directly stated it unless the source actually does.

---

# 15. Direct Quotes

When quotations are used:

1. The source must be identifiable.
2. The quotation must be faithful to the source.
3. The context should be considered.
4. The agent must not invent quotations.
5. The agent should avoid unnecessary quotation when paraphrasing is sufficient.

When exact quotation cannot be verified, the agent should paraphrase or explicitly identify the uncertainty.

---

# 16. Statistics

Statistics require additional scrutiny.

When using a statistic, the agent should attempt to establish:

* Original source
* Population
* Sample
* Date
* Methodology when relevant
* What the statistic actually measures
* Whether the statistic remains relevant

The agent must not present a statistic without context when that context materially affects interpretation.

---

# 17. Historical Claims

Historical claims should be treated carefully.

The agent should distinguish between:

```text
Documented historical fact
Historical interpretation
Traditional account
Disputed claim
Illustrative retelling
```

A disputed historical claim should not be presented as settled fact.

When historians disagree materially, the agent should record the disagreement.

---

# 18. Theological Research

Theological research must remain distinct from the theological profile.

The theological profile establishes the framework in which the sermon is being developed.

Theological research investigates questions within or relevant to that framework.

The agent should be capable of identifying:

```text
Profile Position
    ↓
Research Question
    ↓
Relevant Interpretations
    ↓
Evidence
    ↓
Compatibility / Tension
```

Research should not silently modify the theological profile.

---

# 19. Conflicting Sources

When credible sources conflict, the agent should not simply select the preferred answer without examination.

It should:

1. Identify the disagreement.
2. Determine what the disagreement concerns.
3. Evaluate the sources.
4. Determine whether the conflict can be resolved.
5. Preserve meaningful uncertainty when it cannot.

Conceptually:

```yaml
conflict:
  question:
  sources:
  positions:
  basis_of_disagreement:
  resolution:
  unresolved:
```

---

# 20. Confidence

Research findings should have an internal confidence assessment.

Possible levels:

```text
high
moderate
low
uncertain
```

Confidence should reflect the quality and consistency of evidence.

It should not represent how strongly the agent "believes" something.

The agent should not use confidence as a substitute for evidence.

---

# 21. Corroboration

Corroboration may increase confidence when multiple independent sources support the same finding.

However, multiple sources that merely repeat the same underlying source should not be treated as independent corroboration.

The agent should distinguish:

```text
Independent corroboration
```

from:

```text
Repeated reporting
```

---

# 22. Research Findings and Sermon Claims

Research findings should be linked to the sermon elements they support.

Conceptually:

```text
Research Question
       ↓
Source
       ↓
Finding
       ↓
Evidence
       ↓
Claim
       ↓
Sermon Section
```

This relationship should be preserved in sermon state.

---

# 23. Research Relevance

Every research finding should have a reason for existing.

Possible relevance categories:

```text
interpretation
context
support
clarification
correction
illustration
application
verification
```

If a finding has no meaningful relationship to the sermon, it should not automatically become sermon content.

---

# 24. Research Stopping Conditions

Research should stop when the relevant questions have been sufficiently answered.

The agent should consider research complete when:

1. Major research questions have been answered.
2. Important claims have adequate support.
3. Relevant credible sources have been considered.
4. Major conflicts have been addressed.
5. Remaining uncertainty is understood.
6. Additional research is unlikely to materially change the sermon.

The agent should not continue researching indefinitely.

---

# 25. Research Depth

Research depth should be proportional to the importance of the claim.

A minor illustrative detail does not necessarily require the same research effort as:

* A central historical claim
* A major theological claim
* A disputed interpretation
* A claim upon which the sermon thesis depends

Conceptually:

```text
Claim Importance
      ↓
Required Research Depth
```

---

# 26. Research Budget

The implementation should eventually support practical limits on research.

Possible constraints include:

* Maximum searches
* Maximum sources
* Maximum research time
* Maximum token usage
* User-requested depth

These limits should control resource usage without encouraging premature conclusions.

---

# 27. Research Reuse

Existing research should be reused when relevant.

If the sermon state already contains sufficient evidence for a question, the agent should not repeat the research unnecessarily.

However, the agent should re-verify information when:

* The information may have changed.
* The source is no longer available.
* Evaluation identifies a problem.
* The claim has become more important.
* The existing evidence is insufficient.

---

# 28. Research Updates

If new research contradicts a previously accepted finding, the agent should not silently overwrite the old finding.

Instead:

```text
Existing Finding
      ↓
New Evidence
      ↓
Conflict Identified
      ↓
Re-evaluation
      ↓
Updated Finding
```

The original finding should remain recoverable as part of the research history.

---

# 29. User-Provided Research

The user may provide:

* Articles
* Books
* Notes
* Quotes
* Links
* Research summaries
* Personal observations

User-provided information should be stored separately from independently verified research.

The agent may use it as input but should not automatically treat it as independently verified.

---

# 30. Research Output

A research result should be useful to the next stage of sermon development.

The agent should generally produce:

```text
Research Questions
Sources
Key Findings
Evidence
Conflicts
Uncertainty
Implications for Sermon
Open Questions
```

The output should emphasize information that affects sermon development.

---

# 31. Research State Update

After a research operation, the agent should update sermon state with:

```text
Research Questions
Sources
Findings
Evidence
Conflicts
Confidence
Unresolved Questions
Related Claims
Workflow Status
```

Research should therefore become part of the persistent sermon state rather than existing only in the current conversation.

---

# 32. Research Failure

If research cannot establish an answer, the agent should record the limitation.

For example:

```yaml
research_question:
  status: unresolved
  reason: insufficient_reliable_evidence
```

The agent should then determine whether:

* More research is warranted.
* The claim should be weakened.
* The claim should be removed.
* The user should make a decision.
* The uncertainty should be explicitly acknowledged.

---

# 33. Research Integrity Rules

The agent must never:

1. Invent a source.
2. Invent a quotation.
3. Invent a citation.
4. Attribute a claim to a source that does not support it.
5. Present an inference as though it were directly documented.
6. Hide meaningful disagreement between sources.
7. Manufacture corroboration.
8. Use generated text as evidence.
9. Pretend a search was performed when it was not.
10. Claim verification that did not occur.

---

# 34. Relationship to Scripture Research

Scripture research is subject to `scripture_policy.md`.

This specification governs the **research process**, while the Scripture Policy governs how Scripture itself should be interpreted and used.

The distinction is:

```text
research_spec.md
    ↓
How research is conducted

scripture_policy.md
    ↓
How Scripture is handled
```

Both apply when researching biblical context.

---

# 35. Relationship to Evaluation

Evaluation may generate new research questions.

For example:

```text
Evaluation
    ↓
"Historical claim insufficiently supported"
    ↓
New Research Question
    ↓
Research
    ↓
Updated Evidence
    ↓
Re-evaluation
```

Research is therefore not limited to the initial research phase.

---

# 36. Research Completion Contract

A research stage is complete when:

```text
✓ Relevant questions identified
✓ Appropriate sources investigated
✓ Important findings extracted
✓ Sources recorded
✓ Claims supported where necessary
✓ Conflicts identified
✓ Meaningful uncertainty preserved
✓ Research state updated
✓ Remaining questions identified
✓ Additional research is not currently necessary
```

The sermon may still return to research later.

Completion means the research is currently sufficient for the next stage.

---

# 37. Guiding Principle

The research system should optimize for:

```text
Useful Evidence
+
Source Integrity
+
Traceability
+
Appropriate Depth
+
Intellectual Honesty
```

The goal is not to produce the largest research file.

The goal is to give the sermon development process **enough trustworthy information to reason well**.
