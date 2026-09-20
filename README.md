# Personalization & Discovery

**Profile Formation · Evolving Intent · Recommendations · ML & AI Product Decisions**

Personalization isn't a static profile or a list of things someone likes. It's an ongoing product decision about what evidence means, what the system can reasonably infer from it, and how those inferences should change the experience.

This study follows the same user from cold start through an established personalized experience, then asks where deterministic product logic stops being enough and where ML or AI actually adds value.

The system uses three layers throughout:

**Observed → Inferred → Decided**

**Observed:** What the user actually told us or did.  
**Inferred:** What the system currently believes that evidence may mean.  
**Decided:** How those beliefs affect what the product shows next.

The distinction matters because **evidence is fact; inference is a hypothesis; recommendation is a decision.**

---

## 01 / Profile formation

### How do you personalize before you know someone?

A new user creates a cold-start problem: personalization has no behavioral history to learn from.

One solution is to ask the user everything.

That creates a different problem: cognitive burden.

The product needs enough explicit information to improve the starting experience without asking someone to build a detailed profile before they've received any value.

### Starting with less

The fictional experience begins with one lightweight question:

> **Pick a few things you'd like more of.**

The user chooses:

**Metalcore · Astronomy · Women in tech**

Those selections provide useful starting evidence.

They do **not** establish a permanent identity.

At this point, the product still doesn't know preferred creators, formats, adjacent interests, dislikes, current intent, or how durable any of these preferences will be.

### Early behavior adds evidence

The initial experience deliberately mixes known interests with adjacent discovery and limited exploration.

| Experience | Action | What we know |
| --- | --- | --- |
| Metalcore artist | Follow | Strong positive creator signal |
| Astronomy podcast | Save | Strong positive content/topic signal |
| Women-in-tech creator | Repeated engagement | Positive behavioral evidence accumulating |
| Metalcore-adjacent artist | Save | Possible adjacent affinity |
| Generic tech creator | Skip | Weak contextual signal |
| Unfamiliar creator | Dismiss | Weak or ambiguous negative evidence |

Not every interaction means the same thing.

A **follow** is different from passive viewing.

A **save** is different from a click.

A **skip** may mean "not now," not "I dislike this."

A **dismissal** may carry more or less meaning depending on the interaction.

Explicit **Not Interested** feedback is stronger because the user deliberately communicated a preference.

### The product decision

**Ask only for what materially improves the starting experience, then learn from behavior.**

The initial profile is a hypothesis.

Early behavior should increase, reduce, or refine confidence without allowing a handful of interactions to permanently define the user.

### What I'd measure

- **Time to useful personalization** — how quickly does the experience become meaningfully relevant?
- **Onboarding completion** — how much explicit input can we request before the burden outweighs the benefit?
- **Early positive signals** — are users finding content worth following, saving, or meaningfully engaging with?
- **Early negative feedback** — how often does the initial experience produce explicit rejection?
- **Exploration success** — does content outside the initial selections create new positive signals?

The goal isn't to construct a perfect profile during onboarding.

It's to create a useful starting point that can keep learning.

---

## 02 / Profile evolution

### How should personalization change without losing the person?

Over time, the product has substantially more evidence.

For this fictional user, consistent behavior has established durable affinities around:

**Metalcore · Astronomy · Women in tech**

But people don't stay fixed.

New interests emerge. Existing interests become more specific. Current intent changes. Negative feedback adds boundaries.

The personalization system needs to adapt without allowing the newest behavior to overwrite everything it already knows.

### New evidence

The user begins:

- searching for strength-training content
- engaging with practical strength content
- engaging increasingly with women-founder content
- continuing to discover and save new metalcore and metalcore-adjacent artists

Negative evidence also appears:

- **Country music:** explicit Not Interested
- **Male strength creators:** repeated negative feedback
- **Wellness framing:** repeated dismissals

These signals should not produce the same inference.

### Evidence ≠ inference

A search for strength training provides strong evidence of **current intent**.

It does not establish that fitness should replace the user's durable interests.

Repeated engagement with women-founder content may indicate that the broader women-in-tech affinity is becoming more specific.

Repeated dismissal of wellness-framed content may gradually provide evidence about an unwanted **framing**, without implying that strength training itself is unwanted.

Negative feedback about particular strength creators should not automatically generalize to an entire topic.

The system needs to distinguish:

**Topic affinity · Creator affinity · Framing preference · Current intent · Durable affinity**

### The product decision

**A personalized profile should be a continuously updated hypothesis, not a permanent label.**

That means avoiding several tempting conclusions:

**Strength training → fitness → wellness**  
Not necessarily.

**Negative feedback on a strength creator → dislikes strength training**  
Not necessarily.

**Recent fitness searches → replace established interests with fitness**  
No.

**Already likes metalcore → no need for more metalcore discovery**  
Also no.

Discovery doesn't require abandoning known interests. A new metalcore or metalcore-adjacent artist is still discovery.

### From individual ranking to experience composition

A recommendation system might reasonably determine that several strength-training candidates are highly relevant during a fitness-heavy session.

But ten individually plausible fitness recommendations can collectively create a poor personalized experience.

The product therefore needs to think about the **composition of the experience**, not only the relevance of each item.

A useful mix might include:

- durable affinities
- current intent
- refining interests
- adjacent discovery
- limited exploration

The newest signal shouldn't automatically consume the entire experience.

### Signal strength and scope

Not all negative actions are equivalent.

| Signal | Product interpretation |
| --- | --- |
| Not Interested | Strong explicit negative signal |
| Block / Don't recommend creator | Very strong explicit signal with narrow scope |
| Dismiss | Weak or ambiguous negative signal depending on context |
| Skip | Weak contextual signal, often "not now" |
| Repeated dismissals or skips | Accumulating behavioral evidence |

The system should generalize only as far as the evidence supports.

One disliked creator should not become a demographic preference.

One skipped topic should not become a permanent exclusion.

### What I'd measure

- **Recommendation satisfaction signals** — follows, saves, meaningful consumption, explicit negative feedback
- **Discovery success** — do previously unknown creators or interests produce durable positive behavior?
- **Interest concentration** — is one recent topic beginning to dominate the experience?
- **Negative-feedback rate** — where is personalization repeatedly getting the user wrong?
- **Durable affinity formation** — do emerging interests persist after the immediate context disappears?
- **Return behavior** — does the personalized experience continue to create value over time?

The goal isn't maximum short-term engagement with whichever topic is currently hottest.

It's an experience that can change with the user without continually redefining them.

---

## 03 / ML & AI product decisions

### When a better model doesn't mean a better product

Suppose a creator-discovery ranking model improves on its primary offline relevance metric.

After launch:

- overall feed engagement increases 9%
- average session length increases 12%
- follows of previously unknown creators decrease 18%
- users increasingly consume creators they've already engaged with
- retention and explicit negative feedback remain roughly unchanged

The model may be getting better at what it was asked to predict.

That doesn't mean the product is getting better at everything the experience is supposed to do.

In this case, historical engagement is highly predictive of future engagement. Optimizing relevance can therefore reinforce known preferences while reducing opportunities for discovery.

The product question becomes:

> **Can we preserve relevance while increasing successful discovery?**

### Define the outcome before changing the model

The PM doesn't need to prescribe how the ML team should change the ranking system.

The PM does need to define what successful discovery means.

For this experiment:

**Primary**

- **Repeat engagement with a newly discovered creator within 14 days** — discovery is more meaningful when the user returns to the creator rather than consuming one item once.

**Supporting**

- Meaningful consumption of previously unknown creators
- Follows of previously unknown creators
- Session length

**Guardrails**

- Overall engagement
- Explicit negative-feedback rate

**Longer-term outcome**

- 30-day retention

The ML team can then evaluate approaches such as changes to candidate generation, ranking, or exploration strategy against a product outcome rather than optimizing diversity for its own sake.

### Interpreting the tradeoff

Suppose the experiment produces:

| Metric | Control | Treatment |
| --- | ---: | ---: |
| Repeat engagement with newly discovered creators | 12% | 17% |
| Meaningful consumption of unknown creators | Baseline | +22% |
| Follows of unknown creators | Baseline | +15% |
| Overall engagement | Baseline | -3% |
| Negative feedback | Baseline | +1 pp |
| 30-day retention | 41% | 42% |

The primary outcome improved substantially.

But relevance-related guardrails weakened.

That doesn't automatically mean the treatment failed. Some reduction in immediate engagement may be an acceptable tradeoff when the product deliberately creates more room for unfamiliar content.

Before a broad rollout, I'd want to understand **where the tradeoff occurred**.

Did most established users give up a small amount of immediate engagement in exchange for better discovery?

Or did particular cohorts experience a much larger relevance decline?

The next question becomes whether the system can preserve the improvement in durable creator discovery while recovering some of the relevance loss.

The PM's job isn't to choose the model architecture.

It's to make the tradeoff explicit, define what success means, and determine whether model improvements are producing a better product outcome.

### What changes for the PM

Working with a probabilistic system changes the questions product needs to answer.

**Prediction target**  
What are we actually asking the model to predict?

A click? A save? A follow? Completion? Long-term satisfaction?

**Signals**  
Which behaviors should inform the prediction, and what ambiguity do they carry?

**Ground truth**  
What outcome tells us the recommendation was actually good?

**Offline evaluation**  
Does the model perform better against historical or held-out data?

**Online evaluation**  
Does that improvement translate into a better live product experience?

**Feedback loops**  
Are recommendations creating the behavior that later convinces the system to recommend even more of the same thing?

**Exploration**  
How can the system learn about interests it hasn't given the user an opportunity to demonstrate yet?

**Cold start**  
What happens when the user or content item has little behavioral history?

**Guardrails**  
What should optimization never be allowed to overwhelm?

The PM doesn't need to implement the model to own these product decisions.

But the PM does need to understand what the model is optimizing, what evidence it learns from, and how model behavior affects the user experience.

### Choose the right mechanism

Some outcomes should remain predictable because the user's intent or the product constraint is already known. Other problems benefit from learned systems.

| Problem | Approach | Why |
| --- | --- | --- |
| User blocks a creator | Deterministic | Explicit user control should be honored predictably |
| Rank a very large set of plausible creators and content | ML | Learning relevance across large numbers of users, items, behaviors, and contexts is impractical to encode manually |
| Interpret "women talking about starting companies after leaving tech" | Semantic AI | The intent spans concepts that may not map cleanly to one predefined taxonomy label |
| Balance current strength-training intent with durable affinities | ML + product policy | Prediction can estimate relevance while product strategy shapes the overall experience |

Deterministic rules and learned systems don't have to compete.

They solve different problems.

### Where ML becomes useful

Machine learning becomes valuable when the product needs to learn patterns across more users, content, contexts, and behaviors than a team could reasonably encode as rules.

Examples include:

- retrieving plausible candidates from a very large catalog
- predicting relative relevance
- learning affinity patterns from behavioral history
- identifying similarities from large-scale interaction data
- adapting predictions to context and changing behavior

A ranking model might estimate:

> **Given what we know about this user, this content, and this context, which candidates are most likely to be relevant now?**

That prediction is useful.

It still isn't the entire product decision.

### ML + product policy

Suppose recent behavior causes strength-training content to receive very high predicted relevance.

The model may be working correctly at the item level.

The resulting experience can still be wrong if strength content overwhelms every durable interest.

Product policy and composition can therefore work alongside ML ranking.

**Candidate generation → ML ranking → Product policy / composition → Experience**

---

## Where AI adds value

Machine-learning ranking and generative or semantic AI solve different problems.

AI becomes useful here when the product needs richer understanding of **unstructured content or intent**, not simply because the product already uses personalization.

### Item cold start

A new podcast may have little or no behavioral history.

Its title, description, transcript, creator information, or other content can still provide semantic information about what it discusses.

Semantic representations can help the system understand the new item before enough interaction data exists.

### Natural-language intent

A user might search:

> **women talking about starting companies after leaving tech**

That intent doesn't necessarily map cleanly to one predefined taxonomy label.

A semantic model can help connect the request to concepts such as:

**women in tech · founders · entrepreneurship · career transition**

### Content similarity

Two creators can discuss related ideas without using identical categories or vocabulary.

Semantic representations can help identify those relationships where manually maintained tags or keyword matching are insufficient.

### The product decision

**Add AI when understanding unstructured content or intent materially improves a problem that rules or conventional ranking signals cannot solve well enough.**

Don't add AI merely because the product contains recommendations.

---

## Try the Personalization Lab

→ [Launch the interactive study](https://rtfenter.github.io/Personalization-Discovery-Lab/)

The lab follows one user through all three chapters:

**01 / Profile Formation**  
Start with minimal explicit input and watch early behavior turn a cold-start profile into a richer hypothesis.

**02 / Profile Evolution**  
Introduce current intent, refining interests, negative feedback, and continued discovery while preserving durable affinities.

**03 / ML & AI Product Decisions**  
Decide when deterministic logic, ML prediction, semantic AI, or a combination is appropriate, then work through an ML experiment where improved relevance conflicts with creator discovery.

Throughout the experience, the same three layers remain visible:

**Observed** — what the user actually told us or did.

**Inferred** — what the system currently believes the evidence may mean.

**Decided** — how that belief changes what the product shows.

The prototype uses deterministic simulation to make the product decisions visible. It does not reproduce a production ML ranking system.

---

## What this study is testing

Across all three cases, the core hypothesis is:

> **A useful personalization system should learn continuously without treating its current understanding of a person as permanent truth.**

The system should ask for as little explicit effort as necessary, distinguish evidence from inference, preserve uncertainty where uncertainty exists, adapt to changing intent, continue creating room for discovery, and use increasingly complex technology only when the product problem justifies it.

---

*This is an independent product study designed to build and demonstrate personalization, ML-product, and AI-product fluency. The product, users, creators, content, recommendation behavior, and implementation details are fictionalized or illustrative.*
