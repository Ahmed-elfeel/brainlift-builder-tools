 # LLM BrainLift Construction Guide

> **Purpose:** Concise operational reference for LLMs building and maintaining BrainLift knowledge bases. Focuses on executable rules without extensive pedagogy.

---

## Quick Reference

**Critical Rules:**
- Single file: BrainLift.md (do NOT split into multiple files)
- DOK1 display: Simple bullets, no numbering, no titles, no "DOK1-XXX:" prefixes
- DOK2 display: Exactly `**==DOK2 Summary==**` header (no numbering, no descriptive titles)
- Markdown headers: Use `**==TEXT==**` (bold + double equals) for all section headers
- Sentence limits: DOK1 max 35 words, DOK2 max 40 words
- Structure: Build bottom-up (DOK1→DOK2→DOK3 Insights→DOK3 Blueprints→DOK4), present top-down (DOK4→DOK3→DOK2→DOK1)
- Reading level: Target Grade 12 for all DOK1 and DOK2 content
- Source separation: One source per distinct URL/publication (NOT per author)
- DOK2 per source: Can have multiple DOK2s when logical clustering exists

---

## Document Structure

### Inverted Pyramid Presentation Order

```
1. **==Owner(s)==**
2. **==Purpose==** (In Scope / Out of Scope)
3. **==DOK4 - Spiky Points of View==** (3-5 SPOVs)
4. **==DOK3 - Insights==** (8-12 insights) & **==DOK3 - Blueprints==** (1-8 operational guides)
5. **==Experts==** (4-8 expert profiles)
6. **==DOK2 - Knowledge Trees==**
   └── **==[Category Name]==**
       ├── **==Section Summary==** (category-level synthesis, 2-4 sentences)
       ├── **==Sources==**
       │   ├── **[Source Title] - [Author] / [Publication] ([Year])**
       │   │   ├── **==DOK2 Summary==** (4-5 sentences)
       │   │   ├── **==DOK1 Facts==** (simple bullets)
       │   │   └── Link: [URL]
```

**Key Points:**
- Build DOK1 first, then DOK2, then DOK3, then DOK4 (bottom-up progression)
- Present DOK4 first, then DOK3, then DOK2, then DOK1 (top-down presentation)
- Single BrainLift.md file containing all content

---

## DOK Display Format (CRITICAL)

### DOK1 Format: Simple Bullets Only

**Rules:**
- No "DOK1-XXX:" prefixes
- No titles before facts
- No manual numbering (1., 2., 3.)
- Simple dash bullets only
- No bold emphasis on entire fact (use bold for key terms within fact when appropriate)

### DOK2 Format: Standard Header Only

**Rules:**
- Use exactly `**==DOK2 Summary==**` as header
- No "DOK2-XXX" prefixes
- No descriptive titles after "DOK2 Summary"
- Can have multiple DOK2 summaries per source when appropriate

### DOK3 and DOK4 Format: Descriptive Titles

**DOK3 has two subsections:**

**DOK3 - Insights:**
```markdown
- **==DOK3 - Insights==**
  - **Documentation succeeds through productive incompleteness** - Whether it's SPOVs inviting disagreement or Progressive Summarisation leaving 95% at shallow layers...
  - **AI cost advantages concentrate in pattern-based review** - Privilege review shows 70-90% efficiency gains versus 30-50% for general relevance...
```

**DOK3 - Blueprints:**
```markdown
- **==DOK3 - Blueprints==**
  - **[Relevance Tag Application]** - Apply consistent relevance determinations using structured rubric
    - **Domain Context**: Federal Rule 26(b)(1), categorical tags, review platform
    - **Actions**: [Numbered steps for applying tags]
    - **Tools/Systems**: Relativity/Everlaw/DISCO, Case Summary, categorical taxonomy
    - **Judgment Boundaries**: [Where to use judgment vs. follow rules]
    - **QC/Definition of Done**: All docs tagged, <5% over-tagging rate
    - **Detailed Spec**: [Link to full tagging guide]
```

**DOK4:**
```markdown
- **==DOK4 - Spiky Points of View==**
  - **The best BrainLift documentation is embarrassingly incomplete.** Most documentation fails by trying to be comprehensive...
  - **Hot documents are found, not decided.** Most review frameworks treat hot document identification as a decision process...
```

**Rules:**
- Use descriptive bold titles (no "DOK3-XXX" or "DOK4-XXX" prefixes)
- DOK3 Insights: Title followed by dash and explanation
- DOK3 Blueprints: Title in brackets, overview, then 5 core components
- DOK4: Title as complete sentence, followed by elaboration

---

## Markdown Formatting Convention

### Section Headers: `**==TEXT==**`

Use bold + double equals for ALL structural headers:

```markdown
**==DOK4 - Spiky Points of View==**     (top-level section)
**==DOK3 - Insights==**                  (DOK3 subsection)
**==DOK3 - Blueprints==**                (DOK3 subsection)
**==Experts==**                          (top-level section)
**==DOK2 - Knowledge Trees==**           (top-level section)
**==[Category Name]==**                  (Knowledge Tree category)
**==Section Summary==**                  (category/sub-section summary)
**==Sources==**                          (source container)
**==DOK2 Summary==**                     (source-level header)
**==DOK1 Facts==**                       (source-level header)
**==Insights==**                         (optional source-level header)
```

### Regular Emphasis: `**TEXT**`

Use simple bold (no double equals) for:
- DOK3 insight titles: `**Documentation succeeds through productive incompleteness**`
- DOK3 blueprint names: `**[Relevance Tag Application]**`
- DOK3 blueprint component labels: `**Domain Context:**`, `**Actions:**`, `**Tools/Systems:**`, `**Judgment Boundaries:**`, `**QC/Definition of Done:**`, `**Detailed Spec:**`
- DOK4 SPOV titles: `**The best BrainLift documentation is embarrassingly incomplete.**`
- Inline emphasis: `**In Scope:**`, `**Out of Scope:**`
- Expert profile fields: `Who:`, `Focus:`, `Why Follow:`, `Where:`
- Source titles: `**[Title] - [Author] / [Publication] ([Year])**`

### Complete Example

```markdown
- **==DOK4 - Spiky Points of View==**
  - **The best BrainLift documentation is embarrassingly incomplete.** Most documentation fails...

- **==DOK3 - Insights==**
  - **AI cost advantages concentrate in pattern-based review** - Privilege review shows 70-90% efficiency gains...

- **==DOK3 - Blueprints==**
  - **[Hot Document Identification]** - Systematically identify case-determinative documents requiring immediate escalation
    - **Domain Context**: Review platform, case strategy, escalation protocols
    - **Actions**: [Steps for identifying and escalating hot documents]
    - **Tools/Systems**: Review platform, hot document report template
    - **Judgment Boundaries**: Strategic impact assessment uses judgment; escalation timeline follows rules
    - **QC/Definition of Done**: All hot documents escalated within 2 hours, <5% false positive rate
    - **Detailed Spec**: See /frameworks/hot-document-identification.md

- **==Experts==**
  - **Wes Kao**
    - Who: Co-founder of Maven and altMBA
    - Focus: Spiky points of view, online education
    - Why Follow: Her concept of "spiky POV" aligns with BrainLift's DOK4
    - Where: @weskao (Twitter), weskao.com

- **==DOK2 - Knowledge Trees==**
  - **==Document Review Economics==**
    - **==Section Summary==**
      - This category synthesizes research on AI cost impacts in document review...
    - **==Sources==**
      - **AI Legal Review Study - Research Team / Legal Tech Journal (2024)**
        - **==DOK2 Summary==**
          - This empirical study reveals AI document review achieves dramatic cost reductions...
        - **==DOK1 Facts==**
          - AI document review reduces per-document costs from $2-5 to $0.10-0.50
          - GPT-4 achieved F-score 0.871, matching junior lawyers at 0.860
        - Link: https://example.com
```

---

## Source Structure Rules

### Source Separation

**Create separate sources for:**
- ✅ Different URLs or publications
- ✅ Different years from same organization (e.g., "Report 2023" vs. "Report 2024")

**Do NOT separate sources for:**
- ❌ Different authors within same publication/URL
- ❌ Different chapters of same report
- ❌ Multiple contributors to same article

### Multiple DOK2s Per Source

**Use multiple DOK2 summaries when:**
- DOK1 facts naturally cluster into distinct themes (e.g., cost economics + quality metrics)
- Source yields 15+ DOK1 facts (unwieldy in single summary)
- Facts serve different application contexts within frameworks

**Use single DOK2 summary when:**
- All DOK1 facts address unified topic
- Source yields 3-8 DOK1 facts
- Facts are interconnected and cannot be cleanly separated

### Source Template

```markdown
- **[Source Title] - [Author/Organization] / [Publication] ([Year])**
  - **==DOK2 Summary==**
    - [4-5 sentence synthesis of source's key insights]
  - **==DOK1 Facts==**
    - [Simple bullet fact, 15-25 words]
    - [Another simple bullet fact, 15-25 words]
    - [Additional facts...]
  - Link: [URL]
```

**Key Points:**
- DOK2 Summary appears BEFORE DOK1 Facts
- One "Link:" line per source at end
- Source title format: `**[Title] - [Author] / [Publication] ([Year])**`

---

## DOK1 Writing Rules

### Core Requirements

**Target:** Grade 12 reading level (Flesch-Kincaid)

**Sentence Length:**
- Average: 15-25 words
- Maximum: 35 words
- Preferred: 1 sentence per DOK1 fact
- When needed: 2-3 sentences for complex concepts (40-75 words total)

**Style Guidelines:**
- Active voice (not passive)
- Common vocabulary over jargon
- Concrete examples for abstract concepts
- One idea per sentence
- Front-load key information
- Preserve exact quotes from sources

### DOK1 Patterns

**Pattern 1: Dash Connections**
```markdown
- Element interactivity determines intrinsic cognitive load - how many elements must be processed simultaneously
- The brain cannot multitask - it switches between tasks with high cognitive cost
```

**Pattern 2: Direct Statements**
```markdown
- SPOVs are your thesis about topics in your realm of expertise
- Hot documents need immediate supervisor escalation
```

**Pattern 3: Concrete Comparisons**
```markdown
- AI maintains F-score standard deviation of 0.02 versus 0.12 for human reviewers
- AI review costs $0.25 per document compared to $74 for junior lawyers
```

### Simplification Techniques

**Replace jargon:**
| ❌ Avoid | ✅ Use |
|---------|--------|
| transcend binary determinations | go beyond yes/no answers |
| multi-dimensional metadata profiles | rich document tags with multiple categories |
| case-determinative materials | documents that can change case outcomes |
| upstream design decisions | early planning choices |

**Split long sentences:**
- Before (68 words): Document review represents 70-80% of total ediscovery expenses, making it the primary cost driver in litigation and therefore the primary opportunity for strategic cost management through effective prioritization...
- After (3 sentences, 22/15/19 words): Document review represents 70-80% of total ediscovery expenses, making it the primary cost driver. This creates a major cost management opportunity. Effective prioritization can focus review efforts on materials most likely to yield critical insights.

**Front-load key information:**
- Before: The governing framework under Federal Rule 26(b)(1) establishes that discoverable information must be...
- After: Discoverable information must be "relevant to any party's claim or defense and proportional to the needs of the case" under Federal Rule 26(b)(1).

### DOK1 Examples

**Example 1 (single sentence, 22 words):**
```markdown
- Hot documents have "clear potential to impact the instant case or even an unrelated matter" and require immediate supervisor escalation
```

**Example 2 (two sentences, 23 + 19 = 42 words):**
```markdown
- AI document review costs $0.25 per document compared to $74 for junior lawyers—a 99.7% reduction. This shifts document review from labor-intensive bottleneck to scalable operation with near-zero marginal costs
```

---

## DOK2 Writing Rules

### Core Requirements

**Target:** Grade 12 reading level (Flesch-Kincaid)

**Sentence Count:** 4-5 sentences (NOT 1-2 run-on sentences)

**Sentence Length:**
- Average: 20-30 words
- Maximum: 40 words

**Function:** Synthesize connections between DOK1 facts, show "so what" (not just list facts)

**Structure:** Topic sentence → supporting points → implication

### DOK2 Template

```markdown
**==DOK2 Summary==**
  - [Sentence 1: Topic sentence introducing source's main contribution, 20-25 words]. [Sentence 2: First key finding or theme, 25-30 words]. [Sentence 3: Second key finding, 25-30 words]. [Sentence 4: Third finding or implication, 25-30 words]. [Sentence 5 (optional): "So what" or significance, 20-25 words].
```

### Common Problems and Solutions

**Problem 1: Run-on sentences**
- Before (150 words, 1 sentence): Industry-wide survey data from November 2024 reveals GenAI document review transitioning from early adopter experimentation to mainstream practice, with 48% of legal professionals currently using GenAI...
- After (5 sentences, 21 words avg): Industry-wide survey data from November 2024 shows GenAI document review transitioning from early adopter experimentation to mainstream practice. Currently 48% of legal professionals use GenAI...

**Problem 2: Listing without synthesis**
- Weak: This source discusses hot documents. Hot documents need immediate escalation. Reviewers struggle with over-identification.
- Strong: This framework establishes that hot documents go beyond simple relevance to become case-determinative materials requiring immediate escalation. The critical challenge is over-identification where reviewers flag too many documents as "hot," diluting supervisor attention.

### Synthesis Techniques

**Technique 1: Thematic Grouping**
- Group related DOK1 facts by theme
- Summarize each theme in one sentence
- Show connections between themes

**Technique 2: Cause-and-Effect Chains**
- Show how one finding leads to another
- Connect mechanisms from multiple DOK1s
- Highlight implications

**Technique 3: Contrast and Comparison**
- Highlight differences or unexpected findings
- Show trade-offs or tensions
- Explain why differences matter

### DOK2 Example

```markdown
**==DOK2 Summary==**
  - This empirical study compares AI and human document review accuracy, revealing AI matches professional competency at dramatically lower cost. GPT-4 achieved F-score 0.871, matching junior lawyers at 0.860, while completing review 77x faster. Cost per document dropped from $74 (junior lawyers) to $0.25 (GPT-4)—a 99.97% reduction. AI maintains consistent accuracy regardless of speed, breaking the human speed-quality tradeoff. This enables previously uneconomical litigation by making comprehensive review viable for mid-stakes cases.
```

---

## DOK3 Guidelines

### Overview

DOK3 contains two complementary components:

1. **DOK3 - Insights**: Contrarian patterns emerging from analyzing multiple sources together
2. **DOK3 - Blueprints**: Operational guides that translate insights into executable actions

Develop Insights first (after 4+ sources), then create Blueprints to operationalize key insights.

---

### DOK3 - Insights

#### Purpose

Cross-source synthesis showing patterns, tensions, and principles that emerge from analyzing multiple sources together.

#### Structure

```markdown
- **==DOK3 - Insights==**
  - **[Insight Title]** - [1-2 sentence statement of the insight]
  - **[Second Insight Title]** - [Statement]
  - **[Third Insight Title]** - [Statement]
  [... 8-12 total insights]
```

#### Requirements

**Count:** 8-12 insights

**Length:** 1-2 sentences per insight (20-50 words)

**Timing:** Develop after 4+ sources with DOK2 summaries complete

**Quality Criteria:**
- Requires 2+ sources (cannot be derived from single source)
- Reveals patterns readers wouldn't see from individual sources
- Actionable (provides strategic or tactical guidance)
- Often bridges domains or contexts

#### Synthesis Techniques

**Pattern Recognition:** Themes appearing across 3+ sources
- Template: "[Pattern] appears in [Source A], [Source B], and [Source C], suggesting [insight]"

**Contrast and Tension:** Where sources disagree or present trade-offs
- Template: "While [Source A] emphasizes [X], [Source B] shows [opposite], revealing [tension]"

**Cause and Effect:** Connect mechanisms from multiple sources
- Template: "[Source A's finding] explains why [Source B's observation] occurs, leading to [implication]"

**Domain Bridging:** Apply principles from one field to another
- Template: "[Principle from Field A] applies to [Context from Field B], suggesting [application]"

#### Examples

**Example 1 (Pattern Recognition):**
```markdown
- **Documentation succeeds through productive incompleteness** - Whether it's SPOVs inviting disagreement, Diátaxis separating concerns, or Progressive Summarisation leaving 95% at shallow layers, the best documentation explicitly designs for selective consumption rather than comprehensive coverage
```

**Example 2 (Cause and Effect):**
```markdown
- **Cognitive constraints drive quality** - The 2500-token BrainLift limit, working memory's 3-7 item capacity, and Progressive Summarisation's aggressive reduction all show that arbitrary limitations force the distillation that creates value
```

---

### DOK3 - Blueprints

#### Purpose

Blueprints operationalize insights by providing structured, plain-language directives that enable teams, collaborators, or AI agents to execute processes consistently. Blueprints specify "how" to act on insights in specific contexts.

#### Structure

```markdown
- **==DOK3 - Blueprints==**
  - **[Blueprint Name]** - [1-2 sentence overview]
    - **Domain Context**: [Key concepts, terms, materials this blueprint operates on]
    - **Actions**: [Step-by-step process or decision framework]
    - **Tools/Systems**: [Required tools, platforms, MCPs]
    - **Judgment Boundaries**: [Where judgment required vs. rules must be followed]
    - **QC/Definition of Done**: [Completion criteria and quality measures]
    - **Detailed Spec**: [Optional link to external detailed implementation]
  - **[Second Blueprint]** - [Overview]
    - [Components as above]
```

#### Requirements

**Count:** 1-8 blueprints (variable based on BrainLift scope)

**Overview Length:** 1-2 sentences (20-40 words)

**Component Detail:** High-level with key decision points; link to detailed specs for full implementation

**Timing:** After DOK3 insights developed and patterns need operationalization

**Quality Criteria:**
- Operationalizes DOK3 insight or DOK1/DOK2 pattern
- All 5 core components present (Domain Context, Actions, Tools/Systems, Judgment Boundaries, QC/Definition of Done)
- Actions are concrete and executable
- Judgment boundaries explicitly state rules vs. discretion
- QC provides measurable/observable criteria
- Plain language at Grade 12 reading level

#### Blueprint Types

1. **Sequential Procedures**: Step-by-step processes (e.g., UK redundancy compliance)
2. **Decision Rubrics**: Frameworks for consistent judgments (e.g., relevance tagging)
3. **Escalation Protocols**: When/how to involve supervisors
4. **Quality Frameworks**: Standards for evaluating outputs
5. **Agent Instructions**: Specifications for AI agents with tool invocations

#### Example

**Relevance Tagging Blueprint:**
```markdown
- **[Relevance Tag Application]** - Apply consistent relevance determinations using structured rubric, not ad-hoc judgment
  - **Domain Context**: Federal Rule 26(b)(1) standard, categorical tags (Issue, Custodian, Time Period), review platform
  - **Actions**:
    1. Review document against each claim/defense in Case Summary
    2. Tag "Relevant" if mentions key players, events, or timeframes in scope
    3. Apply categorical tags for all relevant documents (minimum: Issue + Custodian)
    4. Flag "Hot" if could change case strategy or contradicts witness statements
    5. Tag "Not Relevant" only if clearly outside scope
  - **Tools/Systems**: Review platform (Relativity/Everlaw/DISCO), Case Summary, categorical taxonomy, hot document form
  - **Judgment Boundaries**:
    - Use judgment: Strategic impact assessment, proportionality for marginal docs
    - Follow rules: Fed Rule 26(b)(1), categorical tags required, no quotes in hot doc reports
  - **QC/Definition of Done**: All docs have determination, relevant docs have min tags, hot docs escalated within 2h, <5% over-tagging rate
  - **Detailed Spec**: [Link to full tagging guide with claim/defense details, taxonomy, examples]
```

#### Blueprints vs. External Frameworks

**When to keep in BrainLift:** Blueprint is 1-2 paragraphs, primarily for understanding

**When to link external:** Blueprint requires multiple pages, extensive examples, frequent updates, or active daily use by team/agents

**Linking format:**
```markdown
- **[Blueprint Name]** - Overview
  - **Domain Context**: ...
  - **Actions**: ...
  - **Detailed Spec**: See /frameworks/blueprint-name.md for full implementation
```

---

## DOK4 Guidelines

### Purpose

Spiky Points of View: controversial but defensible positions that emerge from deep engagement with sources. Thesis statements you're willing to advocate for, knowing others can disagree.

### Structure

```markdown
- **==DOK4 - Spiky Points of View==**
  - **[SPOV Title in Bold]** [2-4 sentences elaborating position]. [Supporting evidence]. [Implication/call to action].
  - **[Second SPOV]** [Elaboration]. [Evidence]. [Implication].
  - **[Third SPOV]** [Elaboration]. [Evidence]. [Implication].
```

### Requirements

**Count:** 3-5 SPOVs per BrainLift (fewer better than diluted)

**Length:** 2-4 sentences each (50-100 words)

**Tone:** Confident but not arrogant

**Timing:** Develop after 5+ sources and well-developed DOK3 insights

### SPOV Quality Criteria

**Defensible but Not Universal:** Rooted in evidence but not proven facts. Reasonable people can disagree.

**Teaches Something Unexpected:** Challenges conventional wisdom or common practice.

**Requires Bravery:** You must be okay with people disagreeing. If 100% agree, it's too safe.

**Unique to You:** Emerges from your synthesis of these specific sources.

**Actionable Implication:** Should change how readers think or act.

### DOK4 Examples

**Example 1:**
```markdown
- **The best BrainLift documentation is embarrassingly incomplete.** Most documentation fails by trying to be comprehensive, but S-Class BrainLift articles should cover only 20% of possible content - the 20% that enables 80% of value creation. Just as Progressive Summarisation shows only 5% of sources reach final form, and cognitive load theory proves we can only handle 3-7 items at once, BrainLift documentation should aggressively exclude rather than include. If you're not slightly embarrassed by what you left out, you included too much.
```

**Example 2:**
```markdown
- **Confusion is a feature, not a bug.** Traditional documentation aims to eliminate all confusion, but S-Class BrainLift articles should create productive confusion at DOK boundaries. When readers hit the bright lines between DOK2 summaries and DOK3 insights, they should feel the cognitive friction of leveling up. Documentation that never confuses never transforms.
```

---

## Section Summaries

### Category-Level Section Summary

**Purpose:** Synthesize all sources within a category

**Format:**
```markdown
- **==[Category Name]==**
  - **==Section Summary==**
    - [2-4 sentence synthesis of all sources in this category]
```

**Guidelines:**
- One per Knowledge Tree category
- 2-4 sentences (50-100 words)
- Written AFTER all sources in category complete
- Appears at top of category before sources

### Sub-Section Summary (Optional)

**When to use:**
- Category has 10+ sources
- Sources naturally cluster into 2-4 sub-themes
- Additional structure adds clarity

**When to skip:**
- Category has fewer than 10 sources
- All sources address similar questions

**Format:**
```markdown
- **==[Category Name]==**
  - **==Section Summary==**
    - [Overall category synthesis]
  - **==[Sub-Section Name]==**
    - **==Section Summary==**
      - [2-3 sentence synthesis of sub-section sources]
    - **==Sources==**
      - [Source 1]
      - [Source 2]
```

---

## Experts Section

### Structure

```markdown
- **==Experts==**
  - **[Expert Name]**
    - Who: [Title, affiliation, or role - one sentence]
    - Focus: [3-5 key areas or concepts they're known for]
    - Why Follow: [Connection to THIS BrainLift specifically]
    - Where: [2-4 links: social media, website, publications]
```

### Requirements

**Count:** 4-8 experts

**Placement:** After DOK3 - Blueprints, before DOK2 Knowledge Tree

**Selection Criteria:**
- Cited in 3+ sources in your BrainLift, OR
- Created framework/methodology you're using, OR
- Their work directly inspired DOK4 SPOVs or DOK3 insights, OR
- Recognized authority in the field

### Example

```markdown
- **==Experts==**
  - **Wes Kao**
    - Who: Co-founder of Maven and altMBA, Marketing and Product Strategy Expert
    - Focus: Spiky points of view, online education, clear communication, rigorous thinking
    - Why Follow: Her concept of "spiky POV" directly aligns with BrainLift's DOK4, and she specializes in making complex ideas accessible through frameworks
    - Where: @weskao (Twitter), weskao.com, LinkedIn, Maven
```

---

## Owner(s) and Purpose

### Owner(s) Section

```markdown
- **==Owner(s)==**
  - [Name 1]
  - [Name 2] (if multiple owners)
```

**Guidelines:**
- List primary creator(s)
- Update when ownership transfers
- Keep simple - just names

### Purpose Section

```markdown
- **==Purpose==**
  - **In Scope:** [One sentence describing core focus, audience, and value]
  - **Out of Scope:** [3-5 related topics NOT covered]
```

**Guidelines:**
- In Scope: Specific about audience/use case
- Out of Scope: List related topics that might be confused with your focus
- Creates boundaries for source selection

---


## Common Mistakes to Avoid

1. **DOK Numbering in Display** - Never show "DOK1-XXX:" or "DOK2-XXX"
2. **Titled DOK1 Facts** - Use simple bullets, not "**DOK1-001: Title:** content"
3. **Wrong DOK2 Header** - Use exactly `**==DOK2 Summary==**` (not "DOK2-001 - summary")
4. **Wrong Markdown Headers** - Use `**==TEXT==**` for sections, not `**TEXT**` alone
5. **Wrong DOK3 Section Headers** - Use `**==DOK3 - Insights==**` and `**==DOK3 - Blueprints==**` (not `**==DOK3 - Cross-Source Insights==**`)
6. **Splitting Sources by Author** - One source per URL/publication, not per author
7. **Run-On DOK2 Sentences** - Use 4-5 sentences (20-30 words each), not 1-2 long sentences
8. **Exceeding Word Limits** - DOK1 max 35 words/sentence, DOK2 max 40 words/sentence
9. **Listing vs. Synthesizing** - DOK2 should show connections, not just list DOK1 facts
10. **Splitting BrainLift File** - Keep as single BrainLift.md file
11. **Developing DOK3 Too Early** - Wait until 4+ sources complete for Insights
12. **Developing DOK4 Too Early** - Wait until 5+ sources with strong DOK3 Insights
13. **Missing Blueprint Components** - All 5 core components required (Domain Context, Actions, Tools/Systems, Judgment Boundaries, QC/Definition of Done)
14. **Creating Blueprints Without Insights** - Develop DOK3 Insights first, then Blueprints to operationalize them
15. **Using "Category Summary"** - Correct term is "Section Summary"
16. **Passive Voice** - Prefer active voice in DOK1 and DOK2
17. **Omitting Section Summary** - Every category needs Section Summary at top

---

**Document Version:** 1.1
**Last Updated:** 2025-11-01
**Created:** 2025-10-30
**Purpose:** LLM-optimized reference derived from comprehensive brainlift-methodology.md
**Changelog:**
- v1.1 (2025-11-01): Added DOK3 - Blueprints guidelines. Restructured DOK3 section to include both Insights and Blueprints subsections with structure, requirements, examples, and quality criteria.
- v1.0 (2025-10-30): Initial version with DOK1-DOK4 guidelines, formatting conventions, and common mistakes.
