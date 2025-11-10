# New BrainLift

You are tasked with helping the user create a new BrainLift document through an interactive process. You will gather information about their topic, research experts and sources, and create a properly formatted BrainLift markdown file following the methodology specified in brainlift-methodology.md.

## Usage

```
/new_brainlift
```

This command has no parameters. It will guide you through an interactive process with consistent prompts every time.

## Process

When this command is invoked, follow these steps:

### Step 1: Gather Initial Information

Ask the user three questions, one at a time, with examples for each:

1. **Topic Question**:
```
What topic do you want to create a BrainLift about?

Example: "AI agent orchestration in enterprise workflows"
```

2. **Interest Question**:
```
What is your initial interest? (Provide 2-3 sentences about what you want to learn and why)

Example: "I'm building a system that coordinates multiple AI agents to handle complex business processes. I need to understand the trade-offs between different orchestration patterns and when to use centralized vs. decentralized coordination. I'm particularly interested in handling failures and maintaining consistency across agent interactions."
```

3. **Key Question**:
```
What is a key question you want to explore about this topic?

Example: "How should enterprises architect agent orchestration to balance autonomy with coordination?"
```

Wait for the user's response to each question before proceeding to the next.

### Step 2: Define Purpose Statements

Based on the user's responses, draft clear and specific Purpose statements:

1. **Draft In Scope statement**:
   - Format: One sentence covering what this BrainLift covers, the audience, the value, and the domain
   - Make it specific and narrow to a niche where strong opinions are valuable

2. **Draft Out of Scope statements**:
   - Format: 3-5 related topics that will NOT be covered
   - These should be adjacent but distinct topics

Present the drafted Purpose statements to the user:
```
Based on your topic, here's a proposed Purpose:

**In Scope:** [Your drafted statement]

**Out of Scope:**
- [Topic 1 not covered]
- [Topic 2 not covered]
- [Topic 3 not covered]
- [Topic 4 not covered]
- [Topic 5 not covered]

Does this accurately capture the boundaries of your BrainLift? Any adjustments needed?
```

Iterate on the Purpose statements until the user approves them.

### Step 3: Research Experts

Use the WebSearch tool to find 5 experts relevant to the user's topic. Search strategically:
- Search for "[topic] experts"
- Search for "[topic] thought leaders"
- Search for recent articles/papers on the topic to identify authors
- Look for people active on Twitter/X, blogs, and conference talks

For each expert, gather:
- **Name**: Full name
- **Who**: Title, company/affiliation, role (1 sentence)
- **Focus**: 3-5 key areas or concepts they specialize in
- **Why Follow**: Specific connection to THIS BrainLift topic (not generic expertise)
- **Where**: 2-4 links (Twitter/X, website, primary platform)

Present your findings:
```
I've identified 5 experts for your BrainLift:

1. **[Expert Name]**
   - Who: [Title/Company]
   - Focus: [3-5 key areas]
   - Why Follow: [Specific relevance to your topic]
   - Where: [Links]

[Repeat for all 5 experts]

Do these experts align with your research needs? Should I search for anyone else?
```

Allow the user to request changes or approve the expert list.

### Step 4: Research Articles

Use the WebSearch tool to find 3 recent articles that take different positions on the user's key question. Search strategically:
- Search for "[key question]"
- Search for "[topic] 2024" or "[topic] 2025" to find recent content
- Look for articles from different sources (academic, industry, blog posts)
- Prioritize articles with specific viewpoints or opinions

For each article, identify:
- **Title**: Full article title
- **Author/Organization**: Who wrote it
- **Publication**: Where it was published
- **Year**: Publication year
- **URL**: Direct link
- **Perspective**: Brief description of the position it takes

Present your findings:
```
I've found 3 recent articles taking different positions on "[key question]":

1. **[Article Title] - [Author] / [Publication] ([Year])**
   - Perspective: [Brief description of stance]
   - Link: [URL]

2. **[Article Title] - [Author] / [Publication] ([Year])**
   - Perspective: [Brief description of stance]
   - Link: [URL]

3. **[Article Title] - [Author] / [Publication] ([Year])**
   - Perspective: [Brief description of stance]
   - Link: [URL]

Do these articles provide diverse viewpoints on your key question?
```

Allow the user to request different articles or approve the selection.

### Step 5: Create BrainLift Directory and File

Once all information is approved:

1. **Check if brainlift/ directory exists**:
   - Use Bash tool: `ls -la brainlift 2>/dev/null || echo "Directory does not exist"`

2. **Create directory if needed**:
   - Use Bash tool: `mkdir -p brainlift`

3. **Generate filename**:
   - Convert topic to lowercase kebab-case slug
   - Format: `[topic-slug]-brainlift.md`
   - Example: "AI Agent Orchestration" → `ai-agent-orchestration-brainlift.md`

4. **Create the BrainLift file** at `brainlift/[filename].md`

### Step 6: Populate BrainLift File

Write the BrainLift file following the exact format from brainlift-methodology.md:

```markdown
- **==Owner(s)==**
  - [User's name or "Your Name"]
- **==Purpose==**
  - **In Scope:** [Approved in scope statement]
  - **Out of Scope:** [List of approved out of scope items]
- **==DOK4 - Spiky Points of View==**
  - [Placeholder: After researching sources, add 3-5 controversial but defensible claims (2-4 sentences each, 50-100 words). Each should be bold titled statement followed by evidence and implications.]
- **==DOK3 - Insights==**
  - [Placeholder: After analyzing multiple sources, add 8-12 synthesized insights (1-2 sentences each, 20-50 words). Format: **[Insight Title]** - [Statement]]
- **==DOK3 - Blueprints==**
  - [Placeholder: After developing insights, create operational guides. Each blueprint should include: Domain Context, Actions, Tools/Systems, Judgment Boundaries, and QC/Definition of Done]
- **==Experts==**
  - **[Expert 1 Name]**
    - Who: [Title/Company/Role]
    - Focus: [3-5 key areas]
    - Why Follow: [Connection to this BrainLift]
    - Where: [Links]
  - **[Expert 2 Name]**
    - Who: [Title/Company/Role]
    - Focus: [3-5 key areas]
    - Why Follow: [Connection to this BrainLift]
    - Where: [Links]
  - **[Expert 3 Name]**
    - Who: [Title/Company/Role]
    - Focus: [3-5 key areas]
    - Why Follow: [Connection to this BrainLift]
    - Where: [Links]
  - **[Expert 4 Name]**
    - Who: [Title/Company/Role]
    - Focus: [3-5 key areas]
    - Why Follow: [Connection to this BrainLift]
    - Where: [Links]
  - **[Expert 5 Name]**
    - Who: [Title/Company/Role]
    - Focus: [3-5 key areas]
    - Why Follow: [Connection to this BrainLift]
    - Where: [Links]
- **==DOK2 - Knowledge Tree==**
  - **==Category 1: [Thematic Category Name]==**
    - **==Section Summary==**
      - [Placeholder: After adding sources to this category, write 2-4 sentences synthesizing all sources in this category]
    - **[Article 1 Title] - [Author/Organization] / [Publication] ([Year])**
      - **==DOK2 Summary==**
        - [Placeholder: Write 4-5 sentences (80-150 words total) synthesizing the main argument, evidence, and implications from this source]
      - **==DOK1 Facts==**
        - [Placeholder: Extract atomic knowledge units from the source. Each fact should be 15-25 words, max 35. Use simple bullet points, no numbering, no titles. Prefer 1 sentence per fact, up to 3 for complex concepts]
      - Link: [URL from research]
    - **[Article 2 Title] - [Author/Organization] / [Publication] ([Year])**
      - **==DOK2 Summary==**
        - [Placeholder: Write 4-5 sentences (80-150 words total) synthesizing the main argument, evidence, and implications from this source]
      - **==DOK1 Facts==**
        - [Placeholder: Extract atomic knowledge units from the source]
      - Link: [URL from research]
    - **[Article 3 Title] - [Author/Organization] / [Publication] ([Year])**
      - **==DOK2 Summary==**
        - [Placeholder: Write 4-5 sentences (80-150 words total) synthesizing the main argument, evidence, and implications from this source]
      - **==DOK1 Facts==**
        - [Placeholder: Extract atomic knowledge units from the source]
      - Link: [URL from research]
```

### Step 6.5: QC - Remove Empty Lines

After creating the BrainLift file, run a quality check to remove any empty lines for Workflowy compatibility:

1. **Run QC command** to remove all empty lines:
   - Use Bash tool with the following command:
   ```bash
   grep -v '^$' brainlift/[filename].md > brainlift/[filename].tmp && mv brainlift/[filename].tmp brainlift/[filename].md
   ```
   - Replace `[filename]` with the actual generated filename
   - This ensures the file has no empty/spacer lines

2. **Verify file structure**:
   - Confirm file was updated successfully
   - Check that all content is preserved (only empty lines removed)

**Why this matters:** Workflowy requires no empty lines for proper copy/paste functionality. Empty lines that are useful for readability in editors cause formatting issues in Workflowy.

### Step 7: Confirm Completion

After creating the file and running QC, present confirmation to the user:

```
✓ BrainLift created successfully!

**File Location:** `brainlift/[filename].md`
**Format:** Optimized for Workflowy (no empty lines)

**What's Been Populated:**
- Owner (placeholder for you to update)
- Purpose (In Scope / Out of Scope)
- Experts (5 profiles with links)
- Knowledge Tree structure (3 sources as starting points)

**Next Steps:**
1. Update the Owner field with your name
2. Read the 3 articles I found and extract DOK1 facts and DOK2 summaries
3. As you add more sources, organize them into thematic categories
4. Once you have 4+ sources, start synthesizing DOK3 Insights
5. When you have strong opinions from 5+ sources, draft DOK4 Spiky Points of View
6. Create DOK3 Blueprints to operationalize your insights

**Tips:**
- Follow the DOK1/DOK2 formatting rules exactly (see brainlift-methodology.md)
- Build bottom-up: DOK1 → DOK2 → DOK3 → DOK4
- Present top-down: DOK4 → DOK3 → DOK2 → DOK1
- Keep Grade 12 reading level (15-25 words per DOK1 sentence)
- Use `**==Section Headers==**` format (bold + double equals)

Would you like help extracting DOK1 facts and DOK2 summaries from these articles?
```

## Important Guidelines

### 1. Formatting Rules (CRITICAL)

Follow brainlift-methodology.md formatting exactly:

- **Section headers**: Use `**==TEXT==**` (bold + double equals)
  - Example: `**==DOK2 Summary==**`
  - Example: `**==Experts==**`
- **NO markdown ## headers** in the Knowledge Tree
- **Simple bullet points** throughout (no numbering in DOK sections)
- **Plain language**: Grade 12 reading level
  - DOK1: 15-25 words per sentence, 35 max
  - DOK2: 4-5 sentences, 80-150 words total

### 2. Research Quality

- **Experts**: Find real, identifiable people with actual expertise and active presence
- **Articles**: Find actual published articles with URLs, not hypothetical sources
- **Diversity**: Ensure experts and articles represent different perspectives
- **Recency**: Prioritize recent content (2024-2025) for the articles
- **Relevance**: Every expert and article must directly relate to the specific topic

### 3. Interactive Approach

- **One question at a time**: Don't batch all questions together
- **Wait for approval**: Get user buy-in on Purpose, Experts, and Articles before proceeding
- **Allow iteration**: Be ready to research different experts or articles if requested
- **Confirm before creating**: Show the user what will be created before writing the file

### 4. File Structure

- **Directory**: Always use `brainlift/` folder in the project root
- **Filename**: Use kebab-case slug from topic + `-brainlift.md`
- **Template compliance**: Follow the exact structure from brainlift-methodology.md
- **Placeholder guidance**: Make placeholders descriptive so user knows what to add

### 5. What NOT to Do

- **Don't create DOK4 content**: This requires deep synthesis after many sources
- **Don't create DOK3 content**: This requires pattern recognition across sources
- **Don't fill in DOK2 summaries**: User should read the sources and extract these
- **Don't fill in DOK1 facts**: User should extract atomic knowledge from sources
- **Don't use numbered bullets** in DOK sections (DOK1-001, etc.)
- **Don't use ## headers** in the Knowledge Tree section

### 6. Workflowy Compatibility

**No Empty Lines**: The generated BrainLift file contains NO empty or spacer lines for Workflowy compatibility.

**Why This Matters**:
- Workflowy requires continuous lines for proper copy/paste functionality
- Empty lines useful for readability in editors cause formatting issues in Workflowy
- The QC step (Step 6.5) ensures all empty lines are removed after file creation

**QC Process**:
- Template in Step 6 is designed without empty lines between sections
- Step 6.5 automatically runs a bash command to strip any remaining blank lines
- Command: `grep -v '^$'` filters out all empty lines
- Preserves all content, only removes spacing

**Manual Verification** (if needed):
- Open the generated file and visually check for blank lines
- Run: `grep -c '^$' brainlift/[filename].md` (should return 0)
- If empty lines found, re-run the QC command from Step 6.5

### 7. Success Criteria

The command is successful when:

1. ✓ User has provided topic, interest statement, and key question
2. ✓ Purpose statements (In Scope / Out of Scope) are approved
3. ✓ 5 real experts with complete profiles are found and approved
4. ✓ 3 diverse articles with URLs are found and approved
5. ✓ `brainlift/` directory exists
6. ✓ BrainLift markdown file is created with correct filename
7. ✓ File follows exact formatting from brainlift-methodology.md
8. ✓ All required sections are present with appropriate content or placeholders
9. ✓ File has no empty lines (Workflowy compatible)
10. ✓ User understands next steps for populating the BrainLift

## Notes

- This command creates the **initial structure** of a BrainLift document
- The user will need to read sources and extract DOK1/DOK2 content separately
- DOK3 and DOK4 content comes much later after substantial research
- The BrainLift methodology emphasizes building bottom-up (DOK1→DOK2→DOK3→DOK4) but presenting top-down (DOK4→DOK3→DOK2→DOK1)
- Each BrainLift is a living document that evolves as the user learns more about the topic
