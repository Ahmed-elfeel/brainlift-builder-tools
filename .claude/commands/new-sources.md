# New Sources

You are tasked with finding and adding new sources to an existing BrainLift document. You will research sources based on a user-provided key question, present them for review, allow the user to select which sources to add, suggest appropriate placement in the Knowledge Tree, and insert them with proper placeholder formatting.

## Usage

```
/new-sources
```

This command has no parameters. It will guide you through an interactive process to add sources to your BrainLift.

## Process

When this command is invoked, follow these steps:

### Step 1: BrainLift File Selection

1. **Check brainlift/ folder** for markdown files:
   - Use: `ls brainlift/*.md`

2. **Auto-select or prompt**:
   - **If exactly 1 file**: Auto-select and proceed with that file
   - **If multiple files**: Show numbered list and ask user to select
   - **If no files**: Show error message

**Example prompt for multiple files**:
```
I found multiple BrainLift files in your brainlift/ folder:

1. ai-agents-brainlift.md
2. document-review-brainlift.md
3. knowledge-management-brainlift.md

Which BrainLift would you like to add sources to? (Enter number)
```

**If no files exist**:
```
I didn't find any BrainLift files in the brainlift/ folder.

Would you like to create a new BrainLift first? Run /new-brainlift to get started.
```

### Step 2: Key Question Prompt

Ask the user for the key question these sources should answer:

```
What key question do you want these new sources to answer?

Example: "How should enterprises architect agent orchestration to balance autonomy with coordination?"

This will guide the source research to find articles with relevant perspectives.
```

Wait for user response and store the key question.

### Step 3: Source Quantity Prompt

Ask how many sources to find:

```
How many sources would you like me to find? (Enter a number from 1 to 5)

Recommendation: 3 sources provides good diversity without being overwhelming.
```

**Validation**:
- Accept numbers 1-5
- If invalid input, default to 3 and inform user: "I'll search for 3 sources."

### Step 4: Research Sources

Use WebSearch to find the requested number of sources. Search strategically:

**Search Strategies**:
1. Search for the exact key question: "[key question]"
2. Search for recent content: "[key question] 2024" or "[key question] 2025"
3. Look for diverse viewpoints and perspectives
4. Prioritize:
   - Articles with specific viewpoints or opinions
   - Different sources (academic, industry, blog posts, research papers)
   - Recent content (2024-2025 preferred)
   - Actual URLs that are accessible

**For Each Source Found, Gather**:
- **Title**: Full article title
- **Author/Organization**: Who wrote it
- **Publication**: Where it was published
- **Year**: Publication year
- **URL**: Direct link
- **Perspective**: Brief 1-2 sentence description of the stance or viewpoint

### Step 5: Present Sources for Review

Present your findings:

```
I've found [N] sources addressing "[key question]":

1. **[Article Title] - [Author] / [Publication] ([Year])**
   - Perspective: [Brief description of the source's stance or main argument]
   - Link: [URL]

2. **[Article Title] - [Author] / [Publication] ([Year])**
   - Perspective: [Description]
   - Link: [URL]

3. **[Article Title] - [Author] / [Publication] ([Year])**
   - Perspective: [Description]
   - Link: [URL]

[Continue for all requested sources...]

Do these sources provide good perspectives on your key question?
```

### Step 6: Approval and Iteration

Wait for user response:

**If user approves**: Proceed to Step 7

**If user wants changes**: Ask what to adjust:
```
What would you like me to adjust?
- Different perspectives or viewpoints?
- More recent sources?
- Different publication types (academic vs. industry)?
- Different key aspects to explore?
```

Then search again with adjusted criteria and re-present sources.

### Step 7: Source Selection (Iterative Loop)

Present the numbered list of available sources:

```
Which source would you like to add to your BrainLift?

Available sources:
1. [Source 1 Title - Author]
2. [Source 2 Title - Author]
3. [Source 3 Title - Author]

Enter the number of the source to add, or type 'done' if you're finished:
```

**User selects a source by number**

### Step 8: Parse Knowledge Tree Structure

1. **Read the selected BrainLift file** completely

2. **Parse the Knowledge Tree**:
   - Identify all existing categories (sections with `**==[Category Name]==**`)
   - Extract category names and count sources in each
   - Understand themes/topics of each category based on:
     - Category name
     - Existing source titles in that category
     - Section summary content (if not placeholder)

3. **Analyze selected source**:
   - Extract key themes/topics from the source title
   - Identify which existing category best matches
   - Determine if a new category would be more appropriate

### Step 9: Suggest Category Placement

Present placement options with a smart recommendation:

```
Where would you like to add: [Source Title - Author]

EXISTING CATEGORIES:
1. **[Category Name 1]** - [Brief theme description] ([X] sources)
2. **[Category Name 2]** - [Brief theme description] ([Y] sources)
3. **[Category Name 3]** - [Brief theme description] ([Z] sources)

NEW CATEGORY:
[N]. Create new category (you'll specify the name)

RECOMMENDED: Option [#] - [Reason why this category fits best based on source theme]

Enter number to select placement:
```

**Recommendation Logic**:
- Match source theme/keywords to existing category themes
- Consider category balance (don't overfill one category)
- Recommend new category if no good thematic fit
- Explain reasoning clearly

**Example**:
```
RECOMMENDED: Option 2 - This source discusses orchestration patterns, which aligns with the "Agent Coordination" theme in this category (currently 4 sources).
```

### Step 10: Handle Placement Selection

**If user selects existing category**:
1. Proceed to Step 11 to format and insert source

**If user selects "Create new category"**:
1. Ask for category name:
```
What would you like to name this new category?

Example category names:
- "AI Agent Economics"
- "Multi-Agent Communication Protocols"
- "Agent Safety and Reliability"

Category name:
```

2. Wait for user input
3. Proceed to Step 11 to format and insert source in new category

### Step 11: Format Source Entry

Create the source entry with proper placeholders following brainlift-methodology.md:

```markdown
- **[Source Title] - [Author/Organization] / [Publication] ([Year])**
  - **==DOK2 Summary==**
    - [Placeholder: Write 4-5 sentences (80-150 words total) synthesizing the main argument, evidence, and implications from this source]
  - **==DOK1 Facts==**
    - [Placeholder: Extract atomic knowledge units from the source. Each fact should be 15-25 words, max 35. Use simple bullet points, no numbering, no titles. Prefer 1 sentence per fact, up to 3 for complex concepts]
  - Link: [URL]
```

**Critical Formatting Rules**:
- DOK2 Summary header: Exactly `**==DOK2 Summary==**` (no numbering)
- DOK1 Facts header: Exactly `**==DOK1 Facts==**` (no numbering)
- DOK2 appears BEFORE DOK1 Facts
- Link line at the very end
- Use placeholder text that explains what user should add

### Step 12: Insert Source into BrainLift File

**For Existing Category**:
1. Locate the category section in the file
2. Insert new source entry after existing sources (before next category or end of section)
3. **Check Section Summary**:
   - If Section Summary contains placeholder text like `[Placeholder:` or `[Update after...`, replace it with:
     ```markdown
     [Update Section Summary after completing sources in this category - synthesize themes across all sources]
     ```
   - If Section Summary has actual content, leave it unchanged

**For New Category**:
1. Determine where to insert (typically at end of Knowledge Tree)
2. Create complete category structure:
```markdown
- **==[New Category Name]==**
  - **==Section Summary==**
    - [Update Section Summary after completing sources in this category - synthesize themes across all sources]
  - **[Source Title] - [Author/Organization] / [Publication] ([Year])**
    - **==DOK2 Summary==**
      - [Placeholder text]
    - **==DOK1 Facts==**
      - [Placeholder text]
    - Link: [URL]
```

**Use Edit tool** to make the insertion, preserving all existing content and formatting.

**Post-Insertion QC (Workflowy Compatibility)**:

After inserting the source, verify no empty lines were introduced:

a. Read the updated section from the BrainLift file to verify formatting
b. Check for empty lines:
   - Between source entry components (DOK2, DOK1, Link)
   - Between sources in the same category
   - Between category headers and Section Summary
   - Between Section Summary and first source
c. If empty lines are found, use Edit tool to remove them
d. Ensure all content maintains proper indentation without spacing

**Why this matters:** Workflowy's indent-based hierarchy breaks with empty lines. All components must be consecutive lines with only indentation defining relationships.

### Step 12.5: Global QC - Remove Empty Lines

After inserting source into the BrainLift file, run a comprehensive QC to ensure Workflowy compatibility:

1. **Run QC command** to remove all empty lines from the entire file:
   - Use Bash tool with the following command:
   ```bash
   grep -v '^$' brainlift/[filename].md > brainlift/[filename].tmp && mv brainlift/[filename].tmp brainlift/[filename].md
   ```
   - Replace `[filename]` with the actual BrainLift filename
   - This ensures no empty lines exist anywhere in the file

2. **Verify operation**:
   - Confirm file was updated successfully
   - Verify all content is preserved (only empty lines removed)
   - Check that indentation structure is maintained

**Why this matters:** Even if templates are clean, the Edit tool or existing file content may contain empty lines. This global QC ensures the entire file is Workflowy-compatible.

### Step 13: Confirm Addition and Prompt for Next Source

After successful insertion:

```
✓ Successfully added: [Source Title - Author]
   Location: [Category Name] in [brainlift-filename.md]
   Format: Workflowy-compatible (no empty lines)

Remaining sources from this search:
[List remaining sources by number and title]

Would you like to add another source from this list? (yes/no/done)
```

**If user says yes**:
- Return to Step 7 with remaining sources

**If user says no or done**:
- Proceed to Step 14

### Step 14: Continuation Loop

After user finishes adding sources from current batch:

```
You've added [N] source(s) to your BrainLift in this session.

Would you like to find more sources? (yes/no)
```

**If yes**:
- Return to Step 2 (Key Question Prompt) for a new search

**If no**:
- Proceed to Step 15 (Completion Summary)

### Step 15: Completion Summary

```
Great work! You've successfully added new sources to your BrainLift.

**Session Summary:**
- BrainLift: brainlift/[filename].md
- Format: Workflowy-compatible (no empty lines)
- Sources added: [N]
- Categories updated: [List of category names]

**Next Steps:**
1. Extract DOK1 facts and DOK2 summaries using /extract-dok1-dok2
2. Update Section Summaries after completing all sources in each category
3. Once you have 4+ complete sources, develop DOK3 Insights
4. With 5+ sources and strong patterns, draft DOK4 Spiky Points of View

**Tip:** Section Summaries should synthesize themes across ALL sources in a category, written after sources are complete.
```

## Important Guidelines

### 1. Source Research Quality

**Find Real, Accessible Sources**:
- Verify URLs are actual, accessible articles
- Prioritize diversity of viewpoints
- Recent content (2024-2025) when possible
- Mix of source types (academic, industry, blogs, research papers)

**Perspective Descriptions**:
- Be specific about the source's stance or main argument
- Help user understand what viewpoint this source brings
- 1-2 sentences maximum

### 2. Formatting Compliance (CRITICAL)

**Section Headers**: Use `**==TEXT==**` format (bold + double equals)
- `**==DOK2 Summary==**`
- `**==DOK1 Facts==**`
- `**==Section Summary==**`
- `**==[Category Name]==**`

**Source Entry Format**:
- Title format: `**[Title] - [Author/Organization] / [Publication] ([Year])**`
- DOK2 Summary appears BEFORE DOK1 Facts
- Simple bullet placeholder for DOK1, indented paragraph for DOK2
- Single "Link:" line at end

**NO** numbering in DOK sections:
- ❌ `**==DOK2-001 Summary==**`
- ❌ `- DOK1-001: [Fact]`
- ✅ `**==DOK2 Summary==**`
- ✅ `- [Fact]`

### 3. Category Placement Logic

**Recommend Existing Category When**:
- Source theme clearly aligns with existing category theme
- Category has fewer than 10 sources (not overfilled)
- Source addresses similar questions to existing sources

**Recommend New Category When**:
- Source addresses distinctly different aspect of BrainLift topic
- No existing category is thematically appropriate
- Source introduces new domain or perspective

**Explain Reasoning**:
- Always tell user WHY you're recommending a particular placement
- Reference specific themes, keywords, or topics
- Consider category balance

### 4. Section Summary Management

**Update Reminder When**:
- Adding source to existing category that has placeholder Section Summary
- Replace placeholder with: `[Update Section Summary after completing sources in this category - synthesize themes across all sources]`

**Leave Unchanged When**:
- Section Summary has actual synthesized content (not placeholder)
- User has already written the Section Summary

**Never Auto-Generate**:
- Don't write Section Summaries automatically
- They require synthesis across ALL sources in category
- User should write after completing source DOK1/DOK2 extraction

### 5. Interactive Workflow

**One Source at a Time**:
- User selects and places each source individually
- Allows different sources to go to different categories
- Clear progress tracking

**Approval Gates**:
- Get approval on source list before selection
- Allow iteration if sources don't match user needs
- Confirm placement in category

**Continuation Flexibility**:
- User controls how many sources to find (1-5)
- Can add all sources or stop partway
- Can find multiple batches with different key questions

### 6. Knowledge Tree Structure

**Maintain Hierarchy**:
```
- **==DOK2 - Knowledge Tree==**
  - **==[Category]==**
    - **==Section Summary==**
    - [Sources]
  - **==[Another Category]==**
    - **==Section Summary==**
    - [Sources]
```

**For Large Categories (10+ sources)** - Optional Sub-Sections:
```
- **==[Category]==**
  - **==Section Summary==**
  - **==[Sub-Section]==**
    - **==Section Summary==**
    - [Sources]
  - **==[Sub-Section 2]==**
    - **==Section Summary==**
    - [Sources]
```

**When Creating New Category**:
- Place at end of Knowledge Tree (before any closing markers)
- Include Section Summary placeholder
- Use clear, descriptive category name

### 7. Error Handling

**If WebSearch fails to find sources**:
```
I had difficulty finding sources for that key question. This might be because:
- The question is too specific or niche
- Recent sources on this topic are limited
- The phrasing doesn't match how articles discuss this topic

Would you like to:
1. Rephrase the key question
2. Search for a related but broader question
3. Try a different aspect of the topic
```

**If BrainLift file parsing fails**:
```
I had trouble parsing the Knowledge Tree structure in [filename].

This might be because:
- The file doesn't follow the standard BrainLift format
- The Knowledge Tree section is missing or malformed

Would you like me to:
1. Show you the file structure I found
2. Proceed by adding to the end of the file
3. Cancel and check the file format
```

### 8. Quality Checks Before File Update

Before using Edit tool, verify:
- [ ] Source entry has all required sections (DOK2, DOK1, Link)
- [ ] Headers use exact format: `**==DOK2 Summary==**` and `**==DOK1 Facts==**`
- [ ] Placeholder text is clear and instructive
- [ ] Link line is at the end
- [ ] Category structure is correct (Section Summary before sources)
- [ ] Insertion point is correct (after existing sources in category)
- [ ] All existing content is preserved

### 9. Workflowy Compatibility

**No Empty Lines**: Sources added to BrainLift files must have NO empty or spacer lines for Workflowy compatibility.

**Why This Matters**:
- Workflowy uses indent-based hierarchy, not empty lines
- Empty lines break parent-child relationships during import
- Continuous lines with proper indentation maintain structure
- The QC step (Step 12.5) ensures all empty lines are removed

**QC Process**:
- Source entry templates (Step 11) contain no empty lines by design
- New category templates (Step 12) contain no empty lines by design
- Step 12 includes post-insertion verification for local checks
- Step 12.5 runs global QC to clean entire file
- Command: `grep -v '^$'` filters out all empty lines

**Manual Verification** (if needed):
- Open BrainLift file and visually check for blank lines
- Run: `grep -c '^$' brainlift/[filename].md` (should return 0)
- If empty lines found, re-run QC command from Step 12.5

**Important**: This applies to the entire BrainLift file, not just newly added sources. The QC step cleans the complete file each time.

## Success Criteria

The command is successful when:

1. ✓ User selects a BrainLift file (or auto-selected)
2. ✓ User provides a key question
3. ✓ Sources are found matching the key question
4. ✓ User reviews and approves sources
5. ✓ User selects specific sources to add
6. ✓ Appropriate category placement is determined
7. ✓ Sources are inserted with proper formatting
8. ✓ Section Summary reminders are updated if needed
9. ✓ All formatting complies with brainlift-methodology.md
10. ✓ User knows next steps for completing the sources
11. ✓ Post-insertion QC confirms no empty lines (Workflowy compatible)

## Example Interaction Flow

This demonstrates the complete workflow from command invocation through adding sources:

```
User: /new-sources