# New DOK3 Insights Command

You are helping the user identify and add new DOK3 Insights to their BrainLift file. DOK3 Insights are cross-source synthesis that reveal patterns emerging from analyzing multiple sources together - patterns that wouldn't be visible from any single source alone.

## Context and Rules

**DOK3 Insights Requirements:**
- **Count**: Target 8-12 insights total in the file
- **Length**: 1-2 sentences per insight (20-50 words)
- **Timing**: Only create DOK3 when 4+ sources with DOK2 summaries exist
- **Format**: `**[Insight Title]** - [Statement]` (no numbering in the file)
- **Quality**: Must draw from 2+ sources, be actionable, reveal non-obvious patterns

**Your Process:**

---

## Step 1: Select BrainLift File and Parse Structure

1.1. List all `brainlift/*-brainlift.md` files
- If only 1 file: automatically select it
- If multiple files: show numbered list and ask user to select

1.2. Parse the selected file to identify:
- **Purpose** section
- **Existing DOK3 - Insights** (count them)
- **All DOK2 summaries** across all sources/categories
- **All DOK1 facts** across all sources/categories
- Total number of sources available

1.3. Display to user:
```
Found [X] existing DOK3 Insights (target: 8-12)
Analyzing [Y] sources with DOK2 summaries
```

1.4. **Validation check**: If fewer than 4 sources exist, inform user:
```
⚠️ DOK3 Insights require 4+ sources with DOK2 summaries for meaningful cross-source synthesis.
Current source count: [X]

Please add more sources and DOK2 summaries before creating DOK3 Insights.
```
Stop here if validation fails.

---

## Step 2: Comprehensive Cross-Source Analysis

2.1. Analyze ALL DOK2 summaries and DOK1 facts from ALL sources in the file

2.2. Look for patterns that emerge when combining multiple sources:
- **Contrarian insights**: Where sources challenge conventional wisdom together
- **Cross-domain bridges**: Connecting insights from different fields/contexts
- **Actionable patterns**: Strategic or tactical guidance that emerges from synthesis
- **Hidden tensions**: Contradictions or paradoxes revealed across sources
- **Convergent themes**: Multiple sources pointing to same non-obvious conclusion

2.3. For each potential DOK3 insight:
- Verify it requires 2+ sources to derive (cannot come from single source)
- Check it's not a duplicate or near-duplicate of existing DOK3 Insights
- Ensure it reveals something readers wouldn't see from individual sources alone
- Confirm it's actionable (provides strategic or tactical value)

---

## Step 3: Propose New DOK3 Insights to User

3.1. Present 3-5 candidate insights in this format:

```
I've identified [X] potential DOK3 Insights based on cross-source analysis:

**1. [Insight Title]** - [1-2 sentence statement, 20-50 words]
   - **Rationale**: [Why this is meaningful cross-source synthesis]
   - **Supporting Evidence**:
     - Source 1: [DOK2/DOK1 reference]
     - Source 2: [DOK2/DOK1 reference]
     - [Source 3 if applicable]

**2. [Insight Title]** - [1-2 sentence statement, 20-50 words]
   - **Rationale**: [Why this is meaningful cross-source synthesis]
   - **Supporting Evidence**:
     - Source 1: [DOK2/DOK1 reference]
     - Source 2: [DOK2/DOK1 reference]

[Continue for 3-5 total candidates]
```

3.2. Include this guidance:
- Numbers (1, 2, 3...) are ONLY for selection - they won't appear in the file
- Each insight shows title + statement that will be added
- Rationale explains why it's valuable cross-source synthesis
- Supporting evidence shows which sources contribute to each insight

---

## Step 4: Get User Selection

4.1. Ask user:
```
Which insights should I add to the BrainLift file?

Options:
- Enter numbers (e.g., "1,3,5" or "1, 3, 5")
- Type "all" to add all proposed insights
- Type "none" to skip adding insights
- Type "revise" to see different candidate insights

Your choice:
```

4.2. Parse user response:
- If numbers: validate they're in range (1 to X)
- If "all": select all proposed insights
- If "none": stop and thank user
- If "revise": return to Step 2 with instruction to find different patterns
- If invalid: show error and re-prompt

---

## Step 5: Add Approved DOK3 Insights

5.1. Locate the DOK3 - Insights section in the file:
- Should appear after Purpose, before Experts
- If section doesn't exist, create it with header: `- **==DOK3 - Insights==**`

5.2. For each approved insight (in the order proposed):
- Format: `  - **[Title]** - [Statement]`
- No numbering in the actual file
- Maintain proper indentation (2 spaces before bullet)
- Add insights to end of existing DOK3 Insights (if any exist)

5.3. Use Edit tool to update the file:
- Make atomic edits to insert each new insight
- Preserve all existing content
- Maintain file structure (Purpose → DOK3 → Experts → Categories/Sources)

---

## Step 5.5: Workflowy Compatibility QC

5.5.1. **Critical**: Run this command to remove any empty lines:
```bash
grep -v '^$' [brainlift-file].md > [brainlift-file].tmp && mv [brainlift-file].tmp [brainlift-file].md
```

5.5.2. Verify zero empty lines:
```bash
grep -c '^$' [brainlift-file].md
```
Should return: `0`

5.5.3. If verification fails:
- Manually inspect file for empty lines
- Remove them using Edit tool
- Re-run verification

5.5.4. Inform user:
```
✅ WorkFlowy Compatibility Check: PASSED
   - Empty lines removed: [N]
   - Current empty line count: 0
```

5.5.5. **Why this matters**: Workflowy uses indentation-based hierarchy. Empty lines break parent-child relationships during import, causing structural corruption.

---

## Step 6: Completion Summary

6.1. Display summary:
```
✅ Added [X] new DOK3 Insights:
- [Title 1]
- [Title 2]
[...]

Current DOK3 Insight count: [Y] (target: 8-12)
File: [brainlift-file-name].md
```

6.2. Offer next action based on count:
- If under 8 insights: "Would you like me to identify more DOK3 Insights? (yes/no)"
- If 8-12 insights: "You're within the target range (8-12 insights). Add more? (yes/no)"
- If over 12 insights: "⚠️ You have [Y] insights (target: 8-12). Consider consolidating similar insights."

6.3. If user says yes to continue:
- Return to Step 2 with instruction to find different patterns
- Ensure new proposals don't duplicate what was just added

6.4. If user says no or declines:
```
Great! Your DOK3 Insights are updated and Workflowy-compatible.

Next steps you might consider:
- Review insights for clarity and impact
- Develop DOK3 Blueprints to operationalize these insights
- Continue adding sources to deepen cross-source synthesis
```

---

## Important Notes

**Tone & Style:**
- Interactive: one step at a time, wait for user confirmation
- Helpful: provide examples and clear instructions
- Validating: check inputs and offer sensible defaults
- Plain language: Grade 12 reading level for all DOK content

**Quality Standards:**
- Each insight must synthesize 2+ sources
- Insights reveal patterns not visible in individual sources
- Statements are actionable (strategic or tactical guidance)
- Length: 20-50 words (1-2 sentences)
- Format: `**[Title]** - [Statement]` with no numbering

**Workflowy Compatibility:**
- Zero empty lines in the file (critical!)
- Continuous line structure with indentation for hierarchy
- QC step is mandatory, not optional
- Verify with `grep -c '^$'` after all edits

**File Structure Preservation:**
- DOK3 - Insights appears after Purpose, before Experts
- Maintain all existing sections and content
- Use atomic Edit operations
- Never create duplicate sections