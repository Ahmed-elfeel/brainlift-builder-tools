# BrainLift Builder - User Guide

Welcome! This toolkit provides Claude Code commands to help you build **BrainLifts** - structured knowledge documents that organize research using a hierarchical "Depth of Knowledge" (DOK) system.

**What is a BrainLift?** A progressive disclosure document where knowledge is built bottom-up (from atomic facts to insights) but presented top-down (conclusions first, evidence deeper). Think of it as an inverted pyramid of knowledge optimized for WorkFlowy.

**What this toolkit does:** Provides interactive commands that guide you through creating, expanding, and refining BrainLifts with automated quality checking and WorkFlowy compatibility.

> 📚 **Want to understand the theory?** See [`docs/guides/brainlift-methodology.md`](docs/guides/brainlift-methodology.md) for the complete methodology, structure rules, and DOK explanations.

---

## Prerequisites

- **Claude Code** installed and configured
- **Basic understanding** of what a BrainLift is (see methodology doc)
- *Optional:* WorkFlowy account (for using the final output)

---

## Quick Start: Your First BrainLift

Let's create your first BrainLift in about 10 minutes:

### 1. Start the creation command

```bash
/new_brainlift
```

### 2. Answer the interactive questions

The command will ask you (one at a time):
- **Your topic** (what are you researching?)
- **Why it interests you** (your motivation)
- **Your key question** (what do you want to answer?)
- **Purpose boundaries** (what's in scope vs. out of scope?)

### 3. Review the research

The command will automatically:
- Find 5 relevant experts in your field
- Find 3 diverse articles addressing your question
- Show you what it found and ask for approval

### 4. Get your BrainLift file

When you approve, the command creates:
```
brainlift/[your-topic]-brainlift.md
```

This file has the complete structure with:
- ✅ Your Purpose and Owner defined
- ✅ 5 experts populated with details
- ✅ 3 source entries with placeholders
- ✅ Structure for DOK3, DOK4 (to fill later)
- ✅ WorkFlowy-compatible formatting (no empty lines)

### 5. What's next?

You now have a foundation. Next steps:
1. Add more sources with `/new-sources`
2. Extract facts and summaries with `/extract-dok1-dok2`
3. Create insights with `/new-dok3`

---

## The BrainLift Building Workflow

Here's the recommended sequence for building a robust BrainLift:

```
┌─────────────────────────────────────────────────────────┐
│ PHASE 1: FOUNDATION                                     │
│ Command: /new_brainlift                                 │
│ Output: BrainLift file with 3 source placeholders      │
└────────────────────┬────────────────────────────────────┘
                     │
                     ▼
┌─────────────────────────────────────────────────────────┐
│ PHASE 2: RESEARCH EXPANSION                             │
│ Command: /new-sources (repeat 2-4 times)                │
│ Goal: Build to 8-15 diverse sources                    │
│ Output: More source entries with placeholders          │
└────────────────────┬────────────────────────────────────┘
                     │
                     ▼
┌─────────────────────────────────────────────────────────┐
│ PHASE 3: KNOWLEDGE EXTRACTION                           │
│ Command: /extract-dok1-dok2 (repeat for each source)   │
│ Goal: Extract facts and summaries from all sources     │
│ Output: DOK1 facts and DOK2 summaries added            │
└────────────────────┬────────────────────────────────────┘
                     │
                     ▼
┌─────────────────────────────────────────────────────────┐
│ PHASE 4: SYNTHESIS                                      │
│ Command: /new-dok3 (run 2-3 times)                      │
│ Goal: Identify 8-12 cross-source insights              │
│ Output: DOK3 - Insights section populated              │
└────────────────────┬────────────────────────────────────┘
                     │
                     ▼
┌─────────────────────────────────────────────────────────┐
│ PHASE 5: ADVANCED (Optional, Manual)                    │
│ - Create DOK3 Blueprints (operational guides)          │
│ - Create DOK4 SPOVs (controversial opinions)           │
│ - Update Section Summaries                             │
└─────────────────────────────────────────────────────────┘
```

### Decision Points

**When to move from Phase 2 to Phase 3?**
- You have at least 5-8 sources
- Sources represent diverse perspectives
- You're ready to start deep reading

**When to move from Phase 3 to Phase 4?**
- At least 4 sources have complete DOK2 summaries
- You've extracted facts from your core sources
- You're seeing patterns across sources

**When to tackle Phase 5?**
- You have 8-12 DOK3 Insights
- You have strong opinions forming
- You want to operationalize your insights

---

## Command Guide

### `/new_brainlift` - Create Your BrainLift

**When to use:** Starting a new research topic

**What it does:**
1. Asks you about your topic, motivation, and key question
2. Helps you define Purpose (In Scope / Out of Scope)
3. Researches 5 experts relevant to your topic
4. Finds 3 diverse articles addressing your question
5. Creates `brainlift/[topic]-brainlift.md` with complete structure
6. Runs quality check for WorkFlowy compatibility

**What you'll provide:**
- Topic name
- Why it interests you
- Key question to explore
- What's in scope / out of scope

**What you'll get:**
- Complete BrainLift file structure
- 5 experts with credentials and links
- 3 sources with placeholders for DOK1/DOK2
- Ready for expansion

**Tips:**
- Be specific with your Purpose (narrow is better than broad)
- Define clear boundaries (Out of Scope is as important as In Scope)
- Review the articles before approving - diversity matters
- You can request different experts or articles if needed

---

### `/new-sources` - Add Research Sources

**When to use:** After initial BrainLift exists, whenever you want to expand research

**What it does:**
1. Finds your BrainLift file automatically
2. Reads your Purpose to understand context
3. Asks for a key question to explore
4. Researches 3-5 sources with diverse perspectives
5. Lets you select which sources to add
6. Suggests where to place them (category)
7. Inserts source structure with placeholders

**What you'll provide:**
- Key question for this research round
- Which sources to add (from list shown)
- Category placement approval

**What you'll get:**
- New source entries in your Knowledge Tree
- Placeholders for DOK1 facts and DOK2 summaries
- Organized into appropriate categories

**Tips:**
- Run this 2-4 times to build up 8-15 sources
- Frame specific questions each time (not just "tell me more")
- Look for diverse perspectives, not echo chambers
- Let the command suggest categories - it reads your existing structure
- You can specify a different category if the suggestion doesn't fit

**Example workflow:**
```
Round 1: "What are the cost economics of AI document review?"
Round 2: "What are the accuracy concerns with AI review?"
Round 3: "What implementation challenges do teams face?"
Round 4: "What do critics say about AI review?"
```

---

### `/extract-dok1-dok2` - Extract Facts and Summaries

**When to use:** After adding sources (3+ sources with placeholder content)

**What it does:**
1. Lists all your sources (prioritizes those without DOK1/DOK2)
2. You select which source to process
3. Fetches the actual source content from its URL
4. Generates DOK1 facts and DOK2 summary
5. **Validates** against the original source (prevents fabrication)
6. Checks quality (word counts, format, reading level)
7. Shows you a preview before inserting
8. Runs WorkFlowy QC after insertion
9. Offers to continue with another source

**What you'll provide:**
- Which source to extract (select from list)
- Approval of extracted content

**What you'll get:**
- DOK1 facts: Simple bullet points (15-25 words each)
- DOK2 summary: 4-5 sentences (80-150 words total)
- Key threads: How facts connect to your Purpose

**Tips:**
- Process 1-3 sources per session (it's deep work)
- Source URLs must be accessible (public articles work best)
- Review the preview carefully - you can request edits
- The command validates against the source to prevent errors
- You can process sources in any order (command shows incomplete ones first)
- This is the most time-intensive step - extraction is careful work

**What gets validated:**
- ✅ All facts are actually in the source
- ✅ Quotes are exact
- ✅ Numbers haven't been changed
- ✅ Word counts meet limits
- ✅ Format is correct

---

### `/new-dok3` - Create Cross-Source Insights

**When to use:** After 4+ sources have DOK2 summaries complete

**What it does:**
1. Counts how many DOK3 Insights you have (target: 8-12)
2. Validates you have enough sources (4+ minimum)
3. Analyzes ALL your DOK2 summaries and DOK1 facts
4. Identifies patterns requiring multiple sources
5. Proposes 3-5 candidate insights with rationale
6. Shows which sources support each insight
7. Lets you select which insights to add
8. Offers to continue (can run multiple times)

**What you'll provide:**
- Which insights to add (from proposed list)
- Approval to continue or finish

**What you'll get:**
- DOK3 Insights in format: **[Title]** - [Statement]
- Each insight 1-2 sentences (20-50 words)
- Progressive build toward 8-12 total insights

**Tips:**
- Wait until you have 4+ sources with DOK2 (patterns need multiple sources)
- Run this 2-3 times rather than trying to get all insights at once
- Review the rationale - each insight should cite 2+ sources
- Look for insights that are non-obvious (not just summarizing one source)
- Target 8-12 total insights for a mature BrainLift
- Each time you run it, the command knows what insights already exist

**What makes a good DOK3 Insight?**
- Requires 2+ sources to derive
- Reveals pattern you wouldn't see from one source alone
- Actionable (provides strategic or tactical guidance)
- Contrarian or surprising (not obvious)

---

## Workflow Tips & Best Practices

### Building Incrementally

**Don't try to do everything at once.** The workflow is designed to be iterative:

- **Sources:** Add 3-5 at a time, extract, then add more
- **Extraction:** Process 1-3 sources per session (deep focus work)
- **Insights:** Run `/new-dok3` multiple times as understanding deepens

### Quality Over Quantity

**Focus on diverse, high-quality sources:**
- Better to have 8 excellent sources than 20 mediocre ones
- Seek different perspectives, not confirmation
- Academic, industry, practitioner, and critical voices all valuable

### Let Commands Guide You

**Commands have intelligence built in:**
- They suggest categories based on your existing structure
- They prioritize incomplete sources first
- They validate quality automatically
- They handle WorkFlowy compatibility (you don't need to think about formatting)

### When to Extract

**Two approaches work well:**

**Approach 1: Batch sources, then extract**
- Add 5-8 sources with `/new-sources`
- Then extract all with `/extract-dok1-dok2`
- Good if you know your sources in advance

**Approach 2: Add and extract iteratively**
- Add 2-3 sources
- Extract them immediately
- See what's missing, add more sources
- Good for exploratory research

### What Commands Don't Do (Manual Work)

The commands handle DOK1, DOK2, and DOK3 Insights. You'll manually create:

- **DOK3 - Blueprints:** Operational guides with 5 components (see methodology)
- **DOK4 - SPOVs:** Controversial but defensible opinions (3-5 total)
- **Section Summaries:** Category-level synthesis after sources are complete

These require human judgment and synthesis beyond what commands automate.

---

## Common Questions & Troubleshooting

### "Command can't find my BrainLift file"

**Check:** Do you have a `.md` file in the `brainlift/` folder?

Commands look for files matching `brainlift/*-brainlift.md`. If you renamed or moved it, commands won't find it.

### "Source URL is not accessible"

**Solution:** Some sources require authentication or block automated access.

- Try a different source
- Look for publicly accessible versions
- Consider sources from open access journals, blogs, company websites

### "Not enough sources for DOK3"

**Solution:** You need at least 4 sources with completed DOK2 summaries.

Run `/extract-dok1-dok2` on more sources first, then return to `/new-dok3`.

### "I want to add sources to a specific category"

**How it works:** `/new-sources` suggests a category, but you can specify different.

When prompted "Do you agree with this placement?", answer "specify-different" and provide your category name.

### "Empty lines are breaking my WorkFlowy import"

**Don't worry:** All commands automatically remove empty lines (QC step).

You'll see a confirmation: "✅ WorkFlowy Compatibility Check: PASSED"

If you manually edited the file, run any command again and it will fix formatting.

### "I want to revise an existing DOK2 summary"

**How:** Use `/extract-dok1-dok2` again on the same source.

The command will detect existing content and ask if you want to regenerate it.

### "Can I run commands in a different order?"

**Generally yes, but:**
- `/new_brainlift` must be first (creates the file)
- `/new-dok3` requires 4+ sources with DOK2 summaries
- `/extract-dok1-dok2` requires sources to exist

Otherwise, you can iterate freely.

---

## Project Structure

```
.
├── README.md                          # You are here
├── brainlift/                         # Your BrainLift files live here
│   └── [topic]-brainlift.md          # Created by /new_brainlift
├── docs/
│   └── guides/
│       ├── brainlift-methodology.md  # Complete theory and structure
│       └── LLM-brainlift-guide.md    # Operational reference for LLMs
└── .claude/
    └── commands/                      # Command implementations
        ├── new_brainlift.md          # Create BrainLift
        ├── new-sources.md            # Add sources
        ├── extract-dok1-dok2.md      # Extract facts/summaries
        └── new-dok3.md               # Create insights
```

---

## Further Reading

### Understanding BrainLift Methodology
📚 [`docs/guides/brainlift-methodology.md`](docs/guides/brainlift-methodology.md)
- Complete explanation of DOK1, DOK2, DOK3, DOK4
- Writing guidelines and quality standards
- Structure rules and formatting conventions
- Examples and checklists

### Quick Operational Reference
📖 [`docs/guides/LLM-brainlift-guide.md`](docs/guides/LLM-brainlift-guide.md)
- Concise reference optimized for quick lookup
- DOK rules and word limits
- Common patterns and edge cases

### Detailed Command Documentation
🔧 See individual command files in `.claude/commands/`
- Each command file shows step-by-step process
- Includes validation criteria
- Shows what tools are used and when

---

## Getting Help

**Questions about methodology?**
→ See `docs/guides/brainlift-methodology.md`

**Questions about commands?**
→ See `.claude/commands/[command-name].md`

**Issues or bugs?**
→ Check troubleshooting section above

---

## Ready to Start?

Let's build your first BrainLift:

```bash
/new_brainlift
```

The command will guide you through the rest. Good luck! 🚀
