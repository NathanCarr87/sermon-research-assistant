# Sermon State Model

## 1. Purpose

The Sermon State Model defines the information the Sermon Research Assistant maintains while developing a sermon.

It provides a persistent representation of the sermon across research, interpretation, development, evaluation, revision, and output.

The state model is not itself a database schema.

It defines the **conceptual structure and relationships of sermon information** so that implementation can later determine how that information is persisted.

The state must allow the agent to:

* Continue work across sessions
* Understand what has already been completed
* Preserve research and evidence
* Trace claims back to their sources
* Track the sermon from idea to final output
* Preserve evaluation findings
* Track revisions
* Avoid unnecessarily repeating completed work

---

# 2. State Principles

Sermon state should follow these principles.

### 2.1 Source Preservation

Original source material should be preserved whenever practical.

The system should distinguish between:

```text
Original Source
    ↓
Extracted Information
    ↓
Interpretation
    ↓
Sermon Claim
    ↓
Sermon Language
```

Generated material must not overwrite the underlying evidence.

---

### 2.2 Traceability

Important sermon claims should be traceable to their supporting material.

The system should be able to answer:

> "Why is this claim in the sermon?"

A useful conceptual relationship is:

```text
Sermon Claim
    ↓
Evidence
    ↓
Source
```

---

### 2.3 Separation of Concerns

Different types of information should remain distinct.

The system should not treat:

* Scripture
* Research
* Interpretation
* User instructions
* Sermon claims
* Generated prose
* Evaluation findings

as interchangeable information.

---

### 2.4 Incremental State

State should be updated as work progresses.

The agent should not need to regenerate an entire sermon state whenever one component changes.

For example, changing an introduction should not invalidate the research that supports the sermon.

---

### 2.5 Human Ownership

The state represents a sermon being developed **with the user**.

The system should distinguish between:

* User-approved material
* Agent-generated material
* Research-derived material
* Unresolved material
* Rejected material

The agent should not treat its own previous generation as automatically authoritative.

---

# 3. Top-Level Sermon State

A sermon should conceptually contain:

```text
SermonState
├── metadata
├── input
├── intent
├── scripture
├── research
├── theology
├── evidence
├── thesis
├── structure
├── development
├── evaluation
├── revisions
├── output
└── workflow
```

Each section is described below.

---

# 4. Metadata

Metadata identifies the sermon and its basic lifecycle information.

Conceptually:

```yaml
metadata:
  id:
  title:
  created_at:
  updated_at:
  version:
  status:
```

Possible statuses include:

```text
idea
researching
interpreting
structuring
developing
evaluating
revising
ready
completed
archived
```

Status represents the current workflow state.

It does not imply theological quality or completion.

---

# 5. Input

The input contains what the user originally brought to the system.

Conceptually:

```yaml
input:
  original_request:
  supplied_material:
  supplied_scripture:
  supplied_notes:
  supplied_sermon:
  constraints:
```

Original user input should be preserved.

The system should not silently rewrite the original request.

---

# 6. Intent

Intent represents what the user is trying to accomplish.

Conceptually:

```yaml
intent:
  topic:
  purpose:
  audience:
  desired_response:
  context:
  tone:
  constraints:
```

Not every field will always be known.

Unknown information should remain unknown rather than being fabricated.

The agent may update intent when the user clarifies their request.

---

# 7. Scripture State

Scripture state contains the biblical material relevant to the sermon.

Conceptually:

```yaml
scripture:
  primary_passages:
  supporting_passages:
  translations:
  context:
  observations:
  interpretive_questions:
  interpretive_findings:
```

Each passage should retain its reference.

Where the system stores textual excerpts, the source and translation should remain identifiable.

---

# 8. Research State

Research state contains research performed during sermon development.

Conceptually:

```yaml
research:
  questions:
  sources:
  findings:
  unresolved_questions:
```

Each research source should retain enough information to identify it later.

Conceptually:

```yaml
source:
  id:
  title:
  author:
  publisher:
  url:
  publication_date:
  accessed_at:
  source_type:
  reliability_notes:
```

The exact implementation may vary.

Research should be stored separately from conclusions drawn from that research.

---

# 9. Theology State

The theology section represents the theological framework relevant to this sermon.

Conceptually:

```yaml
theology:
  profile:
  relevant_doctrines:
  theological_questions:
  theological_decisions:
  unresolved_questions:
```

The active theological profile comes from:

```text
/docs/profiles/theological-profile.yaml
```

The sermon state may reference that profile rather than duplicating it.

If the theological profile changes, the system should be able to determine which sermon decisions were based upon it.

---

# 10. Evidence State

Evidence connects sources and observations to sermon claims.

This is one of the most important parts of the state model.

Conceptually:

```yaml
evidence:
  items:
    - id:
      type:
      content:
      source_id:
      scripture_reference:
      confidence:
      notes:
```

Evidence types may include:

```text
scripture
historical
theological
scholarly
cultural
user_provided
interpretive
other
```

Evidence should not be considered automatically authoritative simply because it exists.

Its relevance and strength should be evaluated according to the governing policies.

---

# 11. Claims

Sermon claims should be represented independently from the final prose.

Conceptually:

```yaml
claims:
  - id:
    statement:
    type:
    evidence_ids:
    scripture_ids:
    status:
    notes:
```

Possible claim types include:

```text
textual
historical
theological
interpretive
pastoral
application
illustrative
```

Possible statuses include:

```text
proposed
supported
uncertain
rejected
approved
```

This allows the system to distinguish:

> "The agent generated this sentence"

from:

> "The sermon makes this claim and here is the evidence supporting it."

---

# 12. Thesis State

The thesis contains the sermon’s central proposition.

Conceptually:

```yaml
thesis:
  statement:
  rationale:
  supporting_claim_ids:
  scripture_ids:
  status:
```

A thesis should not become final merely because the agent generated one.

It may progress through:

```text
candidate
→ developed
→ evaluated
→ approved
→ revised
```

If research materially changes the thesis, the state should preserve that change.

---

# 13. Structure State

Structure represents the sermon before it becomes full prose.

Conceptually:

```yaml
structure:
  introduction:
  movements:
    - id:
      title:
      purpose:
      claim_ids:
      scripture_ids:
      application:
  conclusion:
```

Each major movement should be traceable to the sermon thesis.

Conceptually:

```text
Thesis
  ↓
Movement
  ↓
Claim
  ↓
Evidence / Scripture
  ↓
Explanation
  ↓
Application
```

---

# 14. Development State

Development contains the actual sermon material being written.

Conceptually:

```yaml
development:
  introduction:
  sections:
  transitions:
  illustrations:
  applications:
  conclusion:
  manuscript:
```

The development layer should reference claims and structural elements rather than becoming a disconnected block of generated prose.

Where practical:

```text
Paragraph
    ↓
Section
    ↓
Claim
    ↓
Evidence
```

---

# 15. Evaluation State

Evaluation records the results of sermon evaluation.

Conceptually:

```yaml
evaluation:
  runs:
    - id:
      created_at:
      findings:
      strengths:
      concerns:
      recommendations:
      status:
```

A finding should be specific and actionable.

Conceptually:

```yaml
finding:
  id:
  category:
  description:
  affected_element_id:
  severity:
  recommendation:
  status:
```

Possible statuses:

```text
open
accepted
resolved
rejected
```

The evaluation record should remain available after revision so that the development history can be understood.

---

# 16. Revision State

Revision state records changes made in response to evaluation or user feedback.

Conceptually:

```yaml
revisions:
  - id:
    created_at:
    reason:
    affected_element_id:
    previous_content:
    revised_content:
    evaluation_finding_id:
    approved:
```

Not every minor wording change needs a revision record.

Revision tracking should focus on meaningful changes to:

* Theology
* Interpretation
* Thesis
* Structure
* Major claims
* Application
* Significant sermon content

---

# 17. Output State

Output represents generated deliverables.

Conceptually:

```yaml
output:
  requested_format:
  generated_artifacts:
    - id:
      type:
      version:
      created_at:
      content:
```

Possible artifact types include:

```text
research_notes
scripture_study
outline
sermon_manuscript
preaching_notes
evaluation
revision_summary
```

Outputs should reference the sermon state version from which they were generated.

---

# 18. Workflow State

Workflow state tracks where the sermon currently sits in the development process.

Conceptually:

```yaml
workflow:
  current_stage:
  completed_stages:
  active_questions:
  blockers:
  next_action:
```

Possible stages:

```text
intake
understanding
research
scripture
thesis
structure
development
evaluation
revision
output
complete
```

The workflow state should reflect actual progress rather than simply tracking the most recent agent action.

---

# 19. Dependencies

Some state elements depend upon others.

The primary dependency graph is:

```text
Input
  ↓
Intent
  ↓
Scripture + Research + Theology
  ↓
Evidence
  ↓
Claims
  ↓
Thesis
  ↓
Structure
  ↓
Development
  ↓
Evaluation
  ↓
Revision
  ↓
Output
```

However, the workflow is not strictly linear.

For example:

```text
Evaluation
    ↓
Research
    ↓
Evidence
    ↓
Claim
    ↓
Thesis
```

The system must therefore support returning to earlier stages when new information requires it.

---

# 20. Invalidation

Changes to one state element may invalidate dependent elements.

Examples:

### Scripture change

A significant change to the primary interpretation may require reconsideration of:

```text
Claims
Thesis
Structure
Development
Evaluation
```

### Thesis change

A thesis change may require reconsideration of:

```text
Structure
Development
Evaluation
```

### Wording change

A minor wording change may affect only:

```text
Development
Output
```

The implementation should eventually determine which dependencies must be re-evaluated automatically.

---

# 21. Versioning

Meaningful sermon state changes should be versionable.

Conceptually:

```text
Sermon v1
   ↓
Research
   ↓
Sermon v2
   ↓
Structure
   ↓
Sermon v3
   ↓
Evaluation
   ↓
Sermon v4
```

Versioning should allow the system to answer:

* What changed?
* Why did it change?
* What evidence supported the change?
* Which evaluation finding prompted it?
* What did the previous version contain?

The implementation may use snapshots, event history, or another mechanism.

This document does not prescribe the storage technology.

---

# 22. Provenance

Important information should retain provenance.

The system should distinguish between:

```text
USER
RESEARCH
SCRIPTURE
THEOLOGICAL_PROFILE
AGENT
```

For generated material, the system should retain the inputs or references that materially contributed to it when practical.

For example:

```yaml
provenance:
  origin: agent
  based_on:
    - claim_12
    - scripture_4
    - research_7
```

This allows the system to preserve transparency as the sermon becomes more developed.

---

# 23. Approval

Some state elements may require explicit user approval.

Examples include:

* Final thesis
* Major theological interpretation
* Major structural direction
* Significant application
* Final sermon

Approval should be represented explicitly when required.

Conceptually:

```yaml
approval:
  status:
  approved_by:
  approved_at:
```

The exact approval mechanism belongs to the implementation.

---

# 24. Rejected Material

Rejected material should not necessarily be deleted.

Where practical, the system should retain rejected:

* Claims
* Thesis candidates
* Structural approaches
* Research conclusions
* Illustrations
* Revisions

This allows the agent to avoid repeatedly proposing the same rejected approach.

Rejected material should not be treated as active sermon content.

---

# 25. Unresolved Questions

The state should maintain questions that remain unanswered.

Conceptually:

```yaml
unresolved_questions:
  - id:
    question:
    stage:
    importance:
    status:
```

Possible statuses:

```text
open
researching
blocked
resolved
accepted_as_uncertain
```

This prevents unresolved uncertainty from disappearing simply because the agent moved forward.

---

# 26. Minimal Viable State

A sermon does not need every possible state component to begin development.

The minimum viable state is:

```text
metadata
input
intent
scripture
research
thesis
structure
development
workflow
```

Additional components become necessary as the sermon matures:

```text
evidence
claims
evaluation
revisions
output
provenance
```

The implementation should allow these components to grow incrementally.

---

# 27. Persistence Requirements

The eventual implementation should persist enough state for the agent to resume work after the user leaves and returns later.

At minimum, persistence should preserve:

* Sermon identity
* User input
* Current stage
* Scripture selections
* Research
* Evidence
* Thesis
* Structure
* Current development
* Evaluation findings
* Revision history
* User decisions
* Unresolved questions

A new conversation should not require reconstruction of the sermon from scratch.

---

# 28. State Integrity Rules

The implementation must prevent the following:

1. Research being presented as Scripture.
2. Agent-generated material being represented as user-provided material.
3. Rejected material being treated as approved.
4. Unsupported claims being marked as supported without evidence.
5. Deleted or superseded material silently becoming current again.
6. Evaluation findings disappearing after revision.
7. Major theological changes occurring without being identifiable.
8. The sermon appearing complete when required stages remain unresolved.

---

# 29. Conceptual State Example

A mature sermon might therefore look conceptually like:

```text
SERMON
│
├── Metadata
│   ├── ID
│   ├── Title
│   ├── Version
│   └── Status
│
├── Input
│   └── User Request
│
├── Intent
│   ├── Audience
│   ├── Purpose
│   └── Context
│
├── Scripture
│   ├── Primary Passage
│   ├── Supporting Passages
│   └── Interpretation
│
├── Research
│   ├── Questions
│   ├── Sources
│   └── Findings
│
├── Evidence
│   └── Evidence Items
│
├── Claims
│   └── Sermon Claims
│
├── Thesis
│   └── Central Proposition
│
├── Structure
│   ├── Introduction
│   ├── Movement 1
│   ├── Movement 2
│   ├── Movement 3
│   └── Conclusion
│
├── Development
│   └── Sermon Manuscript
│
├── Evaluation
│   └── Findings
│
├── Revisions
│   └── Revision History
│
├── Output
│   └── Generated Artifacts
│
└── Workflow
    ├── Current Stage
    ├── Open Questions
    └── Next Action
```

---

# 30. Relationship to Agent Specification

`agent_spec.md` defines **what the agent does**.

`state_model.md` defines **what the agent knows and remembers while doing it**.

Together:

```text
Governing Documents
        ↓
  agent_spec.md
        ↓
 state_model.md
        ↓
Implementation
```

The implementation should use the state model to preserve continuity while using the agent specification to determine what actions should occur next.
