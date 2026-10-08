# Research Policy

## 1. Purpose

This document governs how Sermon Creator discovers, evaluates, records, and uses external information.

The research system exists to provide the sermon architect with a reliable body of evidence from which to reason.

Research is not the sermon.

Research informs the sermon.

The research agent must therefore prioritize:

- accuracy
- traceability
- relevance
- recency
- source quality
- intellectual honesty
- theological usefulness

over volume.

---

## 2. Research-First Principle

The system should research before constructing the final sermon.

The preferred pipeline is:

REQUEST
→ RESEARCH PLAN
→ SOURCE DISCOVERY
→ SOURCE EVALUATION
→ EVIDENCE EXTRACTION
→ EVIDENCE POOL
→ SERMON ARCHITECTURE

The sermon writer should not independently browse the web and introduce unsupported information.

---

## 3. Research Questions

Before researching, the agent should identify what it actually needs to know.

Research questions may include:

- What is happening?
- How common is it?
- What caused it?
- What do credible sources say?
- What historical context matters?
- What does Scripture say about the subject?
- What theological interpretations exist?
- What contemporary examples illuminate the issue?
- What evidence supports or contradicts the proposed claim?

The agent should avoid researching simply because information exists.

Every research item should have a potential purpose.

---

## 4. Research Scope

The research agent may investigate publicly accessible information including:

- current news
- government publications
- public datasets
- academic research
- books and published scholarship
- theological scholarship
- historical sources
- institutional reports
- cultural trends
- interviews
- public speeches
- public websites
- public transcripts
- publicly available multimedia
- relevant Christian resources

Access limitations must be respected.

The agent must never imply access to information it could not actually retrieve.

---

## 5. Source Hierarchy

When multiple sources are available, prefer sources according to the following hierarchy.

### Tier 1 — Primary Sources

Examples:

- original research papers
- government datasets
- official statistics
- court documents
- legislation
- original speeches
- official transcripts
- organizational reports
- original interviews
- original biblical texts

### Tier 2 — High-Quality Secondary Sources

Examples:

- peer-reviewed reviews
- reputable journalism
- established academic publications
- respected theological scholarship
- recognized research organizations

### Tier 3 — Reputable General Sources

Examples:

- established magazines
- professional publications
- respected educational resources
- reputable reference works

### Tier 4 — General Web Sources

Examples:

- blogs
- personal websites
- unspecialized commentary
- aggregators

These may provide leads but should generally not be the sole support for significant factual claims.

### Tier 5 — Social Media

Social media may be used to discover:

- emerging stories
- public reactions
- firsthand material
- cultural conversations

Social media should generally not be treated as authoritative evidence merely because something is widely shared.

---

## 6. Source Quality

Source quality should be evaluated independently from source popularity.

Consider:

- authority
- expertise
- methodology
- transparency
- primary vs secondary status
- editorial standards
- publication date
- corroboration
- potential conflicts of interest
- proximity to the original information

A highly shared source is not necessarily a highly reliable source.

---

## 7. Source Corroboration

Important claims should be corroborated when practical.

The greater the importance of a claim to the sermon, the stronger the expectation for corroboration.

Particular care should be taken with:

- statistics
- controversial claims
- political claims
- claims about individuals
- accusations
- medical claims
- scientific claims
- historical claims
- claims likely to change over time

A single weak source should not normally support a major sermon claim.

---

## 8. Current Information

Current events and changing information require special handling.

When the sermon uses current information, record:

- publication date
- retrieval date
- source
- original event date when known
- whether the information may have changed
- confidence level

Prefer the newest authoritative source available.

Do not treat an old statistic as current simply because it remains widely cited.

---

## 9. Breaking News

Breaking news requires heightened caution.

Early reporting may be:

- incomplete
- contradictory
- speculative
- incorrectly sourced
- subsequently corrected

The agent should avoid incorporating breaking information into a sermon unless:

1. the information is sufficiently verified, or
2. the sermon explicitly discusses uncertainty surrounding the event.

If facts remain uncertain, the uncertainty must be preserved.

---

## 10. Search Strategy

Research should proceed broadly before narrowing.

### Pass 1 — Discovery

Identify:

- major facts
- relevant sources
- terminology
- competing explanations
- significant perspectives

### Pass 2 — Verification

Verify the claims that appear useful.

Prefer:

- primary sources
- authoritative sources
- original studies
- direct quotations
- official records

### Pass 3 — Context

Determine:

- historical context
- limitations
- competing interpretations
- relevant caveats
- information that could materially change the conclusion

### Pass 4 — Evidence Extraction

Convert useful findings into structured evidence.

The sermon agent should consume the structured evidence rather than raw search results.

---

## 11. Evidence Objects

Every meaningful research finding should become an evidence object.

At minimum, an evidence object should contain:

- claim
- source
- source type
- publication date
- retrieval date
- confidence
- relevance
- intended use

The canonical Evidence Pool schema governs the structure.

---

## 12. Claims

A claim is a factual or interpretive statement that may be used in sermon construction.

Examples:

```text
"X percentage of Americans report..."

"The study found..."

"The organization reported..."

"Historically, Christians interpreted..."

"One theological tradition understands this passage as..."

Claims must be separated from:

source metadata
interpretations
assumptions
sermon applications
13. Claim Verification

Each claim should receive a verification status.

Use:

VERIFIED
The source directly supports the claim.

PARTIALLY VERIFIED
The source supports part of the claim but not all of it.

DISPUTED
Credible sources materially disagree.

UNVERIFIED
The claim could not be adequately confirmed.

REJECTED
The claim is contradicted, unreliable, fabricated, or otherwise unsuitable.

Only claims marked VERIFIED should normally be used as factual assertions in the final sermon.

PARTIALLY VERIFIED claims may be used only after narrowing or qualifying the language.

DISPUTED claims require explicit qualification.

UNVERIFIED and REJECTED claims must not appear as factual assertions.

14. Confidence

Confidence represents confidence in the evidence, not confidence in whether the sermon writer likes the claim.

Consider:

source quality
directness of evidence
corroboration
methodological quality
recency
agreement between credible sources

Confidence should not be artificially increased merely because multiple low-quality sources repeat the same information.

15. Statistics

Statistics require special scrutiny.

Whenever practical, record:

exact statistic
population
sample size
methodology
geographic scope
date
source
denominator
relevant limitations

Do not simplify a statistic in a way that materially changes its meaning.

For example:

"30% of respondents..."

must not automatically become:

"30% of Americans..."

unless the research actually supports that broader claim.

16. Scientific and Medical Claims

Scientific and medical claims should receive heightened scrutiny.

Prefer:

peer-reviewed research
systematic reviews
meta-analyses
government health agencies
major medical institutions
recognized scientific organizations

The agent must distinguish:

correlation
causation
hypothesis
established finding
preliminary finding

Do not convert preliminary research into settled fact.

17. Political and Social Claims

Political and socially controversial claims require:

high-quality sourcing
neutral characterization
corroboration
careful wording

The agent should distinguish between:

what happened
what someone claims happened
what an organization believes
what available evidence demonstrates
what remains disputed

The research agent must not convert partisan rhetoric into factual statements.

18. Historical Claims

Historical claims should be evaluated against reputable historical sources.

Avoid:

popular myths
unsourced anecdotes
inspirational legends
quotes with uncertain origins
simplified historical narratives that materially distort context

If a popular story is widely repeated but historically uncertain, identify it as such.

19. Quotes

Quotes must be verified before entering the Evidence Pool as quotations.

Verification should establish, when possible:

exact wording
speaker
original source
date
context

A quote attributed to a famous person without a reliable source should not be presented as authentic.

If the underlying idea is useful but the quotation cannot be verified:

paraphrase the idea
attribute it as a paraphrase
or remove it
20. Books

When books are referenced, distinguish between:

Directly Consulted

The system actually accessed relevant content from the book.

Bibliographic Reference

The system identified the book as relevant but did not access its contents.

Secondary Reference

The system learned about the book through another source.

The agent must never imply that it read a book merely because it knows the book exists.

21. Scripture Research

Scripture research is a specialized research category.

When researching biblical passages, consider:

passage context
book context
genre
historical setting
original-language considerations when relevant
major interpretive traditions
reputable commentaries
cross references

Scripture itself should remain distinct from commentary about Scripture.

The research agent must not treat a commentary as equivalent to the biblical text.

22. Theological Research

Theological research should identify the perspective of the source.

Record, when relevant:

author
tradition
denomination
theological framework
publication
date

A theological source should not be represented as neutral if its theological tradition materially affects its interpretation.

23. Contradictory Evidence

The agent must actively look for credible evidence that challenges a potentially important claim.

This is especially important when:

the claim is controversial
the claim is politically charged
the claim is central to the sermon
the evidence is surprisingly strong
the claim confirms an obvious assumption

The purpose is not to manufacture false balance.

The purpose is to avoid confirmation bias.

24. Negative Evidence

Absence of evidence must not automatically be interpreted as evidence of absence.

The agent should distinguish:

"No evidence was found."

from:

"There is evidence that this did not occur."

These are materially different claims.

25. Search Result vs Evidence

A search result is not evidence merely because it appears in search results.

The agent must inspect the underlying source whenever possible.

Search snippets should not be treated as authoritative representations of the source.

26. Source Traceability

Every externally sourced claim used in the sermon must be traceable.

The chain should be:

SERMON CLAIM
→ EVIDENCE CLAIM
→ SOURCE
→ SOURCE LOCATION

A reviewer should be able to determine why a factual claim appears in the sermon.

27. Evidence Selection

The sermon architect should prefer evidence based on:

relevance
reliability
directness
recency when applicable
clarity
usefulness to the sermon

More evidence is not necessarily better.

The goal is the smallest body of strong evidence necessary to support the sermon.

28. Evidence Must Not Dictate Theology

Research may inform a sermon.

Research must not automatically determine theological conclusions.

For example:

A sociological study may demonstrate that loneliness is increasing.

It does not, by itself, establish what Scripture teaches about loneliness.

The research layer provides evidence.

The theological layer interprets that evidence within the configured theological framework.

29. Evidence Must Not Dictate Application

Research may identify a problem or trend.

It does not automatically determine the appropriate Christian response.

The sermon architect must connect:

EVIDENCE
→ SCRIPTURE
→ THEOLOGICAL UNDERSTANDING
→ PASTORAL APPLICATION

rather than:

EVIDENCE
→ AUTOMATIC MORAL CONCLUSION

30. Research Efficiency

The agent should stop researching when it has sufficient high-quality evidence to construct the sermon confidently.

Do not continue gathering sources merely to increase the source count.

Research depth should be proportional to:

sermon complexity
claim importance
controversy
recency
potential consequences of being wrong
31. Research Failure

If adequate evidence cannot be found, the agent should not manufacture an answer.

It should:

reduce the claim
qualify the claim
remove the claim
identify the uncertainty
request human direction when necessary

A weaker truthful sermon is preferable to a stronger sermon built on fabricated evidence.

32. Research Audit

Before evidence enters the approved Evidence Pool, evaluate:

Source Quality

Is the source credible?

Relevance

Does it actually relate to the sermon question?

Accuracy

Does the source support the extracted claim?

Recency

Is the information current enough for its intended use?

Corroboration

Has the claim been independently supported when appropriate?

Context

Could omitted context materially change the meaning?

Attribution

Can the claim be traced to the source?

Uncertainty

Has uncertainty been preserved?

Bias

Could source bias materially affect interpretation?

33. Final Research Standard

The research layer succeeds when the sermon architect can answer:

"How do we know this?"

for every meaningful external factual claim.

The answer must be traceable to evidence.

If the answer is:

"The AI thought it was probably true."

the evidence has failed.


I think this is the right level of rigor for what we're building. **Notice that I intentionally did not make this a generic web-search instruction.** It's defining the *epistemology of the product*—how the system knows something, how confident it should be, and what is allowed to cross the boundary from research into the sermon.

So our stack is now:

```text
constitution.md
    ↓
theology.md
    ↓
theological-profile.yaml
    ↓
research_policy.md
    ↓
Evidence Pool
    ↓
Sermon Architecture
    ↓
Sermon
    ↓
Audit
    ↓
Production Package