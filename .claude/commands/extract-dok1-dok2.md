You are helping the user extract DOK1 facts and DOK2 summaries from sources in their BrainLift Knowledge Tree.

## Usage

```
/extract-dok1-dok2
```

**Examples:**
- `/extract-dok1-dok2` - Interactive command that guides you through extracting DOK1 and DOK2 content for sources

## Purpose

This command helps you systematically extract DOK1 facts and DOK2 summaries from sources in your BrainLift. It prioritizes sources without existing DOK1/DOK2 content, validates extraction quality against the original source, and ensures WorkFlowy compatibility.

## Process

### Step 1: Find and Select BrainLift File

1.1. Use the `Glob` tool to find all `.md` files in the `brainlift/` folder

1.2. If multiple BrainLift files are found:
   - Present a numbered list of available BrainLift files
   - Ask the user: "Which BrainLift would you like to work with?"
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
   - This provides context for framing DOK1/DOK2 extraction
   - Specifically extract the "In Scope:" statement

2.3. Parse the **==DOK2 - Knowledge Tree==** section to identify all sources:
   - Find all source entries (format: `**[Source Title] - [Author] / [Publication] ([Year])**`)
   - Extract the URL for each source (line starting with `Link:`)
   - Store source title, author, publication, year, and URL for each

2.4. If no sources are found in the Knowledge Tree:
   - Inform user: "No sources found in the Knowledge Tree. Please add sources first using /new-sources"
   - Stop execution

### Step 3: Analyze and Present Source List

3.1. Use `Grep` to identify which sources already have DOK1/DOK2 content:
   - Search for `**==DOK1 Facts==**` pattern to identify sources with DOK1 content
   - Search for `**==DOK2 Summary==**` pattern to identify sources with DOK2 content
   - Mark sources as "complete" if they have both DOK1 and DOK2

3.2. Create a numbered source list with the following structure:
   - **First**: Sources WITHOUT DOK1/DOK2 (marked with `[ ]`)
   - **Second**: Sources WITH existing DOK1/DOK2 (marked with `[✓]`)

3.3. Present the list to the user:
```
I found [N] sources in your BrainLift:

Sources without DOK1/DOK2:
  [ ] 1. [Source Title] - [Author] / [Publication] ([Year])
  [ ] 2. [Source Title] - [Author] / [Publication] ([Year])

Sources with existing DOK1/DOK2:
  [✓] 3. [Source Title] - [Author] / [Publication] ([Year])

Which source would you like to extract DOK1 and DOK2 for? (Enter number)
```

3.4. Wait for user to select a number

3.5. If user selects a source with existing DOK1/DOK2:
   - Show the existing content
   - Ask: "This source already has DOK1/DOK2 content. Would you like to regenerate it?"
   - If user says no, return to step 3.3 to select a different source

### Step 4: Extract DOK1 and DOK2 Content

4.1. Retrieve the selected source details:
   - Source title, author, publication, year
   - Source URL
   - BrainLift Purpose (from Step 2.2)

4.2. Use `WebFetch` to retrieve the original source content from its URL:
   - Store the full source content for later verification
   - If URL cannot be fetched, inform user and ask if they want to proceed without source verification

4.3. Generate DOK1 and DOK2 content using the following extraction prompt:

```
Let's extract the key DOK1 facts and DOK2 summary from this source:

**Source:** [Source Title] - [Author] / [Publication] ([Year])
**BrainLift Purpose:** [In Scope statement from Step 2.2]

Frame the DOK1 facts and DOK2 summary in the context of our defined purpose above.

---

## DOK1 Facts - Extraction Guidelines

**Format:** Simple bullet points ONLY (no numbering, no titles, no "DOK1-XXX:" prefixes)

**Content Rules:**
- Sentence Length: 15-25 words average, 35 words MAXIMUM per sentence
- Complexity: Prefer 1 sentence per fact; use 2-3 sentences (40-75 words total) only for complex concepts
- Reading Level: Grade 12 (Flesch-Kincaid) - accessible to high school graduates
- Voice: Active voice preferred over passive
- Vocabulary: Common words over jargon; replace technical terms when possible
- Quotes: Preserve exact quotes from sources (don't simplify)
- Accuracy: Maintain factual precision; don't round numbers or generalize data
- Self-Containment: Each fact stands alone (doesn't require reading other facts to understand)

**Writing Patterns to Follow:**

Pattern 1 - Dash Connections:
- Element interactivity determines intrinsic cognitive load - how many elements must be processed simultaneously

Pattern 2 - Direct Statements:
- SPOVs are your thesis about topics in your realm of expertise

Pattern 3 - Concrete Comparisons:
- AI maintains F-score standard deviation of 0.02 versus 0.12 for human reviewers

**Example DOK1 Facts:**

1. Hot documents have "clear potential to impact the instant case or even an unrelated matter" and require immediate supervisor escalation

2. AI maintains F-score standard deviation of 0.02 versus 0.12 for human reviewers

3. The brain cannot multitask - it switches between tasks with high cognitive cost

---

## DOK2 Summary - Extraction Guidelines

**Format:** Exactly `**==DOK2 Summary==**` header followed by bullet point(s)

**Content Rules:**
- Sentence Count: 4-5 sentences (NOT 1-2 run-on sentences)
- Sentence Length: 20-30 words average, 40 words MAXIMUM per sentence
- Total Length: 80-150 words
- Reading Level: Grade 12 (Flesch-Kincaid)
- Voice: Active voice preferred
- Function: Synthesize connections between DOK1 facts (show "so what"), don't just list them
- Structure: Topic sentence → supporting points → implication

**Example DOK2 Summary:**

**==DOK2 Summary==**
  - This empirical study compares AI and human document review accuracy, revealing AI matches professional competency at dramatically lower cost. GPT-4 achieved F-score 0.871, matching junior lawyers at 0.860, while completing review 77x faster. Cost per document dropped from $74 (junior lawyers) to $0.25 (GPT-4)—a 99.97% reduction. AI maintains consistent accuracy regardless of speed, breaking the human speed-quality tradeoff. This enables previously uneconomical litigation by making comprehensive review viable for mid-stakes cases.

---

## Target Counts

**DOK1 Facts:**
- Extract as many atomic knowledge units as the source yields
- Typical range: 3-8 DOK1 facts for focused content
- Can be 15+ for comprehensive sources
- Quality over quantity - each fact should be genuinely valuable

**DOK2 Summaries:**
- Typically ONE summary per source
- Can create MULTIPLE summaries if:
  - DOK1 facts naturally cluster into distinct themes
  - Source yields 15+ DOK1 facts (unwieldy in single summary)
  - Facts serve different application contexts

---

## Your Task

Extract DOK1 facts and a DOK2 summary from the source following the guidelines above. Also produce a robust summary (2-3 sentences) identifying the key threads between the DOK1 facts relevant to our BrainLift purpose.

Present your extraction in this format:

**DOK2 Summary:**
[Your DOK2 summary in proper format]

**DOK1 Facts:**
- [Fact 1]
- [Fact 2]
- [Fact 3]
...

**Key Threads:**
[2-3 sentences connecting the DOK1 facts to the BrainLift purpose]
```

4.4. Generate the DOK1 and DOK2 content based on the source material

### Step 5: Quality Validation

5.1. **Source Verification**
   - Use `WebFetch` again to re-read the original source content from its URL
   - Compare the proposed DOK1/DOK2 entries against the actual source content
   - Verify:
     - ✅ All facts are present in the source (nothing fabricated)
     - ✅ Quotes are exact and properly attributed with quotation marks
     - ✅ Numbers and statistics are accurate (not rounded or changed)
     - ✅ Context is preserved (no misrepresentation of author's intent)
   - If any discrepancies are found:
     - List the specific issues
     - Regenerate the problematic DOK1/DOK2 entries
     - Re-verify after regeneration

5.2. **Word Count Check**
   - For each DOK1 fact:
     - Count words in each sentence
     - Flag if any sentence exceeds 35 words
     - Check if average is within 15-25 words
   - For DOK2 summary:
     - Count total words (should be 80-150)
     - Count sentences (should be 4-5)
     - Check individual sentence length (max 40 words)
   - Display metrics to user

5.3. **Sentence Limit Check**
   - Verify each DOK1 fact is typically 1 sentence (2-3 only for complex concepts)
   - Verify DOK2 summary is exactly 4-5 sentences
   - Flag any violations

5.4. **Format Check**
   - Verify DOK1 facts use simple bullets (no numbering, no "DOK1-XXX:" prefixes, no titles)
   - Verify DOK2 summary uses exact header: `**==DOK2 Summary==**`
   - Verify DOK2 summary has bullet point(s) below header
   - Flag any formatting issues

5.5. **Present Validation Results and Preview**

Present to user:
```
## Quality Validation Results

**Source Verification:** [✅ Pass / ❌ Issues found]
[If issues: List specific discrepancies]

**Word Count Check:**
DOK1 Facts: [N] facts generated
  - Average words per fact: [X] words (target: 15-25)
  - Longest fact: [X] words (max: 35)
  - [✅ Pass / ❌ Needs adjustment]

DOK2 Summary:
  - Total words: [X] (target: 80-150)
  - Sentences: [X] (target: 4-5)
  - Longest sentence: [X] words (max: 40)
  - [✅ Pass / ❌ Needs adjustment]

**Format Check:** [✅ Pass / ❌ Needs adjustment]

---

## Preview of Content to Insert

**==DOK2 Summary==**
  - [Preview DOK2 content]

**==DOK1 Facts==**
  - [Preview DOK1 fact 1]
  - [Preview DOK1 fact 2]
  ...

**Key Threads:** [Preview key threads summary]

---

Do you approve this content for insertion? (yes/no/edit)
```

5.6. Wait for user response:
   - If "yes": Proceed to Step 6
   - If "no": Return to Step 4.3 to regenerate
   - If "edit": Ask user what changes they want, then regenerate specific parts

### Step 6: Insert Content into BrainLift

6.1. Locate the selected source's section in the BrainLift file:
   - Find the line containing the source title
   - Identify the insertion point (immediately after the source title line)

6.2. Prepare the content to insert (in this order):
   - `**==DOK2 Summary==**` (on its own line)
   - DOK2 summary bullet point(s) (with proper indentation)
   - `**==DOK1 Facts==**` (on its own line)
   - DOK1 fact bullet points (with proper indentation)

6.3. If source already has DOK1/DOK2 content:
   - Use `Edit` tool to replace the old content with new content
   - Remove old `**==DOK2 Summary==**` section and old `**==DOK1 Facts==**` section
   - Insert new content in the same location

6.4. If source does not have DOK1/DOK2 content:
   - Use `Edit` tool to insert new content after the source title line
   - Maintain proper indentation (sources are typically indented with spaces)

6.5. Verify insertion by reading the relevant section of the file to confirm correct placement

6.6. Inform user: "✅ Content inserted successfully for: [Source Title]"

### Step 7: WorkFlowy Compatibility QC

7.1. Run the QC command to remove any empty lines:
```bash
grep -v '^$' brainlift/[filename].md > brainlift/[filename].tmp && mv brainlift/[filename].tmp brainlift/[filename].md
```

7.2. Verify no empty lines remain:
```bash
grep -c '^$' brainlift/[filename].md
```

7.3. Expected result: `0` empty lines

7.4. If empty lines are found:
   - Re-run the QC command
   - Re-verify
   - If still present, manually inspect and remove

7.5. Inform user:
```
✅ WorkFlowy Compatibility Check: PASSED
   - Empty lines removed: [N]
   - Current empty line count: 0
```

### Step 8: Offer to Continue

8.1. Re-scan the BrainLift to update the source list (now the completed source should show `[✓]`)

8.2. Present the updated source list:
```
✅ Completed: [Source Title]

Updated source list:

Sources without DOK1/DOK2:
  [ ] 1. [Source Title] - [Author] / [Publication] ([Year])
  [ ] 2. [Source Title] - [Author] / [Publication] ([Year])

Sources with existing DOK1/DOK2:
  [✓] 3. [Previously completed source]
  [✓] 4. [Just completed source]

Would you like to extract DOK1/DOK2 for another source? (yes/no)
```

8.3. Wait for user response:
   - If "yes": Return to Step 3.3 (present source list for selection)
   - If "no": Proceed to Step 8.4

8.4. Show completion summary:
```
## Extraction Session Complete

**Sources Processed:** [N]
**DOK1 Facts Added:** [N total across all sources]
**DOK2 Summaries Added:** [N total across all sources]
**WorkFlowy Compatibility:** ✅ Verified

Great work! Your BrainLift has been updated with new DOK1 and DOK2 content.

Next steps you might consider:
- Use /new-dok3 to create cross-source insights after you have 4+ sources with DOK2 summaries
- Continue adding more sources with /new-sources
- Review the Section Summary for each category and update after completing sources
```

## Important Guidelines

1. **Always Re-Fetch Source:** Never trust memory or previous fetches. Always use WebFetch to get the current source content before extraction and again for verification.

2. **Never Fabricate:** Every DOK1 fact must be directly traceable to specific content in the source. If you cannot find support for a fact in the source, do not include it.

3. **Preserve Exact Quotes:** When a DOK1 fact includes quoted material, the quote must be verbatim from the source. Use quotation marks to indicate quoted content.

4. **Maintain Accuracy:** Numbers, statistics, dates, and technical terms must match the source exactly. Do not round, approximate, or simplify factual data.

5. **WorkFlowy Compatibility:** The QC step in Step 7 is mandatory. Empty lines will break the BrainLift structure when imported to WorkFlowy.

6. **Quality Over Quantity:** It's better to have 3 excellent DOK1 facts than 10 mediocre ones. Each fact should provide genuine value.

7. **Show Your Work:** Always display validation results and preview content before insertion. Never insert content without user approval.

8. **Simplify Language:** Follow the simplification techniques from the methodology. Replace jargon with common words while maintaining factual accuracy.

9. **Frame in Context:** Always reference the BrainLift's Purpose when extracting. DOK1/DOK2 should be relevant to the defined scope.

10. **Iterative Refinement:** If validation fails or user requests changes, regenerate specific parts rather than starting over completely.

## Success Criteria

Before completing the command, verify:

- [ ] Source was fetched from URL and content was verified against extraction
- [ ] All DOK1 facts are present in the original source (nothing fabricated)
- [ ] Quotes are exact and properly attributed
- [ ] Numbers and statistics match the source exactly
- [ ] DOK1 facts average 15-25 words per sentence, none exceed 35 words
- [ ] DOK2 summary is 80-150 words total with 4-5 sentences
- [ ] DOK2 summary shows connections between DOK1 facts (not just listing them)
- [ ] Format matches methodology: simple bullets for DOK1, proper `**==Headers==**` for sections
- [ ] Content was previewed and approved by user before insertion
- [ ] Content inserted in correct location within source section
- [ ] WorkFlowy QC passed: 0 empty lines remain in file
- [ ] User was offered option to continue with another source

## Why This Matters

DOK1 and DOK2 are the foundation of your BrainLift's knowledge structure. Well-crafted DOK1 facts become building blocks for DOK3 insights and DOK4 SPOVs. Taking time to verify accuracy, maintain proper formatting, and frame content in your BrainLift's purpose ensures that downstream synthesis (DOK3/DOK4) builds on solid ground.

The source verification step (Step 5.1) is particularly critical because it prevents the accumulation of fabricated or misremembered content that could undermine the credibility of your entire BrainLift.
