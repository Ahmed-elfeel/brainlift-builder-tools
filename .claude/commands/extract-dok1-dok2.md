# Extract DOK1 and DOK2

You are tasked with extracting DOK1 facts and DOK2 summaries from a user-selected source in a BrainLift document. You will read the source content, extract atomic knowledge units (DOK1) and create synthesized summaries (DOK2) following the exact formatting and style rules from brainlift-methodology.md.

## Usage

```
/extract-dok1-dok2
```

This command has no parameters. It will guide you through an interactive process to select a source and extract its DOK1/DOK2 content.

## Process

When this command is invoked, follow these steps:

### Step 1: BrainLift File Selection

1. **Check brainlift/ folder** for markdown files:
   - Use: `ls brainlift/*.md`

2. **Auto-select or prompt**:
   - **If exactly 1 file**: Auto-select and proceed with that file
   - **If multiple files**: Show numbered list and ask user to select
   - **If no files**: Show error message with guidance

**Example prompt for multiple files**:
```
I found multiple BrainLift files in your brainlift/ folder:

1. ai-agents-brainlift.md
2. document-review-brainlift.md
3. knowledge-management-brainlift.md

Which BrainLift would you like to work with? (Enter number)
```

### Step 2: Parse and Present Source List

1. **Read the selected BrainLift file** completely

2. **Parse the Knowledge Tree** to find all sources:
   - Look for source entries: `- **[Title] - [Author] / [Publication] ([Year])**`
   - Identify DOK2 Summary and DOK1 Facts sections under each source
   - Check for placeholder text vs. actual content

3. **Categorize sources**:
   - **Incomplete (○)**: Contains placeholder text like:
     - `[Placeholder: Extract atomic knowledge units...]`
     - `[Placeholder: Write 4-5 sentences...]`
     - `[Placeholder: After reading...]`
   - **Complete (✓)**: Contains actual DOK1 facts and DOK2 summaries

4. **Present numbered list with status indicators**:
   - List incomplete sources FIRST (○)
   - Then list complete sources (✓)
   - Format: `[number] [status] [Source Title - Author]`

**Example output**:
```
I found 8 sources in ai-agents-brainlift.md:

INCOMPLETE SOURCES (missing DOK1/DOK2):
1. ○ Building Effective AI Agents - Smith & Johnson / AI Review (2024)
2. ○ Agent Orchestration Patterns - Chen / Tech Blog (2024)
3. ○ Multi-Agent Systems - Davis et al. / ACM (2023)

COMPLETE SOURCES:
4. ✓ Introduction to AI Agents - Williams / Medium (2024)
5. ✓ Agent Communication Protocols - Garcia / ArXiv (2024)
6. ✓ Autonomous Systems Design - Thompson / IEEE (2023)
7. ✓ Agent Architecture Patterns - Lee / O'Reilly (2024)
8. ✓ Practical Agent Development - Martinez / Dev.to (2024)

Which source would you like to extract DOK1 and DOK2 from? (Enter number)
```

### Step 3: Source Selection

Wait for user to enter a number, then:

1. **Validate selection**: Ensure number is valid
2. **Identify the source**:
   - Extract source title, author, publication, year
   - Extract source URL from the "Link:" line
3. **Confirm selection**:

```
You selected: [Source Title - Author / Publication (Year)]
Link: [URL]

I'll now read this source and extract DOK1 facts and DOK2 summary. This may take a moment...
```

### Step 4: Extract DOK1 and DOK2 Content

1. **Use WebFetch to read the source URL**:
   - Fetch complete content from the URL
   - If URL is inaccessible, inform user and ask if they want to provide content another way

2. **Extract DOK1 facts** following these rules:

**DOK1 RULES (from brainlift-methodology.md):**
- Simple bullet points (no numbering, no titles, no "DOK1-XXX:")
- **Preferred**: 1 sentence (15-25 words)
- **Complex concepts**: 2-3 sentences (40-75 words total)
- **Max per sentence**: 35 words
- **Reading level**: Grade 12
- **Style**: Active voice, concrete examples, one idea per sentence
- Preserve exact quotes from source

**DOK1 STYLE EXAMPLES:**
```markdown
- Hot documents have "clear potential to impact the instant case or even an unrelated matter" and require immediate supervisor escalation
- AI review costs $0.25 per document compared to $74 for junior lawyers—a 99.7% reduction
- Human reviewers face a speed-accuracy tradeoff: faster review (40-50 docs/hour) reduces accuracy, while careful review (1-2 docs/hour) improves precision. LLMs maintain consistent accuracy at any speed
```

**TARGET QUANTITY**: Extract 6-15 DOK1 facts (varies by source depth)

3. **Create DOK2 summary** following these rules:

**DOK2 RULES (from brainlift-methodology.md):**
- Header: Exactly `**==DOK2 Summary==**` (no numbering, no descriptive titles)
- **Sentence count**: 4-5 sentences (NOT 1-2 run-on sentences)
- **Total length**: 80-150 words
- **Sentence length**: 20-30 words average, 40 max
- **Reading level**: Grade 12
- **Focus**: Show connections between DOK1 facts (synthesis, not list)
- **Include**: "so what" or significance of findings
- **Structure**: Topic sentence → supporting points → implication

**DOK2 STYLE EXAMPLE (96 words, 5 sentences):**
```markdown
**==DOK2 Summary==**
  - This empirical study provides the first rigorous comparison of GPT-4 and Claude performance against human lawyers on document review tasks. GPT-4-1106 achieves professional-grade accuracy (F-score 0.871), matching junior lawyers (0.860) and LPO practitioners (0.874), while completing review 77-276x faster at 99.97% lower cost ($0.25 vs. $74.26). A critical finding: model version selection matters more than simply "using AI" given substantial performance variance between versions. LLMs maintain consistent accuracy regardless of speed, decoupling the speed-quality tradeoff that constrains human review. This makes comprehensive document review financially viable for mid-stakes cases that previously couldn't support traditional review costs.
```

4. **Determine if source-level Insights are needed**:
   - **If 8+ DOK1 facts**: Consider adding 2-4 source-level insights
   - **If fewer than 8**: Skip source-level insights
   - Source-level insights connect 2+ DOK1s from THE SAME source

### Step 5: Present Extracted Content for Approval

Present the extracted content to the user:

```
I've extracted DOK1 facts and DOK2 summary from: [Source Title]

**==DOK2 Summary==**
  - [Your 4-5 sentence synthesis, 80-150 words total]
**==DOK1 Facts==**
  - [First DOK1 fact, 15-25 words]
  - [Second DOK1 fact]
  - [Third DOK1 fact]
  - [Continue with remaining DOK1 facts...]

[If 8+ facts, optionally include:]
**==Insights==**
  - [Source-level insight 1]
  - [Source-level insight 2]

---

**Quality Check:**
- DOK1 count: [X] facts
- DOK2 length: [Y] words, [Z] sentences
- Reading level: Grade 12 target
- All formatting complies with brainlift-methodology.md

Does this accurately capture the source? Any adjustments needed?
```

### Step 6: Iterate on Feedback

If user requests changes:
- Adjust DOK1 facts or DOK2 summary based on feedback
- Re-present for approval
- Continue until user approves

### Step 7: Update BrainLift File

Once content is approved:

1. **Locate the source section** in the BrainLift file
2. **Replace placeholder text** with extracted content:
   - Replace DOK2 Summary placeholder with actual summary
   - Replace DOK1 Facts placeholder with actual facts
   - Add Insights section if applicable
3. **Preserve all other content**:
   - Keep source title and metadata
   - Keep "Link:" line
   - Maintain exact BrainLift formatting
4. **Use Edit tool** to make the replacement

**Important**: DOK2 Summary must appear BEFORE DOK1 Facts in the file structure.

### Step 7.5: QC - Remove Empty Lines

After updating the BrainLift file with extracted content, run a quality check to ensure Workflowy compatibility:

1. **Run QC command** to remove all empty lines from the entire file:
   - Use Bash tool with the following command:
   ```bash
   grep -v '^$' brainlift/[filename].md > brainlift/[filename].tmp && mv brainlift/[filename].tmp brainlift/[filename].md
   ```
   - Replace `[filename]` with the actual BrainLift filename
   - This ensures no empty lines exist anywhere in the file

2. **Verify operation**:
   - Confirm file was updated successfully
   - Check that all content is preserved (only empty lines removed)
   - Verify DOK2 appears immediately before DOK1 with no spacing

**Why this matters:** Workflowy requires no empty lines for proper copy/paste functionality. Empty lines between DOK1 facts or between DOK2/DOK1 sections break Workflowy's indent-based hierarchy.

**Critical Check:**
- No empty lines between individual DOK1 facts
- No empty line between DOK2 Summary and DOK1 Facts headers
- No empty lines anywhere in the source entry

### Step 8: Confirm Update and Offer Continuation

After updating the file:

```
✓ Successfully updated: [Source Title]

Updated source structure:
- DOK2 Summary: [X] words, [Y] sentences ✓
- DOK1 Facts: [Z] facts ✓
[- Source-level Insights: [N] insights ✓ (if applicable)]
- Format: Workflowy-compatible (no empty lines) ✓

---

Remaining sources in [brainlift-file.md]:
- Incomplete: [X] sources
- Complete: [Y] sources
- Format: Workflowy-compatible (no empty lines)

Would you like to extract DOK1/DOK2 from another source? (yes/no)
```

If user says **yes**:
- Return to Step 2 (present updated source list)
- Continue the loop

If user says **no**:
- End with completion message

**Completion message**:
```
Great work! You've successfully extracted DOK1/DOK2 content.

**Summary:**
- Total sources processed this session: [X]
- BrainLift file: brainlift/[filename].md
- Remaining incomplete sources: [Y]

Next steps:
- Continue extracting from remaining sources when ready (run /extract-dok1-dok2 again)
- Once you have 4+ sources complete, consider developing DOK3 Insights
- After 5+ sources with strong patterns, draft DOK4 Spiky Points of View
```

## Important Guidelines

### 1. Formatting Compliance (CRITICAL)

**DOK1 Format:**
- ✅ Simple bullets: `- [Fact]`
- ❌ NO numbering: `- DOK1-001: [Fact]`
- ❌ NO titles: `- **Cost Reduction:** [Fact]`
- ❌ NO manual numbering: `1. [Fact]`

**DOK2 Format:**
- ✅ Exact header: `**==DOK2 Summary==**`
- ❌ NO numbering: `**==DOK2-001 Summary==**`
- ❌ NO descriptive titles: `**==DOK2 Summary - Cost Analysis==**`

**Content Quality:**
- DOK1: 15-25 words per sentence (max 35)
- DOK2: 4-5 sentences, 80-150 words total, 20-30 words per sentence (max 40)
- Both: Grade 12 reading level, active voice, concrete examples

**Workflowy Compatibility:**
- No empty lines between DOK1 facts
- No empty line between DOK2 Summary and DOK1 Facts headers
- All content flows continuously with only indentation for structure

### 2. Synthesis vs. Listing

**DOK2 must synthesize**, not just list:

**❌ Weak (just listing):**
> This source discusses hot documents. Hot documents need escalation. Reviewers struggle with over-identification. Reports should avoid quotes.

**✅ Strong (synthesizing):**
> This framework establishes that hot documents go beyond simple relevance to become case-determinative materials requiring immediate escalation. The critical challenge is over-identification where reviewers flag too many documents as "hot," diluting supervisor attention. A disciplined reporting format (identifier, date, parties, brief explanation—no quotes) forces objective flagging while preventing bias. This calibrated approach ensures truly strategic materials get proper attention.

### 3. Source Accessibility

If WebFetch cannot access the URL:
- Inform user immediately
- Offer alternatives:
  - User can paste content directly
  - User can provide alternative URL
  - User can skip this source for now

### 4. Quality Checks Before Updating File

Before using Edit tool, verify:
- [ ] DOK2 is 4-5 sentences (not 1-2 run-ons)
- [ ] DOK2 is 80-150 words total
- [ ] DOK2 shows synthesis and "so what"
- [ ] DOK1 facts use simple bullets (no numbering)
- [ ] DOK1 sentences are 15-25 words (max 35)
- [ ] All content is Grade 12 reading level
- [ ] Exact quotes from source are preserved
- [ ] Active voice used where possible
- [ ] No empty lines between DOK1 facts
- [ ] No empty line between DOK2 Summary and DOK1 Facts

### 5. Handling Multiple DOK2 Summaries

Most sources have 1 DOK2 summary. Create multiple DOK2s only when:
- Source yields 15+ DOK1 facts (unwieldy in single summary)
- DOK1 facts naturally cluster into distinct themes
- Facts serve different application contexts

If creating multiple DOK2s, structure as:
```markdown
- **[Source Title] - Author / Publication (Year)**
  - **==DOK2 Summary==**
    - [First thematic summary, 4-5 sentences]
  - **==DOK1 Facts==**
    - [Facts for first theme]
  - **==DOK2 Summary==**
    - [Second thematic summary, 4-5 sentences]
  - **==DOK1 Facts==**
    - [Facts for second theme]
  - Link: [URL]
```

### 6. Preserving Accuracy

**Critical Rules:**
- Preserve ALL quoted material exactly as in source
- Maintain factual precision (don't round numbers or generalize data)
- Keep technical terms when necessary (some have no simpler equivalent)
- Don't oversimplify complexity (use multiple sentences if needed)

### 7. Plain Language Techniques

**Simplification strategies:**
- Replace jargon: "transcend binary determinations" → "go beyond yes/no answers"
- Split long sentences: 68 words → three 20-word sentences
- Use concrete examples: abstract concepts → specific instances
- Front-load key info: put main point first, details second
- Active voice: "Reviewers should tag..." not "Tags should be applied..."

### 8. Interactive Workflow

- **One source at a time**: Complete extraction, get approval, update file
- **Clear progress indicators**: Show remaining incomplete sources after each update
- **Allow iteration**: User can request adjustments before file update
- **Continuation loop**: Process multiple sources in one session if desired

### 9. Workflowy Compatibility

**No Empty Lines**: Extracted DOK1 and DOK2 content must have NO empty or spacer lines for Workflowy compatibility.

**Why This Matters**:
- Workflowy uses indent-based hierarchy, not empty lines
- Empty lines between DOK1 facts break list structure during import
- Empty lines between DOK2 and DOK1 sections disrupt parent-child relationships
- Continuous lines with proper indentation maintain structure

**QC Process**:
- Step 5 presentation template contains no empty lines by design
- DOK1 facts are listed consecutively (no spacing between facts)
- DOK2 Summary and DOK1 Facts headers are consecutive (no empty line between)
- Step 7.5 runs global QC to clean entire file after extraction
- Command: `grep -v '^$'` filters out all empty lines

**Manual Verification** (if needed):
- Open BrainLift file and check the updated source entry
- Look for empty lines between individual DOK1 facts
- Check for empty line between DOK2 Summary and DOK1 Facts
- Run: `grep -c '^$' brainlift/[filename].md` (should return 0)
- If empty lines found, re-run QC command from Step 7.5

**Important**: The QC step cleans the entire BrainLift file, not just the updated source. This ensures consistency across all sources.

## Success Criteria

The command is successful when:

1. ✓ User selects a source from the BrainLift file
2. ✓ Source content is successfully fetched (via WebFetch or user-provided)
3. ✓ DOK1 facts extracted following all formatting rules
4. ✓ DOK2 summary created with proper synthesis and structure
5. ✓ User approves the extracted content
6. ✓ BrainLift file updated with correct formatting
7. ✓ All formatting complies with brainlift-methodology.md
8. ✓ Post-update QC confirms no empty lines (Workflowy compatible)
9. ✓ User knows status (remaining incomplete sources) and next steps

## Example Interaction Flow

This shows the complete workflow from command invocation to file update:

```
User: /extract-dok1-dok2