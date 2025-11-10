# BrainLift Style Guide

> **Purpose:** This style guide documents conventions and best practices for creating and maintaining BrainLift knowledge bases across projects. Following these conventions ensures consistency, scalability, and reusability of the BrainLift methodology.

---

## Table of Contents

- [BrainLift Document Structure Overview](#brainlift-document-structure-overview)
- [Owner(s) and Purpose](#owners-and-purpose)
- [DOK4 - Spiky Points of View Guidelines](#dok4---spiky-points-of-view-guidelines)
- [DOK3 Guidelines](#dok3-guidelines)
- [Experts Section](#experts-section)
- [DOK2 - Knowledge Tree Structure](#dok2---knowledge-tree-structure)
- [DOK Display Format Convention](#dok-display-format-convention)
- [Markdown Formatting Conventions](#markdown-formatting-conventions)
- [BrainLift Document Structure (Sources & Categories)](#brainlift-document-structure-sources--categories)
- [DOK1 Writing Guidelines](#dok1-writing-guidelines)
- [DOK2 Writing Guidelines](#dok2-writing-guidelines)

---

## BrainLift Document Structure Overview

### The Inverted Pyramid Principle

BrainLift documents follow an **inverted pyramid structure**: the most synthesized, valuable insights appear first, with supporting details progressively deeper. This enables readers to quickly grasp key insights without reading the entire document.

**Document Flow:**
```
1. Owner(s) - Who created/maintains this BrainLift
2. Purpose - In Scope / Out of Scope boundaries
3. DOK4 - Spiky Points of View (3-5 controversial but defensible claims)
4. DOK3 - Insights (8-12 synthesized patterns) & Blueprints (operational guides)
5. Experts - Key authorities on this topic (4-8 profiles)
6. DOK2 - Knowledge Tree
   └── Categories (thematic groupings)
       ├── Section Summary (synthesis of all sources in category)
       ├── Optional: Sub-sections (for 10+ source categories)
       │   ├── Section Summary (synthesis of sub-section sources)
       │   └── Sources
       └── Sources
           ├── DOK2 Summary (source-level synthesis)
           ├── DOK1 Facts (atomic knowledge units)
           ├── Insights (optional source-level synthesis)
           └── Link: [URL]
```

### Why Inverted Pyramid?

**Cognitive Load Management**: Working memory handles 3-7 items simultaneously. Starting with synthesis allows readers to build mental scaffolding before encountering details.

**Progressive Disclosure**: Readers choose their depth. Executives may read only DOK4. Practitioners read through DOK3. Researchers dive to DOK1.

**Value-First Design**: Most important insights (DOK4, DOK3) represent weeks of synthesis. They should be immediately visible, not buried after 50 DOK1 facts.

### Progression vs. Presentation Order

**Progression Order** (how knowledge develops):
- DOK1 → DOK2 → DOK3 → DOK4 (extract facts, summarize sources, synthesize across sources, form SPOVs)

**Presentation Order** (how document is structured):
- DOK4 → DOK3 → DOK2 → DOK1 (show conclusions first, then supporting evidence)

You **build knowledge bottom-up** but **present it top-down**.

---

## Owner(s) and Purpose

### Owner(s) Section

**Purpose**: Document who created and maintains this BrainLift for accountability and contact.

**Format**:
```markdown
- **==Owner(s)==**
  - [Name 1]
  - [Name 2] (if multiple owners)
```

**Guidelines**:
- List primary creator(s) who can answer questions about the BrainLift
- Update when ownership transfers
- Multiple owners acceptable for collaborative BrainLifts
- Keep it simple - just names, no bios here (bios go in Experts if relevant)

**Example**:
```markdown
- **==Owner(s)==**
  - Sarah Chen
  - Marcus Rodriguez
```

### Purpose Section

**Purpose**: Define clear boundaries for what this BrainLift covers and explicitly excludes.

**Format**:
```markdown
- **==Purpose==**
  - **In Scope:** [Concise description of what this BrainLift covers]
  - **Out of Scope:** [Explicit list of related topics NOT covered]
```

**Guidelines for In Scope**:
- One sentence describing the core focus
- Be specific about the audience or use case
- Explain the value: what can readers do with this knowledge?
- Mention the specific domain or context

**Guidelines for Out of Scope**:
- List 3-5 related topics that might be confused with your focus
- Helps readers immediately know if this is the right BrainLift
- Prevents scope creep during development
- Creates clear boundaries for source selection

**Example (from S-Class BrainLift)**:
```markdown
- **==Purpose==**
  - **In Scope:** Creating clear, actionable, learning-science-backed documentation specifically for BrainLift and BrainMaxxing concepts that reduces confusion, accelerates adoption, and enables both beginners and advanced users to build effective knowledge structures.
  - **Out of Scope:** General technical writing best practices, API documentation, marketing copy, academic papers on knowledge management, or documentation for other non-BrainLift tools and platforms.
```

**Why Explicit Boundaries Matter**:
- Prevents adding irrelevant sources during research
- Helps readers quickly assess if this BrainLift answers their questions
- Creates productive constraints that force focus
- Makes gaps visible (what needs a separate BrainLift)

---

## DOK4 - Spiky Points of View Guidelines

### Purpose

DOK4 represents the highest level of synthesis: **controversial but defensible positions** that emerge from deep engagement with sources. SPOVs are thesis statements you're willing to advocate for, knowing others can disagree.

### What Makes a Good SPOV?

**From Wes Kao's framework (see S-Class example):**

1. **Defensible but Not Universal**: Rooted in evidence but not proven facts. You can make a strong argument, but reasonable people can disagree.

2. **Teaches Something Unexpected**: Your audience learns something relevant they don't already know. Challenges conventional wisdom or common practice.

3. **Requires Bravery**: You must be okay with people disagreeing. If 100% of readers agree, it's too safe.

4. **Unique to You**: Emerges from your experience synthesizing these specific sources. Nearly impossible for someone else to imitate.

5. **Actionable Implication**: SPOVs should change how readers think or act. Not just interesting observations.

### SPOV Structure

**Format**:
```markdown
- **==DOK4 - Spiky Points of View==**
  - **[SPOV Title in Bold]** [2-4 sentences elaborating the position]. [Supporting evidence or rationale]. [Implication or call to action].
  - **[Second SPOV Title]** [Elaboration]. [Evidence]. [Implication].
  - **[Third SPOV Title]** [Elaboration]. [Evidence]. [Implication].
```

**Guidelines**:
- **Count**: 3-5 SPOVs per BrainLift (fewer is better than diluted)
- **Length**: 2-4 sentences each (50-100 words)
- **Tone**: Confident but not arrogant. Advocate, don't preach.
- **Title**: Make it provocative. Should make readers pause.
- **Placement**: At the TOP of the document, after Purpose

### Examples from S-Class BrainLift

**Example 1**:
> **The best BrainLift documentation is embarrassingly incomplete.** Most documentation fails by trying to be comprehensive, but S-Class BrainLift articles should cover only 20% of possible content - the 20% that enables 80% of value creation. Just as Progressive Summarisation shows only 5% of sources reach final form, and cognitive load theory proves we can only handle 3-7 items at once, BrainLift documentation should aggressively exclude rather than include. If you're not slightly embarrassed by what you left out, you included too much.

**What makes this work**:
- ✅ Controversial: "embarrassingly incomplete" contradicts documentation norms
- ✅ Defensible: Cites 3 supporting frameworks (Progressive Summarisation, CLT, 80/20)
- ✅ Actionable: "aggressively exclude rather than include"
- ✅ Testable claim: "If you're not slightly embarrassed..."

**Example 2**:
> **Confusion is a feature, not a bug.** Traditional documentation aims to eliminate all confusion, but S-Class BrainLift articles should create productive confusion at DOK boundaries. When readers hit the bright lines between DOK2 summaries and DOK3 insights, or between DOK3 insights and DOK4 SPOVs, they should feel the cognitive friction of levelling up. This confusion signals the transition from consuming to creating knowledge. Documentation that never confuses never transforms.

**What makes this work**:
- ✅ Controversial: Deliberately creating confusion opposes standard practice
- ✅ Defensible: Explains mechanism (cognitive friction = learning)
- ✅ Memorable: "never confuses never transforms"

### When to Develop DOK4s

**Timing**: Wait until you have 5+ sources and well-developed DOK3 insights. SPOVs emerge from deep synthesis, not early exploration.

**Signals you're ready**:
- You've identified surprising patterns across multiple sources
- You have strong opinions that contradict common practice
- You can defend positions with evidence from 3+ sources
- You feel slightly nervous about publishing your conclusions

**If you're not ready**: Skip DOK4 section entirely. Better to have no SPOVs than weak ones.

### Quality Checklist for DOK4

Before publishing SPOVs, verify:

- [ ] Each SPOV is controversial enough that smart people could disagree
- [ ] You can defend each position with evidence from multiple sources
- [ ] Each SPOV teaches readers something they likely don't know
- [ ] You're genuinely willing to advocate for these positions publicly
- [ ] SPOVs have actionable implications, not just observations
- [ ] Titles are provocative but not clickbait
- [ ] 3-5 SPOVs total (quality over quantity)
- [ ] Each connects back to DOK3 insights or DOK1 facts

---

## DOK3 Guidelines

### Overview

DOK3 represents the cross-source synthesis layer of BrainLift, containing two complementary components:

1. **DOK3 - Insights**: Contrarian, surprising patterns that emerge from analyzing multiple sources together
2. **DOK3 - Blueprints**: Operational guides that translate insights into executable actions for teams and agents

Together, these components bridge the gap between knowledge synthesis (DOK1-DOK3 Insights) and practical implementation (frameworks, processes, agent instructions).

---

### DOK3 - Insights

#### Purpose

DOK3 Insights represent **cross-source synthesis**: patterns, tensions, and principles that emerge when you analyze multiple sources together. Unlike DOK2 (single-source summaries), DOK3 insights require reading across sources to discover.

#### What Makes a Good DOK3 Insight?

1. **Requires Multiple Sources**: Can't be derived from a single source. Emerges from comparison, contrast, or synthesis.

2. **Reveals Patterns**: Shows connections readers wouldn't see from individual sources alone.

3. **Actionable**: Provides strategic or tactical guidance, not just observations.

4. **Bridges Domains**: Often connects ideas from different fields or contexts.

#### DOK3 Insight Structure

**Format**:
```markdown
- **==DOK3 - Insights==**
  - **[Insight Title]** - [1-2 sentence statement of the insight]
  - **[Second Insight Title]** - [Statement]
  - **[Third Insight Title]** - [Statement]
  [... 8-12 total insights]
```

**Guidelines**:
- **Count**: 8-12 insights (enough to show patterns, not so many it's overwhelming)
- **Length**: 1-2 sentences per insight (20-50 words)
- **Tone**: Declarative. State the insight clearly.
- **Title**: Descriptive, action-oriented when possible
- **Placement**: After DOK4 (if present), before DOK2 Knowledge Tree

### Examples from S-Class BrainLift

**Example - Pattern Recognition**:
> **Documentation succeeds through productive incompleteness** - Whether it's SPOVs inviting disagreement, Diátaxis separating concerns, or Progressive Summarisation leaving 95% at shallow layers, the best documentation explicitly designs for selective consumption rather than comprehensive coverage.

**Why this works**:
- ✅ Cites 3 sources (SPOVs, Diátaxis, Progressive Summarisation)
- ✅ Reveals pattern: incompleteness is a design principle, not a failure
- ✅ Counterintuitive: contradicts "comprehensive documentation" ideal

**Example - Cause and Effect**:
> **Cognitive constraints drive quality** - The 2500-token BrainLift limit, working memory's 3-7 item capacity, and Progressive Summarisation's aggressive reduction all show that arbitrary limitations force the distillation that creates value. Documentation improves by subtracting, not adding.

**Why this works**:
- ✅ Connects multiple constraints from different sources
- ✅ Reveals mechanism: limits force quality
- ✅ Actionable: "subtracting, not adding"

#### Synthesis Techniques for DOK3 Insights

##### 1. Pattern Recognition
Look for themes that appear across 3+ sources.

**Template**: "[Pattern] appears in [Source A], [Source B], and [Source C], suggesting [insight]"

##### 2. Contrast and Tension
Find where sources disagree or present trade-offs.

**Template**: "While [Source A] emphasizes [X], [Source B] shows [opposite], revealing [tension/trade-off]"

##### 3. Cause and Effect Chains
Connect mechanisms from multiple sources.

**Template**: "[Source A's finding] explains why [Source B's observation] occurs, leading to [implication]"

##### 4. Domain Bridging
Apply principles from one field to another.

**Template**: "[Principle from Field A] applies to [Context from Field B], suggesting [novel application]"

##### 5. Expertise Progression
Show how understanding evolves from novice to expert.

**Template**: "Novices focus on [X per Source A], but experts recognize [Y per Source B], explaining [expertise difference]"

#### When to Develop DOK3 Insights

**Timing**: After you have 4+ sources with DOK2 summaries complete. Don't try to synthesize too early.

**Process**:
1. Read all DOK2 summaries in sequence
2. Note patterns, contrasts, and connections
3. Draft 15-20 potential insights
4. Refine to strongest 8-12
5. Order from most to least important

**If you're not ready**: Wait. DOK3 insights require enough sources to show patterns. With only 2-3 sources, synthesis is premature.

#### Quality Checklist for DOK3 Insights

Before finalizing insights, verify:

- [ ] Each insight draws from 2+ sources (cite DOK1 or DOK2 references)
- [ ] Insights couldn't be derived from a single source alone
- [ ] 8-12 total insights (not fewer, not many more)
- [ ] Each insight is 1-2 sentences (20-50 words)
- [ ] Insights are ordered by importance/impact
- [ ] Together, insights form a coherent narrative
- [ ] Insights connect to DOK4 SPOVs (if present)
- [ ] Each insight is actionable or reveals important patterns

---

### DOK3 - Blueprints

#### Purpose

DOK3 Blueprints operationalize insights by providing structured, plain-language directives that enable teams, collaborators, or AI agents to execute processes consistently. Unlike insights (which reveal "what" patterns exist), blueprints specify "how" to act on those patterns in specific contexts.

Blueprints bridge the gap between strategic understanding and tactical execution. They transform contrarian insights into repeatable processes that others can follow.

#### What Makes a Good Blueprint?

1. **Operationalizes Insights**: Translates DOK3 insights or DOK1/DOK2 knowledge into executable actions. The blueprint should make an insight actionable.

2. **Structured Directives**: Includes clear components—domain context, specific actions, decision boundaries, tools/systems, and quality criteria. Someone reading the blueprint should know exactly what to do.

3. **Plain Language**: Written at Grade 12 reading level with concrete, unambiguous instructions. Avoids jargon unless necessary, defines technical terms when used.

4. **Judgment Boundaries**: Explicitly states where human judgment is required ("season to taste") versus where rules must be followed ("reaches 150° internal temperature").

5. **Definition of Done**: Provides clear quality criteria or completion markers so executors know when the process is finished and whether it was done correctly.

#### Blueprint Structure

**Format**:
```markdown
- **==DOK3 - Blueprints==**
  - **[Blueprint Name]** - [1-2 sentence overview of what this blueprint accomplishes]
    - **Domain Context**: [Key concepts, terms, or materials this blueprint operates on]
    - **Actions**: [Step-by-step process or decision framework]
    - **Tools/Systems**: [Required tools, platforms, or MCPs to use]
    - **Judgment Boundaries**: [Where judgment is required vs. where rules must be followed]
    - **QC/Definition of Done**: [How to know the process is complete and successful]
    - **Detailed Spec**: [Optional link to external document with full implementation details]
  - **[Second Blueprint Name]** - [Overview]
    - [Components as above]
```

**Guidelines**:
- **Count**: Variable based on BrainLift scope (typically 1-8 blueprints)
- **Overview Length**: 1-2 sentences (20-40 words)
- **Component Detail**: High-level with key decision points; link to detailed specs for full implementation
- **Tone**: Directive and clear. Use imperative voice ("Tag documents...", "Escalate when...").
- **Placement**: After DOK3 - Insights, before Experts section

#### Examples

##### Example 1: Recipe/Playbook Blueprint (from image)

**[Cooking Blueprint Name]** - Follow this process to prepare [dish name] with consistent results.

- **Domain Context**: Fresh ingredients including [list], cooking equipment (pan, oven), target internal temperature of 150°
- **Actions**:
  1. Preheat oven to [temperature]
  2. Season ingredients with pinch of salt, adjust to taste
  3. Sear in pan until golden brown
  4. Transfer to oven, cook until internal temperature reaches 150°
  5. Stir occasionally until mixture becomes jammy
- **Tools/Systems**: Pan, oven, meat thermometer
- **Judgment Boundaries**:
  - **Use judgment**: Seasoning amount ("pinch of salt, season to taste"), stirring frequency ("until jammy")
  - **Follow rules**: Internal temperature must reach 150° (food safety), oven temperature (recipe accuracy)
- **QC/Definition of Done**: Reaches 150° internal temperature, turns bright red, firm to the touch
- **Detailed Spec**: [Link to full recipe with timing, ingredient quantities, troubleshooting]

##### Example 2: UK Redundancy Process Blueprint

**[UK Redundancy Process]** - Execute redundancies in UK operations while complying with Collective Consultation requirements.

- **Domain Context**: UK employment law, Collective Consultation threshold (20+ redundancies in 90 days triggers 30-day Collective Consultation), proposed redundancy population, union notification requirements
- **Actions**:
  1. Calculate total redundancies planned across all UK locations in next 90 days
  2. If 20-38, split into separate actions at least 90 days apart to avoid Collective Consultation
  3. If <20 per action, proceed with individual consultations only
  4. If >38, plan for collective consultation.
  5. Document business rationale and selection criteria
  6. Start 1-on-1 redundancy consultation process with affected employees
- **Tools/Systems**: HRIS for headcount tracking, legal counsel for compliance review, consultation documentation templates
- **Judgment Boundaries**:
  - **Use judgment**: Selection criteria specifics, consultation messaging, severance negotiations
  - **Follow rules**: 90-day separation between actions if avoiding Collective Consultation, 30-day consultation period if triggered, statutory redundancy pay calculations
- **QC/Definition of Done**: All redundancies executed without triggering Collective Consultation (if intended), no employment tribunal claims filed, all affected employees notified per timeline
- **Detailed Spec**: [Link to full HR policy with timelines, templates, escalation procedures]

##### Example 3: Litigation Document Review - Relevance Tagging Blueprint

**[Relevance Tag Application]** - Apply consistent relevance determinations using structured rubric, not ad-hoc judgment.

- **Domain Context**: Document population post-processing, Federal Rule 26(b)(1) standard ("relevant to any party's claim or defense and proportional"), categorical tags (Issue, Custodian, Time Period, Document Type)
- **Actions**:
  1. Review document against each claim and defense in Case Summary
  2. Tag as "Relevant" if document mentions key players, events, or timeframes in scope
  3. Apply categorical tags for all relevant documents (minimum: Issue + Custodian)
  4. Flag as "Hot" if document could change case strategy or contradicts witness statements
  5. Tag as "Not Relevant" only if clearly outside scope (wrong time period, unrelated business unit, etc.)
- **Tools/Systems**: Review platform (Relativity/Everlaw/DISCO), Case Summary document, categorical tag taxonomy, hot document escalation form
- **Judgment Boundaries**:
  - **Use judgment**: Assessing potential strategic impact (hot document determination), weighing proportionality for marginal documents
  - **Follow rules**: Federal Rule 26(b)(1) standard, categorical tags required for all relevant docs, no quotes in hot document reports (identifier + brief explanation only)
- **QC/Definition of Done**: All documents have relevance determination, relevant documents have minimum categorical tags, hot documents escalated within 2 hours, <5% over-tagging rate on QC sampling
- **Detailed Spec**: [Link to full tagging guide with claim/defense details, categorical taxonomy, hot document examples]

#### Blueprint Types

Blueprints can take several forms depending on the domain:

1. **Sequential Procedures**: Step-by-step processes with clear order (like UK redundancy example, cooking recipe)
2. **Decision Rubrics**: Frameworks for making consistent judgments (like relevance tagging)
3. **Escalation Protocols**: When and how to involve supervisors or experts (embedded in hot document blueprint)
4. **Quality Frameworks**: Standards for evaluating outputs (can be part of QC/Definition of Done)
5. **Agent Instructions**: Detailed specifications for AI agents with tool invocations, MCP integrations, and success criteria

All types share the same core components: domain context, actions, tools, judgment boundaries, and QC criteria.

#### When to Create Blueprints

**Timing**: After DOK3 insights are developed and you've identified patterns that need operationalization. Blueprints make insights actionable.

**Signals you're ready**:
- You have DOK3 insights that suggest "how" to do something differently
- You've identified processes where consistency matters across team members
- You're planning to share knowledge with others who will execute (not just understand)
- You're designing workflows for AI agents that need structured instructions

**If you're not ready**: Focus on DOK3 insights first. Blueprints operationalize insights—you need insights to operationalize.

#### Blueprints vs. External Frameworks

**Relationship**: Blueprints in the BrainLift methodology file provide high-level overviews with key decision points. Full implementations may live in the `/frameworks/` directory.

**When to keep in BrainLift**:
- Blueprint is 1-2 paragraphs or less
- Blueprint is primarily for understanding, not daily execution
- Blueprint illustrates how insights translate to action

**When to link to external**:
- Blueprint requires multiple pages of detail
- Blueprint includes extensive examples, templates, or edge cases
- Blueprint will be updated frequently as processes evolve
- Blueprint is actively used by team members or agents

**Example structure**:
```markdown
- **[Hot Document Identification]** - Systematically identify case-determinative documents...
  - **Domain Context**: ...
  - **Actions**: ...
  - **Detailed Spec**: See `/frameworks/hot-document-identification.md` for full rubric
```

#### Quality Checklist for DOK3 Blueprints

Before finalizing blueprints, verify:

- [ ] Each blueprint operationalizes a DOK3 insight or addresses a DOK1/DOK2 pattern
- [ ] All five core components present: Domain Context, Actions, Tools/Systems, Judgment Boundaries, QC/Definition of Done
- [ ] Actions are concrete and executable (not abstract principles)
- [ ] Judgment boundaries explicitly state where rules apply vs. where discretion is needed
- [ ] QC/Definition of Done provides measurable or observable completion criteria
- [ ] Plain language at Grade 12 reading level
- [ ] Links to detailed specs provided for complex implementations
- [ ] Someone unfamiliar with the domain could execute the blueprint with the detailed spec
- [ ] Blueprint is at appropriate level (high-level overview, not multi-page procedure)
- [ ] Each blueprint has a clear, descriptive name that indicates what it accomplishes

---

## Experts Section

### Purpose

The Experts section identifies key authorities whose work informed this BrainLift. This serves three purposes:
1. **Credibility**: Shows whose thinking influenced your synthesis
2. **Further Learning**: Directs readers to deep expertise
3. **Attribution**: Credits intellectual foundations

### Expert Profile Structure

**Format**:
```markdown
- **==Experts==**
  - **[Expert Name]**
    - Who: [Title, affiliation, or role]
    - Focus: [Key areas of expertise]
    - Why Follow: [How their work relates to this BrainLift]
    - Where: [Social media, website, publications]
  - **[Second Expert Name]**
    - Who: [Description]
    - Focus: [Areas]
    - Why Follow: [Relevance]
    - Where: [Links]
```

**Guidelines**:
- **Count**: 4-8 experts typically (quality over quantity)
- **Who**: One sentence describing their role/credentials
- **Focus**: 3-5 key areas or concepts they're known for
- **Why Follow**: Explain the connection to THIS BrainLift specifically
- **Where**: 2-4 links (Twitter/X, website, primary platform)
- **Placement**: After DOK3, before DOK2 Knowledge Tree

### Example from S-Class BrainLift

```markdown
- **==Experts==**
  - **Wes Kao**
    - Who: Co-founder of Maven and altMBA, Marketing and Product Strategy Expert
    - Focus: Spiky points of view, online education, clear communication, rigorous thinking
    - Why Follow: Her concept of "spiky POV" directly aligns with BrainLift's DOK4, and she specialises in making complex ideas accessible and compelling through frameworks
    - Where: @weskao (Twitter), weskao.com, LinkedIn, Maven
```

**What makes this work**:
- ✅ Clear credentials (Maven co-founder)
- ✅ Specific relevance ("spiky POV" → DOK4 connection)
- ✅ Actionable follow links
- ✅ Focus areas help readers assess relevance

### Selecting Experts to Include

**Strong signals for inclusion**:
- Cited in 3+ sources in your BrainLift
- Created a framework or methodology you're using
- Their work directly inspired DOK4 SPOVs or DOK3 insights
- Recognized authority in the field

**Weak signals** (don't include):
- Mentioned once in passing
- General expertise but not specific to your BrainLift focus
- Your sources cite them, but their work isn't directly relevant to your synthesis

### Quality Checklist for Experts Section

Before finalizing, verify:

- [ ] 4-8 experts listed (not too few, not too many)
- [ ] Each expert has Who / Focus / Why Follow / Where
- [ ] "Why Follow" explains specific relevance to THIS BrainLift
- [ ] "Where" provides 2-4 active follow links
- [ ] Experts represent diverse perspectives when possible
- [ ] At least half of experts are cited in multiple sources
- [ ] Focus areas help readers understand expertise quickly

---

## DOK2 - Knowledge Tree Structure

### Purpose

The Knowledge Tree organizes sources into thematic categories, with section summaries providing navigation and context. This is the heart of the BrainLift where detailed knowledge lives.

### Section Summaries (Category-Level)

**Purpose**: Synthesize all sources within a category into a cohesive narrative.

**Format**:
```markdown
- **==[Category Name]==**
  - **==Section Summary==**
    - [2-4 sentence synthesis of all sources in this category]
```

**Guidelines**:
- One per category in Knowledge Tree
- 2-4 sentences (50-100 words)
- Synthesizes themes across ALL sources in category
- Written AFTER all sources in category are complete
- Appears at top of category, before sub-section summaries or sources

### Section Summaries (Sub-Section Level - Optional)

**Purpose**: For large categories with 10+ sources, sub-section summaries group related sources under sub-themes.

**Format**:
```markdown
- **==[Category Name]==**
  - **==Section Summary==**
    - [Overall category synthesis]
  - **==[Sub-Section Name]==**
    - **==Section Summary==**
      - [2-3 sentence synthesis of sources in this sub-section]
    - **==Sources==**
      - [Source 1]
      - [Source 2]
  - **==[Second Sub-Section Name]==**
    - **==Section Summary==**
      - [Synthesis]
    - **==Sources==**
      - [Source 3]
```

**When to use sections**:
- Category has 10+ sources
- Sources naturally cluster into 2-4 sub-themes
- Category covers multiple aspects of a topic

**When to skip sections**:
- Category has fewer than 10 sources
- All sources address similar questions
- Additional structure adds complexity without clarity

### Source-Level Insights (Optional)

**Purpose**: Synthesize DOK1 facts within a single source when the source is complex with many facts.

**Format**:
```markdown
- **[Source Title] - Author / Publication (Year)**
  - **==DOK2 Summary==**
    - [Source-level synthesis]
  - **==DOK1 Facts==**
    - **DOK1-XXX:** [Fact]
    - **DOK1-YYY:** [Fact]
  - **==Insights==**
    - [Insight 1 connecting multiple DOK1s from this source]
    - [Insight 2]
  - Link: [URL]
```

**Guidelines**:
- Optional - use only when valuable
- 2-4 insights per source maximum
- Each insight should connect 2+ DOK1 facts from the same source
- Different from DOK3 (source-level, not cross-source)

**When to include**:
- Source has 8+ DOK1 facts
- DOK1 facts cluster into themes within the source
- Source presents complex arguments that benefit from synthesis

**When to skip**:
- Source has fewer than 6 DOK1 facts
- DOK1 facts are straightforward and don't require synthesis
- DOK2 summary adequately synthesizes the source

### Deprecated: "Initial Insights"

**Do NOT use**: Category-level "Initial Insights" sections that appeared in early BrainLift versions.

**Why deprecated**: Confused the hierarchy. Category-level synthesis belongs in Section Summary (category-level). Source-specific synthesis belongs in source-level Insights (optional). Cross-source synthesis belongs in DOK3.

**If you see "Initial Insights" in old BrainLifts**:
- Move content to Section Summary if it synthesizes across sources in the category
- Move content to source-level Insights if it's specific to one source
- Move content to DOK3 if it crosses multiple sources/categories
- Delete if redundant with DOK2 summaries

---

## DOK Display Format Convention

### Overview

BrainLift uses simple, clean formatting for DOK1 and DOK2 entries to maximize readability. DOK1 facts use simple bullet points without numbering or titles. DOK2 summaries use a standard "DOK2 Summary" header without numbering.

### DOK1 Display Format

**Format**: Simple bullet points, no numbering, no titles

**Correct Format:**
```markdown
- AI document review reduces per-document costs from $2-5 to $0.10-0.50, achieving 80-95% cost reductions
- GPT-4 achieved F-score 0.871, matching junior lawyers at 0.860
- The brain cannot multitask - it switches between tasks with high cognitive cost
```

**Incorrect Format (DO NOT USE):**
```markdown
❌ DOK1-001: AI Review Costs Drop 99% vs. Human Review: AI document review costs...
❌ **DOK1-078:** AI document review reduces per-document costs...
❌ 1. AI document review reduces per-document costs...
```

**Key Points:**
- No "DOK1-XXX" prefixes or numbers
- No titles before the fact
- No manual numbering (1., 2., 3.)
- Just simple dash bullets with clean, direct facts

### DOK2 Display Format

**Format**: "DOK2 Summary" header, no numbering

**Correct Format:**
```markdown
**==DOK2 Summary==**
  - This empirical study reveals AI document review achieves dramatic cost reductions while maintaining accuracy parity with junior attorneys. AI reduces per-document costs from $2-5 (human) to $0.10-0.50 (AI-assisted)...
```

**Incorrect Format (DO NOT USE):**
```markdown
❌ **==DOK2-015 - Cost Economics Summary==**
❌ **==DOK2-001 - summary==**
❌ **==DOK2 Summary 1==**
```

**Key Points:**
- Use exactly "DOK2 Summary" as the header
- No "DOK2-XXX" prefixes or numbers
- No descriptive titles after "DOK2 Summary"
- One DOK2 Summary per source typically

### DOK3 and DOK4 Display Format

**DOK3 Format**: Descriptive titles without numbering

DOK3 has two subsections: Insights and Blueprints

```markdown
- **==DOK3 - Insights==**
  - **Documentation succeeds through productive incompleteness** - Whether it's SPOVs...
  - **AI cost advantages concentrate in pattern-based review** - Privilege review shows...

- **==DOK3 - Blueprints==**
  - **[Blueprint Name]** - [Overview]
    - **Domain Context**: ...
    - **Actions**: ...
```

**DOK4 Format**: Bold statement titles without numbering
```markdown
- **==DOK4 - Spiky Points of View==**
  - **The best BrainLift documentation is embarrassingly incomplete.** Most documentation fails...
  - **Hot documents are found, not decided.** Most review frameworks treat hot document...
```

**Key Points:**
- DOK3 and DOK4 use descriptive titles in bold
- No "DOK3-XXX" or "DOK4-XXX" prefixes
- Titles capture the essence of the insight or SPOV

### Rationale for Simple Format

**1. Readability**
- Simple bullets are easier to scan and read
- No cognitive overhead from parsing numbering schemes
- Clean, professional appearance

**2. Focus on Content**
- Numbering systems draw attention away from the actual facts
- Simple bullets keep focus on the knowledge itself
- Reduces visual clutter

**3. Flexibility**
- Easy to add, remove, or reorder facts without renumbering
- No broken cross-references when facts are reorganized
- More maintainable over time

### Quality Checklist

Before finalizing a BrainLift, verify:

- [ ] All DOK1 facts use simple bullet format (no numbering, no titles)
- [ ] DOK2 uses exactly "**==DOK2 Summary==**" header format
- [ ] No "DOK1-XXX:" or "DOK2-XXX" prefixes in the BrainLift document
- [ ] DOK3 and DOK4 use descriptive titles without numbering prefixes
- [ ] External frameworks can reference DOK codes (e.g., DOK1-006) but BrainLift doesn't display them
- [ ] Clean, simple visual presentation throughout

---

## Markdown Formatting Conventions

### Overview

BrainLift documents use consistent Markdown formatting to create clear visual hierarchy and improve scanability. The `**==TEXT==**` convention (bold + double equals) marks section headers at various levels.

### Section Header Hierarchy

**Format Convention**: `**==TEXT==**` for all section headers

This creates a distinct visual marker that's easy to scan and clearly separates sections from regular emphasis.

**Examples by Level**:

```markdown
- **==DOK4 - Spiky Points of View==**           (Top-level section)
- **==DOK3 - Insights==**                        (DOK3 subsection)
- **==DOK3 - Blueprints==**                      (DOK3 subsection)
- **==Experts==**                                (Top-level section)
- **==Document Review Economics==**              (Knowledge Tree category)
- **==Section Summary==**                        (Category/sub-section summary)
- **==Sources==**                                (Source container)
- **==DOK2 Summary==**                           (Source-level header)
- **==DOK1 Facts==**                             (Source-level header)
- **==Insights==**                               (Optional source-level header)
```

### Regular Emphasis vs. Section Headers

**Section Headers** use `**==TEXT==**`:
- DOK4, DOK3 - Insights, DOK3 - Blueprints, Experts section headers
- Knowledge Tree category names
- Section Summary, Sources headers
- DOK2 Summary, DOK1 Facts headers

**Regular Bold** uses `**TEXT**` (without double equals):
- DOK3 insight titles: `**Documentation succeeds through productive incompleteness**`
- DOK3 blueprint names: `**[Hot Document Identification]**`
- DOK4 SPOV titles: `**The best BrainLift documentation is embarrassingly incomplete.**`
- Emphasis within body text: `**In Scope:**`, `**Out of Scope:**`
- Expert profile fields: `Who:`, `Focus:`, `Why Follow:`, `Where:`

### Complete Formatting Example

```markdown
- **==DOK4 - Spiky Points of View==**
  - **The best BrainLift documentation is embarrassingly incomplete.** Most documentation fails by trying...
  - **Confusion is a feature, not a bug.** Traditional documentation aims...

- **==DOK3 - Insights==**
  - **Documentation succeeds through productive incompleteness** - Whether it's SPOVs...
  - **Cognitive constraints drive quality** - The 2500-token limit...

- **==DOK3 - Blueprints==**
  - **[Hot Document Identification]** - Systematically identify case-determinative documents...
    - **Domain Context**: ...
    - **Actions**: ...

- **==Experts==**
  - **Wes Kao**
    - Who: Co-founder of Maven and altMBA
    - Focus: Spiky points of view, online education
    - Why Follow: Her concept of "spiky POV" directly aligns with BrainLift's DOK4
    - Where: @weskao (Twitter), weskao.com

- **==DOK2 - Knowledge Tree==**
  - **==Document Review Economics==**
    - **==Section Summary==**
      - This category synthesizes research on AI cost impacts...
    - **==Sources==**
      - **AI Legal Review Study - Research Team / Legal Tech Journal (2024)**
        - **==DOK2 Summary==**
          - This empirical study reveals...
        - **==DOK1 Facts==**
          - AI document review reduces per-document costs from $2-5 to $0.10-0.50
          - GPT-4 achieved F-score 0.871, matching junior lawyers at 0.860
        - Link: https://example.com
```

### Why This Convention?

**Visual Scanability**: The `**==TEXT==**` format creates clear visual anchors when scanning long documents. The double equals act as "bookends" that make section headers instantly recognizable.

**Semantic Clarity**: Distinguishes structural headers (sections) from content emphasis (bold within text). Readers immediately know whether they're seeing navigation elements or emphasized content.

**Markdown Compatibility**: Works in all Markdown processors. The double equals don't conflict with any Markdown syntax, and the bold renders correctly everywhere.

**Search-Friendly**: The `==TEXT==` pattern is unique enough to search for section headers specifically without matching regular emphasized text.

### Quality Checklist

Before finalizing a BrainLift, verify:

- [ ] All section headers use `**==TEXT==**` format (bold + double equals)
- [ ] DOK3 and DOK4 titles use simple bold: `**Title**` (no double equals)
- [ ] Regular emphasis uses simple bold: `**text**`
- [ ] No inconsistent header formats (e.g., `##` markdown headers in Knowledge Tree)
- [ ] Visual hierarchy is clear and consistent throughout

---

## BrainLift Document Structure

### Overview

BrainLift documents organize knowledge into **Knowledge Tree categories** containing multiple **sources**, where each source produces one or more **DOK2 summaries** that synthesize logically related **DOK1 facts**. Understanding when to separate sources and how to structure DOK2 summaries is critical for maintaining clean, queryable knowledge bases.

### Source Separation Rules

**When to Create Separate Source Sections:**

1. **Different URLs or Publications** - Each distinct URL or publication gets its own source section
   - ✅ Split: "Article A" from website1.com AND "Article B" from website2.com
   - ✅ Split: "Report 2023" AND "Report 2024" from same organization (different publications)

2. **Do NOT Split Based Solely on Different Authors** - Multiple authors within the same publication stay together
   - ❌ Don't split: "Article by Author X and Author Y" from same URL
   - ❌ Don't split: Different chapters of same report by different authors

**Rationale:** Each source should have a distinct, citable reference (URL or publication). This enables verification, prevents duplicate extraction from the same material, and maintains clear provenance for each DOK1 fact.

### Multiple DOK2 Summaries Per Source

**Key Principle:** One source CAN have multiple DOK2 summaries. There is no one-to-one mapping between sources and DOK2s.

**When to Create Multiple DOK2s for a Single Source:**

1. **Logical Clustering** - DOK1 facts naturally group into distinct themes or topics
   - Example: Source covers both "cost economics" AND "quality metrics" - create DOK2-A for economics facts, DOK2-B for quality facts

2. **Excessive DOK1 Count** - Source yields 15+ DOK1 facts that become unwieldy in single summary
   - Example: Comprehensive report with 20 DOK1 facts splits into 2-3 thematic DOK2 summaries

3. **Different Application Contexts** - DOK1 facts serve different use cases within frameworks
   - Example: Source discusses both "initial review workflows" AND "escalation procedures" - separate DOK2s enable targeted framework references

**When to Keep Single DOK2 for a Source:**

1. **Coherent Theme** - All DOK1 facts address a unified topic or research question
   - Example: Case study focused entirely on privilege review implementation

2. **Small DOK1 Count** - Source yields 3-8 DOK1 facts that naturally summarize together
   - Example: Blog post with focused scope

3. **Interconnected Insights** - DOK1 facts rely on each other for context and cannot be cleanly separated
   - Example: Research paper where findings build sequentially on each other

### Source Section Structure

Each source must follow this structure:

```markdown
- **[Source Title] - [Author/Organization] / [Publication] ([Year])**
  - **==DOK2 Summary==**
    - [4-5 sentence summary synthesizing the source's key insights]
  - **==DOK1 Facts==**
    - [Single sentence fact, 15-25 words]
    - [Another single sentence fact, 15-25 words]
    - [Additional facts as simple bullets...]
  - Link: [URL]
```

**Important Notes:**

1. **DOK2 Format** - Use "DOK2 Summary" header (no numbering), one per source typically
2. **DOK1 Format** - Simple bullet points without numbering or titles
3. **DOK2 Placement** - DOK2 Summary appears BEFORE the DOK1 Facts section
4. **Single Link Line** - One "Link:" line per source, placed at the end
5. **No Cross-References** - DOK2 Summary synthesizes themes; no requirement to cite specific DOK1 items

### Example: Single Source

```markdown
- **Comprehensive AI Legal Review Study - Research Team / Legal Tech Journal (2024)**
  - **==DOK2 Summary==**
    - This empirical study reveals AI document review achieves dramatic cost reductions while maintaining accuracy parity with junior attorneys. AI reduces per-document costs from $2-5 (human) to $0.10-0.50 (AI-assisted), achieving 80-95% cost reductions across five litigation types. GPT-4 achieved F-score 0.871, matching junior lawyers at 0.860. AI maintains consistent accuracy with F-score standard deviation of 0.02 versus 0.12 for human reviewers, eliminating fatigue-based quality degradation. Human accuracy declines 15-25% after 4+ hour review sessions, while AI maintains performance regardless of processing speed.
  - **==DOK1 Facts==**
    - AI document review reduces per-document costs from $2-5 to $0.10-0.50, achieving 80-95% cost reductions
    - GPT-4 achieved F-score 0.871, matching junior lawyers at 0.860
    - AI maintains consistent F-score standard deviation of 0.02 versus 0.12 for human reviewers
    - Human accuracy degrades 15-25% after 4+ hour review sessions
    - AI eliminates fatigue-based quality degradation while humans show performance decline
    - Cost per document dropped from $74 (junior lawyers) to $0.25 (GPT-4)—a 99.97% reduction
  - Link: https://legaltechjournal.com/ai-review-study-2024
```

### Example: Two Separate Sources Under One Category

```markdown
## Knowledge Tree

- **==Document Review Economics & Effectiveness==**
  - **==Section Summary==**
    - [Category-level summary synthesizing insights across all sources in this category]
  - **==Sources==**
    - **Handling Hot Docs - Mark Lyon / marklyon.org (2013)**
      - **==DOK2 Summary==**
        - This foundational framework establishes that hot documents transcend binary relevance to become case-determinative materials requiring immediate escalation. Document review represents 70-80% of total discovery costs, making it the primary cost driver. The critical challenge is over-identification where reviewers flag too many documents as "hot," diluting supervisor attention. Systematic categorical tagging transforms reviewed document sets into queryable strategic databases. A disciplined hot document reporting format prevents reviewer bias while enabling effective escalation.
      - **==DOK1 Facts==**
        - Hot documents have "clear potential to impact the instant case or even an unrelated matter"
        - Document review represents 70-80% of total ediscovery expenses, making it the primary cost driver
        - Over-identification of hot documents dilutes strategic focus and supervisor attention
        - Hot document reports should include only identifier, date, parties, and brief explanation—no direct quotes
      - Link: https://marklyon.org/2013/04/handling-hot-docs/

    - **What Is Document Review? - Zapproved / Zapproved Blog (2024)**
      - **==DOK2 Summary==**
        - This comprehensive overview defines document review's role across multiple legal contexts including litigation, regulatory investigations, and M&A due diligence. Processing-stage culling determines the review universe through custodian, date range, and keyword decisions before human review begins. Federal Rule 26(b)(1) requires discoverable information to be "relevant to any party's claim or defense and proportional to the needs of the case." Categorical tagging creates multi-dimensional metadata profiles enabling sophisticated querying beyond simple relevant/non-relevant binaries. Review effectiveness depends critically on these upstream strategic decisions about which documents merit human review time.
      - **==DOK1 Facts==**
        - Categorical tags create multi-dimensional document profiles beyond binary relevance determinations
        - The processing stage reduces document population using agreed criteria (custodians, date ranges, search terms)
        - Federal Rule 26(b)(1) requires discovery to be "relevant to any party's claim or defense and proportional to the needs of the case"
        - Document review serves multiple legal contexts: litigation, regulatory investigations, M&A due diligence
      - Link: https://zapproved.com/blog/what-is-document-review/
```

### Quality Checklist for Source Structure

Before finalizing a BrainLift section, verify:

- [ ] Each distinct URL/publication has its own source section
- [ ] No sources are combined solely because they have different authors
- [ ] Each source has exactly one DOK2 Summary (typically)
- [ ] DOK2 Summary uses header format: **==DOK2 Summary==** (no numbering)
- [ ] DOK1 Facts uses header format: **==DOK1 Facts==** (no numbering)
- [ ] DOK2 Summary appears before the DOK1 Facts section
- [ ] DOK1 facts use simple bullet format (no numbering, no titles)
- [ ] Each source has exactly one "Link:" line at the end
- [ ] No "Initial Insights" sections (deprecated format)
- [ ] Source title format: **[Title] - [Author] / [Publication] ([Year])**
- [ ] DOK2 Summary synthesizes themes without needing to cite specific DOK1 items

---

## DOK1 Writing Guidelines

### Purpose

DOK1 facts serve as the atomic units of knowledge in the BrainLift system. They must be clear, accurate, and accessible to readers with a high school education (Grade 12 reading level). Dense academic or legal language creates barriers to understanding and reduces the BrainLift's utility across diverse audiences.

### Plain Language Principles

**Target Audience:** High school graduates and above (Flesch-Kincaid Grade 12)

**Core Guidelines:**
1. **Sentence Length:** 15-25 words average, 35 words maximum
2. **Active Voice:** Prefer active over passive constructions
3. **Common Vocabulary:** Use everyday words over jargon when possible
4. **Concrete Examples:** Include specific examples to illustrate abstract concepts
5. **One Idea Per Sentence:** Don't nest multiple claims in complex sentences

### DOK1 Structure Template

Each DOK1 entry uses simple bullet format without numbering:

```markdown
- [Single sentence stating the core fact, 15-25 words]
```

**For complex concepts requiring elaboration:**

```markdown
- [First sentence: core claim, 15-20 words]. [Second sentence: elaboration or mechanism, 20-25 words]. [Third sentence (optional): concrete example or implication, 15-20 words]
```

**Length Guidelines:**
- **Preferred**: 1 sentence (15-25 words)
- **When needed**: 2-3 sentences for complex concepts (40-75 words total)

**Example Structure (1 sentence - preferred):**

```markdown
- AI document review costs $0.25 per document compared to $74 for junior lawyers—a 99.7% reduction
- The brain cannot multitask - it switches between tasks with high cognitive cost
- Hot documents have "clear potential to impact the instant case or even an unrelated matter"
```

**Example Structure (2-3 sentences - when needed):**

```markdown
- AI document review costs $0.25 per document compared to $74 for junior lawyers—a 99.7% reduction. This shifts document review from a labor-intensive bottleneck to a scalable operation with near-zero marginal costs.
```

### DOK1 Style Patterns

Based on S-Class BrainLift examples, effective DOK1 facts follow these patterns:

#### Pattern 1: Dash Connections

Use dashes to connect related concepts in a clear cause-effect or equivalence relationship:

```markdown
- Element interactivity determines intrinsic cognitive load - how many elements must be processed simultaneously
- The brain cannot multitask - it switches between tasks with high cognitive cost
- A spiky POV is a perspective others can disagree with - if everyone agrees, it's too middle of the road
```

#### Pattern 2: Direct Statements

Use clear, assertive statements without hedging:

```markdown
✅ Good:
- SPOVs are your thesis about topics in your realm of expertise
- Writing for an audience forces clearer thinking than private notes
- Hot documents need immediate supervisor escalation

❌ Avoid hedging:
- SPOVs are generally considered to be your thesis...
- Writing for an audience may potentially force clearer thinking...
- Hot documents typically should be escalated to supervisors...
```

#### Pattern 3: Inline Examples

When examples are brief, include them inline rather than as separate sentences:

```markdown
- Experts have schemas that treat multiple interacting elements as single units
- Split-attention effect occurs when learners must mentally integrate separated text and diagrams
- Mindful productivity balances ambition with mental health sustainability
```

#### Pattern 4: Concrete Comparisons

Use specific numbers and comparisons to make abstract concepts tangible:

```markdown
- AI maintains consistent F-score standard deviation of 0.02 versus 0.12 for human reviewers
- Human accuracy degrades 15-25% after 4+ hour review sessions
- AI review costs $0.25 per document compared to $74 for junior lawyers
```

### Simplification Techniques

#### Replace Academic/Legal Jargon

| ❌ Avoid | ✅ Use Instead |
|---------|---------------|
| transcend binary determinations | go beyond yes/no answers |
| multi-dimensional metadata profiles | rich document tags with multiple categories |
| case-determinative materials | documents that can change case outcomes |
| dual-gated test | two-part test |
| upstream design decisions | early planning choices |
| proportionality analysis | balancing costs vs. benefits |
| empirical validation | real-world testing |
| nominalizations (e.g., "determination") | verbs (e.g., "determine") |

#### Split Long Sentences

**Before (68 words):**
> Document review represents 70-80% of total ediscovery expenses, making it the primary cost driver in litigation and therefore the primary opportunity for strategic cost management through effective prioritization and culling methodologies that focus review efforts on materials most likely to yield case-critical insights.

**After (3 sentences, 22/15/19 words):**
> Document review represents 70-80% of total ediscovery expenses, making it the primary cost driver in litigation. This creates a major cost management opportunity. Effective prioritization and culling can focus review efforts on materials most likely to yield critical insights.

#### Use Concrete Examples

**Before (abstract):**
> Hot documents reveal critical contradictions between witness testimony and documentary evidence.

**After (concrete):**
> Hot documents reveal critical contradictions between witness testimony and documentary evidence. Example: Meeting minutes prove X was considered when all witnesses said it wasn't.

#### Front-Load Key Information

**Before (key info buried):**
> The governing framework under Federal Rule of Civil Procedure 26(b)(1) establishes that discoverable information must be "relevant to any party's claim or defense and proportional to the needs of the case."

**After (key info first):**
> Discoverable information must be "relevant to any party's claim or defense and proportional to the needs of the case" under Federal Rule 26(b)(1).

### Common Patterns to Simplify

#### Pattern 1: Nested Qualifiers

**Before:**
> The processing stage intentionally reduces the document population before human review begins by culling based on agreed criteria like custodians, date ranges, and search terms - meaning the effectiveness of document review depends critically on upstream strategic decisions.

**After:**
> The processing stage reduces the document population before human review using agreed criteria (custodians, date ranges, search terms). This means document review effectiveness depends on these early strategic decisions.

#### Pattern 2: Passive Voice

**Before:**
> The recommended reporting structure for hot documents includes only document identifier, date, parties, and brief explanation.

**After:**
> Hot document reports should include only: document identifier, date, parties, and brief explanation.

#### Pattern 3: Abstract Chains

**Before:**
> This creates a classification task more amenable to AI pattern recognition than subjective relevance determinations requiring case-specific strategic judgment.

**After:**
> This makes privilege review easier for AI than relevance review. Privilege follows patterns; relevance requires case-specific judgment.

### Quality Checklist for DOK1 Entries

Before finalizing a DOK1 fact, verify:

- [ ] Average sentence length: 15-25 words
- [ ] No sentences exceed 35 words
- [ ] Active voice used where possible
- [ ] Technical terms defined or replaced with common words
- [ ] At least one concrete example if concept is abstract
- [ ] No nested parentheticals within parentheticals
- [ ] Quoted material from source preserved exactly
- [ ] One main claim per sentence
- [ ] Reading level: Grade 12 or below (can check with online tools)

### Preserving Accuracy While Simplifying

**Critical Rules:**
1. **Preserve All Quoted Material:** Never simplify direct quotes from sources
2. **Maintain Factual Precision:** Don't round numbers or generalize data
3. **Keep Technical Terms When Necessary:** Some legal/technical terms have no simpler equivalent
4. **Don't Oversimplify Complexity:** If a concept is genuinely complex, break it into multiple sentences rather than losing nuance

**Example - Preserving Quotes:**

**Before:**
> Hot documents possess "clear potential to impact the instant case or even an unrelated matter" and require immediate supervisor escalation.

**After (quote preserved):**
> Hot documents have "clear potential to impact the instant case or even an unrelated matter" and need immediate supervisor escalation.

### Examples: Before and After

These examples show how to transform dense academic language into clear, simple-bullet DOK1 facts.

#### Example 1: Hot Documents

**Before (101 words, Grade 18+):**
> Hot documents possess "clear potential to impact the instant case or even an unrelated matter" and require immediate supervisor escalation - they are not simply "relevant" documents but ones that fundamentally alter case strategy, either by strongly supporting litigation positions or by revealing critical contradictions between witness testimony and documentary evidence (such as meeting minutes showing X was considered and attempted when all witnesses claimed X was never contemplated).

**After (62 words, Grade 12, simple bullet format):**
```markdown
- Hot documents have "clear potential to impact the instant case or even an unrelated matter" and need immediate supervisor escalation
- Unlike simply "relevant" documents, hot documents can change case strategy—either by strongly supporting your position or by showing contradictions between witness testimony and documentary evidence
- Example: Meeting minutes prove X was considered when all witnesses said it wasn't
```

#### Example 2: Processing Stage Culling

**Before (61 words, Grade 16+):**
> The processing stage intentionally reduces the document population before human review begins by culling based on agreed criteria like custodians, date ranges, and search terms - meaning the effectiveness of document review depends critically on upstream strategic decisions about what document populations merit the substantial investment of human review time versus automated filtering.

**After (43 words, Grade 11, simple bullet format):**
```markdown
- The processing stage reduces the document population before human review using agreed criteria (custodians, date ranges, search terms)
- Document review effectiveness depends on these early decisions about which documents merit human review time versus automated filtering
```

#### Example 3: Speed-Accuracy Tradeoff

**Before (72 words, Grade 17+):**
> Human reviewers face an inherent speed-accuracy tradeoff where faster review (40-50 documents per hour) reduces accuracy while careful review (1-2 documents per hour) improves precision, whereas LLMs maintain consistent accuracy regardless of processing speed, effectively decoupling the speed-quality tradeoff that constrains human review economics and enabling "careful analysis at machine speed."

**After (53 words, Grade 12, simple bullet format):**
```markdown
- Human reviewers face a speed-accuracy tradeoff: faster review (40-50 docs/hour) reduces accuracy, while careful review (1-2 docs/hour) improves precision
- LLMs maintain consistent accuracy at any speed
- This decouples the speed-quality tradeoff that limits human review economics, enabling "careful analysis at machine speed"
```

---

## DOK2 Writing Guidelines

### Purpose

DOK2 summaries synthesize the key insights from a single source, connecting multiple DOK1 facts into a coherent narrative. Like DOK1 entries, they must be accessible to readers with a high school education (Grade 12 reading level) while capturing the essence and significance of the source material.

### DOK2 vs. DOK1: Key Differences

| Aspect | DOK1 | DOK2 |
|--------|------|------|
| **Format** | Simple bullet points | "DOK2 Summary" header |
| **Scope** | Single atomic fact | Synthesis of multiple related DOK1 facts |
| **Length** | 1 sentence preferred (15-25 words); 2-3 for complex concepts (40-75 words) | 4-5 sentences (80-150 words) |
| **Sentence Length** | 15-25 words avg, 35 max | 20-30 words avg, 40 max |
| **Function** | State one specific claim | Show connections and "so what" |
| **Technical Terms** | Minimize, replace with common words | Can retain some for precision |
| **Examples** | Include concrete examples inline when brief | Focus on patterns and themes |
| **Numbering** | No numbering (simple bullets) | No numbering (just "DOK2 Summary") |

### Plain Language Principles for DOK2

**Target Audience:** High school graduates and above (Flesch-Kincaid Grade 12)

**Core Guidelines:**
1. **Sentence Count:** 4-5 sentences (not 1-2 run-on sentences)
2. **Sentence Length:** 20-30 words average, 40 words maximum
3. **Active Voice:** Prefer active over passive constructions
4. **Synthesis Focus:** Show how DOK1 facts connect, don't just list them
5. **Clear Structure:** Topic sentence → supporting points → implication

### DOK2 Structure Template

Each DOK2 entry uses "DOK2 Summary" header (no numbering) and follows a 4-5 sentence structure:

```markdown
**==DOK2 Summary==**
  - [Sentence 1: Topic sentence introducing source's main contribution, 20-25 words]. [Sentence 2: First key finding or theme, 25-30 words]. [Sentence 3: Second key finding or theme, 25-30 words]. [Sentence 4: Third finding or implication, 25-30 words]. [Sentence 5 (optional): "So what" or significance, 20-25 words].
```

**Example Structure:**

```markdown
**==DOK2 Summary==**
  - This empirical study compares AI and human document review accuracy, revealing AI matches professional competency at dramatically lower cost. GPT-4 achieved F-score 0.871, matching junior lawyers at 0.860, while completing review 77x faster. Cost per document dropped from $74 (junior lawyers) to $0.25 (GPT-4)—a 99.97% reduction. AI maintains consistent accuracy regardless of speed, breaking the human speed-quality tradeoff. This enables previously uneconomical litigation by making comprehensive review viable for mid-stakes cases.
```

### Common DOK2 Problems and Solutions

#### Problem 1: Run-On Sentences with Multiple Nested Clauses

**Before (150 words, 1 sentence):**
> Industry-wide survey data from November 2024 reveals GenAI document review transitioning from early adopter experimentation to mainstream practice, with 48% of legal professionals currently using GenAI (split between 51% law firm adoption vs. 45% corporate legal), 64% planning document review usage within one year, and 93% expecting usage within five years, while counterintuitively hallucination concerns rank as the LEAST important risk factor despite media emphasis (89% comfortable with GenAI for review), with adoption led by paralegals and legal operations (>50%) over attorneys (47%)—suggesting value creation shifting from document processing toward synthesis...

**After (107 words, 5 sentences):**
> Industry-wide survey data from November 2024 shows GenAI document review transitioning from early adopter experimentation to mainstream practice. Currently 48% of legal professionals use GenAI (51% law firms vs. 45% corporate legal), with 64% planning usage within one year and 93% within five years. Counterintuitively, hallucination concerns rank as the LEAST important risk factor despite media emphasis—89% feel comfortable with GenAI for review. Paralegals and legal operations (>50%) lead adoption over attorneys (47%), suggesting value creation shifting from document processing toward synthesis. The 41-point gap between comfort (89%) and usage (48%) indicates implementation barriers around platform availability, training, and workflow integration.

**Techniques Used:**
- Split 150-word sentence into 5 sentences (21 words average)
- Removed nested parentheticals where possible
- Created logical flow: current state → projections → surprising finding → adoption pattern → interpretation

#### Problem 2: Dense Academic/Legal Language

**Before:**
> ...revealing that privilege review's pattern-recognizable characteristics (attorney involvement, legal advice indicators, confidentiality markings) make it more amenable to AI classification than subjective relevance determinations requiring case-specific strategic judgment—explaining consistent 70-90% efficiency gains in privilege applications versus 30-50% for general review.

**After:**
> Privilege review shows consistently higher efficiency gains (70-90%) than general relevance review (30-50%). This occurs because privilege determination relies on identifiable patterns—attorney involvement, legal advice language, and confidentiality markers. These patterns are easier for AI to recognize than the subjective, case-specific judgment required for relevance determinations.

**Techniques Used:**
- Front-load key finding (70-90% vs. 30-50%)
- Split complex explanation across 2-3 shorter sentences
- Replace "amenable to AI classification" with "easier for AI to recognize"
- Replace "pattern-recognizable characteristics" with "identifiable patterns"

#### Problem 3: Listing Facts Without Synthesis

**Weak DOK2 (just lists DOK1 facts):**
> This source discusses hot documents. Hot documents need immediate escalation. Reviewers struggle with over-identification. Hot document reports should avoid editorializing.

**Strong DOK2 (synthesizes connections):**
> This framework establishes that hot documents go beyond simple relevance to become case-determinative materials requiring immediate escalation. The critical challenge is the over-identification problem where reviewers flag too many documents as "hot," diluting supervisor attention. A disciplined reporting format (identifier, date, parties, brief explanation—no quotes) forces objective flagging while preventing bias. This calibrated approach ensures truly strategic materials get proper attention.

**Techniques Used:**
- Shows relationship between concepts (hot docs → over-identification → reporting format → outcome)
- Explains "why" not just "what"
- Creates narrative flow
- Highlights the "so what" (ensures strategic materials get attention)

### Synthesis Techniques

#### Technique 1: Thematic Grouping

Group related DOK1 facts by theme, then summarize each theme in one sentence:

**DOK1 facts cover:**
- Cost reduction (DOK1-017, DOK1-018)
- Time compression (DOK1-020)
- Variation by context (DOK1-021)
- Selection bias warning (DOK1-024)

**DOK2 synthesis:**
> Real-world implementations demonstrate measurable cost reductions of 30-50% and time savings of 40-70% across different case types. Review timelines compress from months to weeks for million-document populations. Results vary significantly by application, with privilege review showing higher benefits (50-90%) than general relevance review. Vendor case studies likely reflect selection bias toward successful implementations, so actual results may vary more widely.

#### Technique 2: Cause-and-Effect Chains

Show how one finding leads to another:

**DOK1 sequence:**
- AI eliminates false positives (DOK1-026)
- This reduces review population by 87% (DOK1-025)
- Leading to $1M cost savings (DOK1-028)
- Higher credibility from named client (DOK1-027)

**DOK2 synthesis:**
> The Microsoft case study demonstrates 87% reduction in privilege review documents (190,000 to 24,000) by using AI to classify 70% of privilege-term hits as "unlikely privileged." This eliminates false positives at scale, achieving nearly $1 million in cost savings. The implementation's credibility stems from specific client identification and concrete metrics rather than anonymous case studies. This shows privilege review's pattern-recognizable characteristics make it especially suitable for AI assistance.

#### Technique 3: Contrast and Comparison

Highlight differences or unexpected findings:

**DOK1 contrasts:**
- Humans face speed-accuracy tradeoff (DOK1-014)
- LLMs maintain consistent accuracy at any speed (DOK1-014)
- This enables previously uneconomical litigation (DOK1-015)

**DOK2 synthesis:**
> Human reviewers face an inherent speed-accuracy tradeoff: faster review reduces accuracy, while careful review improves precision. LLMs maintain consistent accuracy regardless of processing speed, decoupling the speed-quality constraint. This transformation makes comprehensive document review financially viable for mid-stakes cases ($500K-$2M damages) that previously couldn't support traditional review costs ($100K-$300K). The result potentially expands access to justice while creating competitive advantage for firms implementing AI workflows.

### Quality Checklist for DOK2 Entries

Before finalizing a DOK2 summary, verify:

- [ ] 4-5 sentences total (not 1-2 run-on sentences)
- [ ] Average sentence length: 20-30 words
- [ ] No sentences exceed 40 words
- [ ] Active voice used where possible
- [ ] Shows connections between DOK1 facts (synthesis, not list)
- [ ] Highlights "so what" or significance
- [ ] Reading level: Grade 12 or below
- [ ] No nested parentheticals within parentheticals
- [ ] Logical flow from sentence to sentence
- [ ] Includes key quantitative findings from source

### Preserving Accuracy While Simplifying

**Critical Rules (same as DOK1):**
1. **Preserve All Quoted Material:** Keep exact quotes from sources
2. **Maintain Factual Precision:** Don't round numbers or generalize data
3. **Keep Key Technical Terms:** Some terms have no simpler equivalent
4. **Don't Lose Nuance:** If a finding is genuinely complex, use multiple sentences

### Examples: Before and After

#### Example 1: DOK2-002

**Before (129 words, 1 sentence, Grade 18+):**
> This controlled empirical study provides the first rigorous quantitative comparison of GPT-4 and Claude performance against human lawyers on legal document review tasks, revealing that GPT-4-1106 achieves professional-grade accuracy (F-score 0.871) statistically equivalent to junior lawyers (0.860) and LPO practitioners (0.874) while completing review 77-276x faster at 99.97% lower cost per document ($0.25 vs. $74.26 for junior lawyers), with the critical finding that model version selection matters more than the binary distinction of "using AI" given substantial performance variance between GPT-4 versions and the consistent accuracy LLMs maintain regardless of processing speed—effectively decoupling the speed-quality tradeoff that constrains human review economics and enabling previously uneconomical litigation by making comprehensive document review financially viable for mid-stakes cases.

**After (96 words, 5 sentences, Grade 12):**
> This empirical study provides the first rigorous comparison of GPT-4 and Claude performance against human lawyers on document review tasks. GPT-4-1106 achieves professional-grade accuracy (F-score 0.871), matching junior lawyers (0.860) and LPO practitioners (0.874), while completing review 77-276x faster at 99.97% lower cost ($0.25 vs. $74.26). A critical finding: model version selection matters more than simply "using AI" given substantial performance variance between versions. LLMs maintain consistent accuracy regardless of speed, decoupling the speed-quality tradeoff that constrains human review. This makes comprehensive document review financially viable for mid-stakes cases that previously couldn't support traditional review costs.

#### Example 2: DOK2-004

**Before (124 words, 1 sentence, Grade 17+):**
> The Microsoft Hart-Scott-Rodino Second Request matter provides a named-client case study demonstrating 87% reduction in privilege review document population (from 190,000 expected documents to 24,000 requiring human review) by using AI to classify 70% of privilege-term-hitting documents as "unlikely privileged," eliminating false positives at scale and achieving nearly $1 million in litigation cost savings while reducing privilege log preparation time by 50%, with the implementation's higher credibility stemming from specific client identification and concrete metrics rather than anonymous case studies, revealing that privilege review's pattern-recognizable characteristics (attorney involvement, legal advice indicators, confidentiality markings) make it more amenable to AI classification than subjective relevance determinations—explaining consistent 70-90% efficiency gains in privilege applications versus 30-50% for general review.

**After (102 words, 5 sentences, Grade 12):**
> The Microsoft Hart-Scott-Rodino Second Request provides a named-client case study demonstrating 87% reduction in privilege review documents (from 190,000 expected to 24,000 requiring human review). AI classified 70% of privilege-term hits as "unlikely privileged," eliminating false positives at scale and achieving nearly $1 million in cost savings. AI-generated privilege logs reduced preparation time by 50%. The implementation's credibility stems from specific client identification and concrete metrics rather than anonymous case studies. Privilege review shows consistently higher efficiency gains (70-90%) than general relevance review (30-50%) because privilege determination relies on identifiable patterns that AI recognizes better than subjective relevance judgments.

---

## Future Style Guide Sections

This style guide will be expanded to include:

- [x] BrainLift Document Structure Overview (inverted pyramid)
- [x] Owner(s) and Purpose sections
- [x] DOK4 - Spiky Points of View Guidelines
- [x] DOK3 - Insights Guidelines
- [x] DOK3 - Blueprints Guidelines
- [x] Experts Section (four-part structure)
- [x] DOK2 - Knowledge Tree Structure (with Section Summary terminology)
- [x] DOK Display Format Convention
- [x] Markdown Formatting Conventions (`**==TEXT==**` convention)
- [x] BrainLift Document Structure (Sources & Categories)
- [x] DOK1 Writing Guidelines (verbosity, format, self-containment)
- [x] DOK2 Writing Guidelines (synthesis level, source attribution)
- [ ] Source Selection Criteria (2023-2025 preference, quality signals)
- [ ] Cross-Referencing Best Practices
- [ ] Version Control and Update Procedures

---

**Document Version:** 1.2
**Last Updated:** 2025-10-31
**Status:** Added DOK3 - Blueprints guidelines. Restructured DOK3 Guidelines section to include both Insights and Blueprints subsections with complete documentation, examples, and quality checklists.
