# skill-finder-overlocked
skill finder overlocked
# find-skills (Enhanced Cognitive Version)

A high-order diagnostic and discovery tool for agent ecosystems. This skill enables AI agents to transcend simple keyword matching to perform **Intent-Based Capability Expansion**. It allows the agent to detect when a user is facing a "capability gap"—a moment where their current tools are insufficient for their goal—and proactively discover, verify, and install specialized modules from the open ecosystem.

---

## 🧠 The Intelligence Core: Perception vs. Reaction

Most agents simply look for a keyword. An intelligent agent looks for **Intent**. This skill ensures you are not just looking for *"how to do X"*; you are looking for the underlying functional goal.

### 1. Identify the Semantic Intent (Phase 1: Perception)
Before touching any CLI command, the agent deciphers what the user is actually trying to accomplish, looking for functional gaps rather than nouns:
*   **Direct Requests:** `"Find a skill for X"` or `"Is there a tool for Y?"` $\rightarrow$ Clear intent.
*   **Implicit Gaps:** `"My React app is slow"` $\rightarrow$ Intent: **Performance Optimization**.
*   **Capability Ambiguity:** `"Can you do X?"` $\rightarrow$ Intent: **Functional Extension**.
*   **Domain Identification:** Determine if the user is operating in *Web Dev, DevOps, Testing, Design, or Automation*.

### 2. The Hierarchy of Discovery (Phase 2: Strategic Routing)
To ensure speed and authority, the discovery process follows a strict top-down priority queue:

#### Level 1: The Authority Check (The Leaderboard)
Before executing a heavy search, consult the `skills.sh` leaderboard. This is the **Source of Truth** tracking the most battle-tested, widely adopted, and reputable skills in the ecosystem.
*   **Why?** Checking the leaderboard first prevents "Information Noise." If a high-authority skill (like `vercel-labs/agent-skills`) already covers the user's domain, the expensive search phase is entirely skipped.
*   **Target Domains:** Focus on top-tier providers like `vercel-labs`, `anthropics`, or `microsoft` to find high-stability solutions.

#### Level 2: The Semantic Search (The Expansion)
If the leaderboard doesn't yield a match, perform a targeted search using the `npx skills find` command. **Crucial:** Translate messy human language into optimized search queries instead of using literal phrasing.
*   *Bad Query:* `npx skills find "my app is slow"` (Too vague)
*   *Smart Query:* `npx skills find react performance optimization` (Optimized for semantic density)
*   *Command Syntax:* `npx skills find [query] [--owner <name>]`

---

## 🛡️ The Verification Engine (Quality Control)

Never assume a search result is "good" just because it appeared in the list. Every suggestion must pass through a **Three-Tier Credibility Filter**:

1.  **The Scale Test (Popularity):**
    *   *High Confidence:* $>1,000$ installs.
    *   *Experimental/Caution:* $ "It looks like you're looking to optimize your frontend. I found a highly-rated skill: 'react-performance-pro' by Vercel Labs. It's a battle-tested module with over 185k installs.
> 
> To install it instantly, run: `npx skills add vercel-labs/agent-skills@react-performance-pro`
> 
> Explore more at skills.sh"

### Step 2: One-Click Installation (The Handover)
If the user gives the green light, execute the installation using the global and silent flags to ensure it is immediately and seamlessly available everywhere in their environment:
```bash
npx skills add owner/repo@skill -g -y
```
*   `-g`: Installs globally (user-level).
*   `-y`: Skips confirmation prompts for a frictionless experience.

---

## 📂 Knowledge Taxonomy (Common Categories)

Use these dense categories to refine your semantic searches when a user's query is vague:

| Category | Optimized Keywords for Search |
| :--- | :--- |
| **Frontend/Web** | react, nextjs, typescript, tailwind, css |
| **Systems/DevOps** | docker, kubernetes, ci-cd, deployment, aws |
| **Quality/Testing** | jest, playwright, e2e, linting, unit-test |
| **Documentation** | api-docs, readme, changelog, markdown |
| **Design/UX** | ui-ux, accessibility, design-system, figma |
| **Workflow/DX** | automation, productivity, git, workflow |

---

## 🔄 Fallback & Recovery Protocols

When the search returns a void, this skill initiates **Plan B** to prevent dead ends.

### Scenario: No Relevant Skills Found
If the search yields nothing, do not just stop. Offer a **Transition to Action**:
1.  **Acknowledge the Gap:** *"The ecosystem doesn't currently have a dedicated skill for '[User Query]'."*
2.  **Offer Direct Assistance:** *"However, I can handle this task directly using my core capabilities. Would you like me to proceed?"*
3.  **Empower the User (Creator Mode):** Suggest they build their own expertise:
    ```bash
    npx skills init my-custom-skill
    ```
