You are helping the user add new research sources to an existing BrainLift Knowledge Tree.

## Usage

```
/new-sources
```

**Examples:**
- `/new-sources` - Interactive command that guides you through finding and adding new research sources to your BrainLift

## Purpose

This command helps you systematically add new research sources to your existing BrainLift. It finds diverse sources addressing a key question you want to explore, lets you select which sources to add, suggests appropriate placement in your Knowledge Tree, and ensures WorkFlowy compatibility.

## Process

### Step 1: Find and Select BrainLift File

1.1. Use the `Bash` tool to find all `.md` files in the `brainlift/` folder:
```bash
find brainlift -name "*-brainlift.md" -type f
```

1.2. If multiple BrainLift files are found:
   - Present a numbered list of available BrainLift files
   - Ask the user: "Which BrainLift would you like to add sources to?"
   - Wait for user selection

1.3. If only one BrainLift file is found:
   - Proceed with that file
   - Inform user: "Working with: [filename]"

1.4. If no BrainLift files are found:
   - Inform user: "No BrainLift files found in brainlift/ folder. Please create a BrainLift first using /new_brainlift"
   - Stop execution

### Step 2: Read BrainLift Structure

2.1. Use the `Read` tool to load the selected BrainLift file completely

2.2. Extract and store the **Purpose** section:
   - This provides context for source research
   - Specifically extract the "In Scope:" statement

2.3. Parse the **==DOK2 - Knowledge Tree==** section to identify existing categories:
   - Find all category headers (format: `**==[Category Name]==**`)
   - Store category names and their location in the file
   - This will help suggest placement for new sources

2.4. Note the structure for later insertion

### Step 3: Ask for Key Question

3.1. Present the BrainLift's purpose to the user:
```
Your BrainLift's Purpose:
**In Scope:** [Purpose statement from Step 2.2]

What key question do you want to answer with these new sources?
```

3.2. Wait for user to provide their key question

3.3. Store the key question for use in research queries

### Step 4: Research and Find Sources

4.1. Use the `WebSearch` tool to find 3-5 recent sources that take different positions on the user's key question

**Search Strategies:**
- Search for "[key question]"
- Search for "[topic] 2025" or "[topic] 2024" to find recent content
- Look for articles from different sources (academic publications, industry blogs, reports, news outlets)
- Prioritize sources with specific viewpoints or opinions
- Aim for diversity in perspective and publication type

4.2. For each source found, collect:
- **Title**: Full article/report title
- **Author/Organization**: Who wrote it or which organization published it
- **Publication**: Where it was published (journal, blog, company site, etc.)
- **Year**: Publication year (prefer 2024-2025)
- **URL**: Direct link to the source
- **Perspective**: 1-2 sentence description of the position it takes on the key question

4.3. Aim to find 3-5 sources total

### Step 5: Present Findings to User

5.1. Present your research findings in a clear, numbered format:
```
I've found [N] sources addressing your key question: "[key question]"

1. **[Article Title] - [Author/Organization] / [Publication] ([Year])**
   - Perspective: [Brief description of stance]
   - Link: [URL]

2. **[Article Title] - [Author/Organization] / [Publication] ([Year])**
   - Perspective: [Brief description of stance]
   - Link: [URL]

3. **[Article Title] - [Author/Organization] / [Publication] ([Year])**
   - Perspective: [Brief description of stance]
   - Link: [URL]

[Continue for all sources found]

Do these sources provide diverse viewpoints on your key question?
(Enter: yes / refine / cancel)
```

5.2. Wait for user response:
   - If "yes": Proceed to Step 6
   - If "refine": Ask "What's missing or what would you like me to adjust?" → Return to Step 4 with refined search
   - If "cancel": Exit gracefully with message "Source research cancelled"

### Step 6: User Selection of Sources

6.1. Ask the user which sources they want to add:
```
Which sources would you like to add to your BrainLift?

Options:
- Enter numbers (e.g., "1,3,5" or "1, 3, 5" or "1 3 5")
- Type "all" to add all sources
- Type "none" to cancel

Your choice:
```

6.2. Wait for user input

6.3. Parse the user's selection:
   - If "all": Select all sources
   - If "none": Exit gracefully
   - If numbers: Parse the numbers and select corresponding sources
   - Validate that numbers are within range

6.4. Store the selected sources for insertion

### Step 7: Suggest Placement in Knowledge Tree

7.1. Analyze existing categories in the DOK2 - Knowledge Tree (from Step 2.3)

7.2. Based on the key question and selected sources, suggest the most appropriate placement:
   - If sources align with an existing category: Suggest that category
   - If sources represent a new theme: Suggest a new category name

7.3. Present suggestion to user:
```
I suggest adding these sources to the following category:

**Existing category:** **==[Category Name]==**

Do you agree with this placement? (yes / specify-different)
```

OR if suggesting new category:
```
I suggest creating a new category for these sources:

**New category:** **==[Suggested Category Name]==**

Do you agree with this category name? (yes / specify-different)
```

7.4. Wait for user response:
   - If "yes": Use suggested placement/category name
   - If "specify-different": Ask "What category name would you like to use?" → Wait for response → Store new category name

7.5. Store the final category name and determine if it's new or existing

### Step 8: Format Source Structures

8.1. For each selected source, format according to brainlift-methodology.md:

**Source Format:**
```
- **[Source Title] - [Author/Organization] / [Publication] ([Year])**
  - **==DOK2 Summary==**
    - [PLACEHOLDER: Extract 4-5 sentence summary (80-150 words) using /extract-dok1-dok2]
  - **==DOK1 Facts==**
    - [PLACEHOLDER: Extract key facts as simple bullets using /extract-dok1-dok2]
  - Link: [URL]
```

**Indentation Rules:**
- Source title: 2 spaces (one level under category or sub-section)
- DOK2/DOK1 headers: 4 spaces (two levels)
- DOK2/DOK1 content: 6 spaces (three levels)
- Link: 4 spaces (two levels)

8.2. If adding to existing category with existing **==Sources==** section:
   - Sources will be inserted under the **==Sources==** header
   - Maintain same indentation as existing sources

8.3. If adding to existing category without **==Sources==** section:
   - Will need to add **==Sources==** header first
   - Then add source entries

8.4. If creating new category:
   - Create full category structure:
   ```
   - **==[New Category Name]==**
     - **==Section Summary==**
       - [PLACEHOLDER: After completing DOK1/DOK2 extraction for all sources, write 2-4 sentences synthesizing themes across ALL sources in this category]
     - **==Sources==**
       - [Source entries here]
   ```

### Step 9: Preview Before Insertion

9.1. Show the user exactly what will be added and where:

```
## Preview of Content to Insert

**Location:** **==[Category Name]==** section in DOK2 - Knowledge Tree

**Content to add:**

[Show the exact formatted content that will be inserted, with proper indentation]

---

This will add [N] new source(s) to your BrainLift.

Do you approve this insertion? (yes / no / edit)
```

9.2. Wait for user response:
   - If "yes": Proceed to Step 10
   - If "no": Ask "What would you like to change?" → Adjust as needed → Return to Step 9.1 with updated preview
   - If "edit": Ask "What specific changes do you need?" → Make changes → Return to Step 9.1

### Step 10: Insert Content into BrainLift

10.1. Locate the insertion point in the BrainLift file:
   - If adding to existing category with **==Sources==** section: Insert after the last source in that section
   - If adding to existing category without **==Sources==** section: Insert **==Sources==** header after Section Summary, then add sources
   - If creating new category: Insert entire new category structure at the end of DOK2 - Knowledge Tree section

10.2. Use the `Edit` tool to insert the content:
   - Maintain proper indentation (match surrounding content)
   - Ensure no extra empty lines are introduced
   - Preserve the structure of the Knowledge Tree

10.3. Verify insertion by using `Read` tool to check the relevant section

10.4. Inform user: "✅ Content inserted successfully: [N] source(s) added to **==[Category Name]==**"

### Step 11: WorkFlowy Compatibility QC

11.1. Run the QC command to remove any empty lines:
```bash
grep -v '^$' brainlift/[filename].md > brainlift/[filename].tmp && mv brainlift/[filename].tmp brainlift/[filename].md
```

11.2. Verify no empty lines remain:
```bash
grep -c '^$' brainlift/[filename].md
```

11.3. Expected result: `0` empty lines

11.4. If empty lines are found:
   - Re-run the QC command
   - Re-verify
   - If still present, manually inspect and use `Edit` tool to remove

11.5. Inform user:
```
✅ WorkFlowy Compatibility Check: PASSED
   - Empty lines removed: [N]
   - Current empty line count: 0
```

11.6. **Why this matters:** WorkFlowy uses indentation-based hierarchy. Empty lines break parent-child relationships during import, causing structural corruption. This step ensures your BrainLift maintains its structure when imported to WorkFlowy.

### Step 12: Completion and Next Steps

12.1. Show completion summary:
```
## Sources Added Successfully

**BrainLift:** [filename]
**Category:** **==[Category Name]==**
**Sources Added:** [N]

✅ All sources added with placeholder structure
✅ WorkFlowy compatibility verified

---

## Next Steps

1. **Extract DOK1 Facts and DOK2 Summaries**
   - Use `/extract-dok1-dok2` to read each source and extract key content
   - This will replace the [PLACEHOLDER] text with actual knowledge

2. **Update Section Summary** (if applicable)
   - After completing DOK1/DOK2 extraction, update the **==Section Summary==** at the top of the category
   - Should synthesize themes across ALL sources in the category (2-4 sentences)

3. **Continue Building**
   - Once you have 4+ sources with DOK2 summaries, use `/new-dok3` to create cross-source insights
   - Continue adding more sources with `/new-sources` to explore different aspects of your topic
```

12.2. Ask if user wants to continue:
```
Would you like to add more sources? (yes / no)
```

12.3. Wait for user response:
   - If "yes": Return to Step 3 (ask for new key question)
   - If "no": End with "Great work! Your BrainLift has been updated."

## Important Guidelines

1. **Always Find BrainLift First:** Never ask the user for a BrainLift filename. Use the `find` or `Bash` tool to locate BrainLift files in the brainlift/ directory. Only work with files you have specifically found.

2. **Context-Driven Research:** Always read the BrainLift's Purpose before asking for the key question. This ensures the sources align with the BrainLift's scope.

3. **Diverse Perspectives:** Actively seek sources with different viewpoints. Avoid echo chambers. Look for academic, industry, practitioner, and critical perspectives.

4. **Recent Sources:** Prioritize 2024-2025 content when possible, but don't sacrifice quality or relevance for recency.

5. **Placeholder Structure Only:** This command creates the source structure with placeholders. DO NOT attempt to extract DOK1/DOK2 content. That's the job of `/extract-dok1-dok2`.

6. **Source Format Compliance:** Follow brainlift-methodology.md exactly:
   - Format: `**[Source Title] - [Author/Org] / [Publication] ([Year])**`
   - Headers: `**==DOK2 Summary==**` and `**==DOK1 Facts==**`
   - Simple bullets under headers (no numbering, no prefixes)
   - Link line after facts

7. **WorkFlowy Compatibility:** The QC step in Step 11 is mandatory. Empty lines will break the BrainLift structure when imported to WorkFlowy. Always verify with `grep -c '^$'`.

8. **Show Before Insert:** Always preview the exact content and location before insertion. Never insert content without user approval.

9. **Proper Indentation:** Maintain consistent indentation (2 spaces per level). Match the indentation of surrounding content in the Knowledge Tree.

10. **Interactive and Iterative:** Give users control at each decision point. Allow refinement, adjustment, and cancellation throughout the process.

11. **Category Placement Logic:**
    - Existing category with similar theme → Add to that category
    - New distinct theme → Create new category
    - When in doubt → Ask the user

12. **Graceful Error Handling:**
    - If no BrainLift files found → Direct user to `/new_brainlift`
    - If user cancels → Exit gracefully with confirmation
    - If search fails → Offer to try different search terms

## Success Criteria

Before completing the command, verify:

- [ ] BrainLift file was found using `find` or `Bash` tool (not user-provided filename)
- [ ] BrainLift Purpose was read and used to frame research context
- [ ] Key question was collected from user AFTER reading BrainLift
- [ ] WebSearch found 3-5 sources with diverse perspectives
- [ ] Each source has: Title, Author/Org, Publication, Year, URL, Perspective
- [ ] User was shown findings and had opportunity to refine
- [ ] User selected specific sources to add (or chose "all")
- [ ] Category placement was suggested and user approved
- [ ] Source structure follows brainlift-methodology.md format exactly
- [ ] Placeholders are clearly marked for DOK1/DOK2 extraction
- [ ] Content was previewed with exact indentation before insertion
- [ ] User approved insertion before it was performed
- [ ] Content inserted at correct location in Knowledge Tree
- [ ] Proper indentation maintained (2 spaces per level)
- [ ] WorkFlowy QC passed: 0 empty lines remain in file
- [ ] User was guided to use `/extract-dok1-dok2` next
- [ ] User was offered option to continue adding more sources

## Why This Matters

The quality of your BrainLift depends on the diversity and relevance of your sources. This command helps you systematically expand your Knowledge Tree by:

1. **Maintaining Context:** By reading the BrainLift's Purpose first, sources stay aligned with your defined scope
2. **Ensuring Diversity:** Active search for different perspectives prevents confirmation bias
3. **Preserving Structure:** Proper formatting and WorkFlowy compatibility ensure the knowledge remains usable
4. **Enabling Synthesis:** Well-organized sources in thematic categories make DOK3 insights and DOK4 SPOVs easier to develop

The placeholder approach (adding structure now, extracting content later) separates concerns and lets you efficiently gather multiple sources before diving deep into extraction work.
