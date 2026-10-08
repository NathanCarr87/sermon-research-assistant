# Sermon Evaluation Specification

## 1. Purpose

The Sermon Evaluation Specification defines how the Sermon Research Assistant evaluates sermon material during development.

Evaluation exists to identify:

* Strengths worth preserving
* Errors requiring correction
* Unsupported claims
* Interpretive problems
* Structural weaknesses
* Theological inconsistencies
* Communication problems
* Weak or disconnected applications
* Opportunities for improvement

Evaluation is an **analysis and feedback process**, not a final judgment of the preacher or the spiritual value of a sermon.

The evaluator should produce useful findings that can be acted upon during revision.

---

# 2. Governing Authority

Evaluation must operate according to:

1. `constitution.md`
2. `theological-profile.yaml`
3. `theology.md`
4. `scripture_policy.md`
5. `research_policy.md`
6. `sermon_style.md`
7. `sermon_structure.md`
8. `sermon_development.md`
9. `sermon_evaluation.md`
10. `sermon_revision.md`
11. `sermon_output.md`

This specification defines the evaluation process.

It does not redefine the standards being evaluated.

---

# 3. Evaluation Principles

The evaluator must:

1. Evaluate against established requirements.
2. Distinguish factual errors from stylistic preferences.
3. Distinguish theological disagreement from demonstrable inconsistency with the active profile.
4. Identify evidence for substantive findings.
5. Avoid inventing problems simply to produce feedback.
6. Preserve strengths while identifying weaknesses.
7. Prioritize material problems over cosmetic issues.
8. Provide actionable findings.
9. Avoid treating numerical scores as a substitute for reasoning.
10. Make uncertainty visible.

---

# 4. Evaluation Inputs

Evaluation may operate on:

* Sermon idea
* Scripture interpretation
* Research findings
* Thesis
* Outline
* Partial draft
* Complete manuscript
* Application
* Final sermon output

The evaluator should evaluate only what is sufficiently developed to assess.

For example, a partial outline should not be evaluated as though it were a finished manuscript.

---

# 5. Evaluation Modes

The system should support several evaluation modes.

### Diagnostic

Used to identify potential problems during development.

```text
Material
→ Findings
```

### Structural

Focused on sermon organization.

```text
Thesis
→ Movements
→ Claims
→ Flow
```

### Biblical / Interpretive

Focused on Scripture handling.

```text
Passage
→ Interpretation
→ Sermon Claims
```

### Theological

Focused on consistency with the active theological framework.

### Research

Focused on evidence and source integrity.

### Communication

Focused on clarity, language, transitions, illustrations, and audience accessibility.

### Final

A comprehensive evaluation performed before final output.

---

# 6. Evaluation Process

The general evaluation process is:

```text
Sermon Material
      ↓
Load Relevant State
      ↓
Identify Applicable Standards
      ↓
Inspect Material
      ↓
Identify Findings
      ↓
Verify Findings
      ↓
Prioritize Findings
      ↓
Produce Recommendations
      ↓
Update Evaluation State
```

The evaluator should have access to the evidence and governing material necessary to make the evaluation.

---

# 7. Evaluation Dimensions

The evaluator should consider the following dimensions.

## 7.1 Biblical Faithfulness

Evaluate whether the sermon represents its primary biblical material responsibly.

Questions include:

* Does the sermon accurately represent the passage?
* Are important contextual considerations ignored?
* Are verses being used in ways disconnected from their context?
* Are conclusions supported by the text?
* Are distinctions between interpretation and application maintained?

---

## 7.2 Interpretive Integrity

Evaluate the reasoning connecting Scripture to sermon claims.

Questions include:

* Is the interpretation plausible from the text?
* Is important context being ignored?
* Is the sermon importing an idea into the passage?
* Are interpretive assumptions visible?
* Are disputed interpretations presented appropriately?

The evaluator should distinguish between:

```text
Clearly unsupported interpretation
```

and:

```text
Legitimate interpretive disagreement
```

---

## 7.3 Theological Consistency

Evaluate the sermon against the active theological profile and governing theology.

Questions include:

* Does the sermon contradict an established theological commitment?
* Are theological claims internally consistent?
* Does the sermon introduce a theological position without adequate support?
* Does the application depend on an unstated theological assumption?

The evaluator should not substitute its own theological preferences for the configured theological framework.

---

## 7.4 Research Integrity

Evaluate factual and research-dependent claims.

Questions include:

* Is the claim supported?
* Is the source appropriate?
* Is the source being represented accurately?
* Is a quotation verifiable?
* Is a statistic sufficiently contextualized?
* Is a historical claim appropriately qualified?
* Are conflicting sources being handled honestly?

---

## 7.5 Thesis Clarity

Evaluate the central proposition.

Questions include:

* Is there a recognizable central idea?
* Is it sufficiently specific?
* Is it supported by the sermon?
* Does the sermon actually develop the stated thesis?
* Does the conclusion reinforce the central idea?

---

## 7.6 Structural Coherence

Evaluate the relationship between sermon components.

Questions include:

* Does each major movement serve the thesis?
* Is the progression understandable?
* Are sections redundant?
* Are transitions meaningful?
* Does the conclusion follow from the development?
* Are major ideas given appropriate weight?

---

## 7.7 Development

Evaluate whether the sermon adequately develops its ideas.

Questions include:

* Are claims explained?
* Is there sufficient reasoning?
* Are Scripture references integrated rather than merely listed?
* Are illustrations serving the argument?
* Are applications connected to the preceding material?

---

## 7.8 Application

Evaluate whether application follows from the sermon.

Questions include:

* Is the application connected to the biblical argument?
* Is it specific enough to be useful?
* Does it address the intended audience?
* Does it avoid unsupported assumptions about the audience?
* Does it provide meaningful response rather than generic encouragement?

---

## 7.9 Communication

Evaluate:

* Clarity
* Accessibility
* Sentence complexity
* Terminology
* Transitions
* Repetition
* Pacing
* Redundancy
* Emotional and rhetorical movement

Communication findings should not override theological or biblical requirements.

---

## 7.10 Style

Evaluate consistency with `sermon_style.md`.

Style findings should generally have lower priority than:

* Biblical problems
* Theological problems
* Unsupported factual claims
* Structural problems

unless the style issue materially interferes with communication.

---

# 8. Finding Types

Evaluation findings should be categorized.

Possible categories:

```text
biblical
interpretive
theological
research
evidence
thesis
structure
development
application
communication
style
technical
```

A finding should have one primary category.

Secondary relationships may be represented separately.

---

# 9. Severity

Severity describes the effect of a problem on the sermon.

Recommended levels:

```text
critical
major
moderate
minor
```

### Critical

A problem that materially compromises the sermon.

Examples:

* Major misrepresentation of Scripture
* Fabricated evidence
* Serious theological contradiction
* Central claim unsupported by the sermon

### Major

A problem that significantly weakens the sermon.

Examples:

* Thesis substantially disconnected from the passage
* Major unsupported factual claim
* Structural breakdown
* Significant application problem

### Moderate

A meaningful issue that should be addressed but does not undermine the entire sermon.

Examples:

* Weak transition
* Underdeveloped point
* Redundant section
* Insufficient contextual explanation

### Minor

A relatively small improvement.

Examples:

* Awkward wording
* Minor repetition
* Small clarity issue

Severity should describe **material impact**, not how strongly the evaluator dislikes the material.

---

# 10. Finding Structure

Each substantive finding should contain:

```yaml
finding:
  id:
  category:
  severity:
  description:
  affected_element_id:
  evidence:
  recommendation:
  status:
```

The description should identify the actual problem.

The evidence should explain why the evaluator reached that conclusion.

The recommendation should provide a practical path forward.

---

# 11. Finding Validation

Before creating a finding, the evaluator should ask:

1. Is this actually a problem?
2. Which governing requirement does it relate to?
3. What evidence supports the finding?
4. Is it material?
5. Is it a factual problem, interpretive issue, theological issue, or preference?
6. Can the problem be corrected?

This reduces false-positive criticism.

---

# 12. Preference vs Problem

The evaluator must distinguish between:

```text
Requirement violation
```

and:

```text
Preference
```

For example:

> "This transition could be shorter."

is different from:

> "This transition obscures the relationship between the two sermon movements."

The first may be a stylistic preference.

The second identifies a structural communication problem.

Preferences should not be presented as objective defects.

---

# 13. Strengths

Evaluation should identify meaningful strengths.

Strengths may include:

* Strong biblical connection
* Clear thesis
* Effective structure
* Well-supported claims
* Useful application
* Strong illustration
* Effective progression
* Clear communication
* Consistency across sections

Strengths should be specific enough to preserve during revision.

The evaluator should avoid generic praise.

---

# 14. Recommendations

Recommendations should be actionable.

Weak:

```text
"Make this better."
```

Useful:

```text
"Clarify the connection between the second movement and the thesis by
stating how the passage supports the movement before introducing the
application."
```

Recommendations should identify the likely change rather than merely identifying the problem.

---

# 15. Evaluation Prioritization

Findings should be prioritized by material importance.

The general order is:

```text
Biblical / theological integrity
        ↓
Research / factual integrity
        ↓
Thesis
        ↓
Structure
        ↓
Development
        ↓
Application
        ↓
Communication
        ↓
Style / polish
```

This is a **workflow priority**, not a quality ranking.

A minor style issue should not distract from a major interpretive problem.

---

# 16. Evaluation Without Numerical Scoring

The evaluator should not reduce sermon quality to a single numerical score.

A number can conceal important differences between problems.

Instead, evaluation should provide:

```text
Strengths
Critical Findings
Major Findings
Moderate Findings
Minor Findings
Recommended Actions
Open Questions
```

If an implementation later uses internal metrics, those metrics must not replace the substantive evaluation.

---

# 17. Cross-Reference Evaluation

Evaluation should use the relationships stored in sermon state.

For example:

```text
Claim
 ↓
Evidence
 ↓
Source
```

The evaluator can then determine whether:

* Evidence actually supports the claim.
* The source is being represented accurately.
* The claim exceeds the evidence.
* The claim requires qualification.

Likewise:

```text
Thesis
 ↓
Movement
 ↓
Claim
```

allows evaluation of structural alignment.

---

# 18. Scripture Cross-Reference

The evaluator should be able to trace sermon claims back to Scripture where applicable.

Conceptually:

```text
Sermon Claim
     ↓
Scripture Reference
     ↓
Relevant Passage
     ↓
Interpretation
```

If the sermon makes a claim that appears to depend on Scripture but has no meaningful biblical basis, the evaluator may identify this as a finding.

Not every sentence requires a direct Scripture citation.

The requirement is meaningful biblical grounding, not mechanical citation density.

---

# 19. Research Cross-Reference

Research-dependent claims should be traceable to research findings.

```text
Claim
 ↓
Finding
 ↓
Source
```

If no adequate evidence exists, the evaluator should identify the claim as:

* unsupported
* insufficiently supported
* uncertain
* requiring verification

The evaluator should not automatically recommend removing a claim if additional research could resolve the problem.

---

# 20. Theological Cross-Reference

The evaluator should compare theological claims against:

```text
Theological Profile
        +
Theology Policy
        +
Relevant Scripture
```

If a potential conflict exists, the evaluator should identify the specific conflict.

It should not merely say:

> "This theology seems wrong."

Instead:

> "This statement appears inconsistent with the configured position on X because the sermon asserts Y."

---

# 21. Audience Evaluation

The evaluator should consider the intended audience from sermon state.

Questions include:

* Is terminology appropriate?
* Are assumptions about the audience justified?
* Is application relevant to the stated context?
* Are explanations sufficient for the intended audience?

The evaluator must not invent demographic or personal characteristics that are not established in sermon state.

---

# 22. Length and Pacing

Length should be evaluated relative to the user's requested format and intended use.

The evaluator should identify:

* Unnecessary repetition
* Excessive development
* Underdeveloped sections
* Uneven emphasis
* Long sections that do not advance the argument

The evaluator should not optimize for a universal sermon length.

---

# 23. Evaluation of Illustrations

Illustrations should be evaluated for:

* Accuracy
* Relevance
* Clarity
* Connection to the sermon
* Appropriate emotional weight
* Whether the illustration supports rather than replaces the argument

Factual illustrations should be checked according to the research requirements.

Invented illustrations should be identifiable as hypothetical or illustrative.

---

# 24. Evaluation of Application

The evaluator should verify:

```text
Biblical Claim
    ↓
Theological Meaning
    ↓
Practical Implication
```

Application should not appear to be an unrelated moral lesson added after the sermon.

Where application makes assumptions about people's circumstances, the evaluator should check whether those assumptions are justified.

---

# 25. Final Evaluation

A final evaluation should inspect the sermon as a complete system.

It should consider:

```text
Scripture
Research
Theology
Thesis
Structure
Development
Application
Communication
Output
```

The evaluator should determine whether unresolved material problems remain.

The final evaluation should produce:

```text
Summary
Strengths
Critical Findings
Major Findings
Moderate Findings
Minor Findings
Recommended Revisions
Open Questions
```

---

# 26. Revision Loop

Evaluation feeds directly into revision.

The standard cycle is:

```text
Draft
 ↓
Evaluate
 ↓
Findings
 ↓
Prioritize
 ↓
Revise
 ↓
Evaluate Again
```

Evaluation findings should remain linked to the revisions that address them.

Conceptually:

```text
Finding
 ↓
Revision
 ↓
Resolution
```

---

# 27. Finding Resolution

A finding may become:

```text
open
accepted
resolved
rejected
```

### Open

The issue has not yet been addressed.

### Accepted

The user or system has consciously decided to retain the issue.

### Resolved

The issue has been addressed.

### Rejected

The finding was determined not to represent a valid problem.

Rejected findings should retain their reasoning where practical.

---

# 28. Regression Detection

After revision, the evaluator should consider whether the revision introduced new problems.

For example:

```text
Fix Structure
    ↓
Creates Redundancy

Fix Theology
    ↓
Breaks Thesis

Shorten Section
    ↓
Removes Necessary Explanation
```

Revision should therefore trigger re-evaluation of affected dependencies.

---

# 29. Evaluation Completion

An evaluation run is complete when:

```text
✓ Applicable standards identified
✓ Material examined
✓ Findings validated
✓ Findings categorized
✓ Severity assigned
✓ Evidence recorded
✓ Strengths identified
✓ Recommendations produced
✓ State updated
```

A completed evaluation does not necessarily mean the sermon is ready for output.

It means the evaluation itself is complete.

---

# 30. Definition of Evaluation Readiness

A sermon is ready for final-output consideration when:

```text
✓ No unresolved critical findings
✓ No unresolved major findings that materially affect the sermon
✓ Important factual claims are adequately supported
✓ Major biblical / interpretive concerns are addressed
✓ Theological consistency has been checked
✓ Thesis and structure remain coherent
✓ Application remains connected to the sermon
✓ User decisions have been respected
```

Minor and stylistic findings may remain when they do not materially affect the sermon.

---

# 31. Failure Handling

If the evaluator lacks sufficient information to determine whether something is a problem, it should not manufacture certainty.

Instead it should record:

```yaml id="1l7lgi"
status: uncertain
reason:
required_information:
```

The system may then:

* Request additional research
* Ask the user
* Mark the issue unresolved
* Continue with an explicit limitation

---

# 32. Evaluation Integrity Rules

The evaluator must never:

1. Invent evidence for a criticism.
2. Invent a theological contradiction.
3. Treat personal stylistic preference as objective failure.
4. Present disputed interpretation as unquestionably erroneous without appropriate qualification.
5. Hide uncertainty.
6. Remove strengths simply because weaknesses exist.
7. Generate criticism solely to produce more findings.
8. Treat numerical scores as sufficient evaluation.
9. Claim that a finding has been resolved when it has not.
10. Modify sermon content while performing evaluation unless explicitly operating in a revision step.

---

# 33. Evaluation State Contract

Each evaluation run should update sermon state with:

```text
Evaluation Run
    ↓
Findings
    ↓
Strengths
    ↓
Recommendations
    ↓
Open Questions
    ↓
Workflow State
```

Each finding should retain a relationship to the sermon element it concerns.

---

# 34. Relationship to Revision

`sermon_evaluation.md` defines the standards and philosophy of evaluation.

This specification defines the operational process for applying those standards.

`sermon_revision.md` defines how identified problems should be addressed.

Therefore:

```text
sermon_evaluation.md
        ↓
What should be evaluated?

evaluation_spec.md
        ↓
How is evaluation performed?

sermon_revision.md
        ↓
How should identified problems be addressed?
```

---

# 35. Guiding Principle

The evaluation system should optimize for:

```text
Truth
+
Faithfulness
+
Clarity
+
Coherence
+
Actionable Feedback
```

The evaluator's purpose is not to criticize the sermon.

Its purpose is to help determine:

> **What is working, what is not adequately supported or developed, why, and what should be considered next.**

Evaluation should make revision more intelligent, more transparent, and more useful.
