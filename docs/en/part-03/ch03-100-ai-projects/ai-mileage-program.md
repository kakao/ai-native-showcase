---
layout: default
title: '3.1. Experiments in productivity innovation: AI Mileage Program'
lang: en
parent: 'Chapter 3. Accelerate AI-native transformation: 100-person AI project'
nav_order: 1
permalink: /en/part-03/ch03-100-ai-projects/ai-mileage-program/
author: sue.cream
---

# 3.1. An Experiment in Productivity Innovation: The AI Mileage Program

After confirming the potential for one-person prototyping through agentic coding and collecting various use cases of agentic coding tasks at the individual and organizational level, the Technology Strategy team planned the “AI Mileage Program.” Developers who participated in the program were provided with credits (mileage) that allowed them to freely try various commercial AI tools (e.g., code generation AI, design prototyping AI, etc.).

The main objectives of the AI Mileage Program pilot were as follows. First, to verify at which stages of the overall workflow developers were using AI development tools and how much they improved the entire workflow. Second, to secure the know-how necessary for actual operations, such as effective utilization of AI tools and optimization of AI usage costs.

About 100 developers participated in the three-month pilot. Belonging to around 30 different organizations, they worked on more than 40 projects and used their monthly mileage allowance to freely combine different AI development tools. Participants actively used the tools and also provided feedback in various forms such as surveys, interviews, and case sharing.

## Fundamental Concerns About Introducing AI Tools

After one month of the pilot, interviews with participants revealed an unexpected pattern. Many openly admitted that, having adapted to the convenience of AI tools, they would feel significant discomfort and loss if those tools were suddenly taken away.

At that moment, a fable I had read as a child came to mind: “The Monkey’s Flower Shoes.” In the story, a monkey lived perfectly well without shoes. One day, a badger insisted they were necessary and gifted him flower shoes. Once the monkey became accustomed to their comfort, the badger demanded payment for them, and gradually the monkey became subjugated to the badger.

“Am I, perhaps, giving these developers unnecessary flower shoes, doing them a disservice?”

This concern went beyond a simple worry—it raised a fundamental question about adopting AI tools. Does the AI Mileage Program truly strengthen developers’ capabilities, or does it trap them into mere dependency on convenience?

## An Irresistible Trend, or Unnecessary Dependence?

The answer to this question came from another interview. Several participants independently expressed a shared insight:

“Development with AI is now an irresistible trend.”

If AI development tools are truly an unstoppable trend, then providing them is not handing out unnecessary flower shoes—it is helping guide a necessary transformation.

But how can we determine whether this is really an “irresistible trend”?

My conclusion was that AI tools must demonstrate tangible benefits to productivity that are real, not illusory. If developers experience improvements substantial enough to feel that working with AI has real value, then the more people share that experience, the more certain it becomes that this trend will dominate the future.

The next challenge was: how do we confirm this reality? Of course, quantitatively tracking numbers such as how much faster development becomes or how much project duration is reduced is important. But more than numbers, we needed something concrete—the collection of developers’ real-world cases. This became the conclusion: the true substance lies in the accumulation of actual developer experiences.

It may seem like an obvious conclusion, but it took considerable reflection to reach it. Yet the process of reflection was important, because the outcomes and examples shared in this chapter are tangible evidence obtained through such concerns and validation.

The results of the AI Mileage Program demonstrate that it is leading to a redefinition of the developer’s role and a fundamental transformation of organizational culture. Above all, they prove that these are not “monkey’s flower shoes,” but real outcomes that serve as a foundation for strengthening true competitiveness.

## Who Participated?

The 100 participants in the AI Mileage Program pilot came from a wide variety of organizations across the company, ranging from junior to senior levels, and across roles such as backend, full-stack, infrastructure, AI/ML, data engineering, and frontend developers. This diversity was essential to validate the effectiveness of AI tools across different backgrounds and experiences.

## Which AI Development Tools Were Chosen?

One striking feature was the participants’ active utilization of tools. On average, each used 3–4 AI tools simultaneously, showing an approach of combining the strengths of multiple tools rather than depending on a single one.

The most frequently chosen tools (excluding commonly used IDEs like IntelliJ) were Cursor and Copilot. LLMs such as ChatGPT and Gemini were also widely used, and Claude Code doubled its user base from the first to the last month, establishing itself as a mainstream development tool. API-based tools such as the OpenAI API and Claude API were also actively used.

Though combinations varied, some common patterns emerged. In the first month, the most popular set was Cursor + JetBrains + Copilot + LLM. Over time, the proportion of developers adopting Claude Code as their main tool grew the highest. In parallel, combinations such as Cursor + Claude Code also increased, showing that developers were tailoring tool combinations to their work styles and project needs.

## Productivity Improvement Metrics by Workflow Stage

Comparing survey results over 1–3 months of the program, we confirmed that as developers became more proficient in AI usage, the overall effectiveness improved. This suggests they were learning and improving their collaboration with AI.

Work was divided into six stages: (1) System Design, (2) Coding, (3) Debugging/Testing, (4) Code Review, (5) Documentation, (6) Release. Participants were asked at each stage what percentage of time was reduced through AI tool usage. The proportion of users reporting positive time savings was as follows:

**Work with clear time reduction (Month 1 → Month 2 → Month 3):**

- Coding: **93.5% → 96.7% → 98.0%** (+4.5%p)
- Debugging/Testing: **81.5% → 87.0% → 86.3%** (+4.8%p)
- System Design: **63% → 78.5% → 84.2%** (+21.2%p, significant increase)
- Documentation: **61.9% → 68.8% → 79.5%** (+17.6%p)

**Work with relatively smaller reduction (Month 1 → Month 2 → Month 3):**

- Code Review: **51.1% → 62.4% → 61.0%** (+9.9%p)
- Release: **26.0% → 31.2% → 43.1%** (+17.1%p)

The dramatic 21.2%p improvement in the “System Design” stage is highly meaningful. It shows developers learning to use AI not just as a code generator but as a design partner. In fact, many senior developers reported a pattern such as: “I discuss design with ChatGPT and delegate implementation to Claude.” Meanwhile, the smaller gains in release tasks reflect the reality that deployment pipelines are already highly automated and, for security reasons, integration with AI tools is limited.

## Developers’ Perception of AI: Building a Healthy Partnership

### Trust: A Balanced Approach

In the surveys from months 2 and 3 of the pilot, we asked participants how much they trust AI-generated code. The results show a healthy level of trust. (**Month 3**)

- Strongly trust: **3.2%**
- Trust to some extent: **51.6%**
- Neutral: **36.8%**
- Distrust: **8.4%**

Most developers neither blindly trust nor flatly distrust AI; they have formed a sound trust relationship. The fact that only 3.2% “strongly trust” may in fact be a positive sign—developers recognize AI’s limitations accurately.

Senior developers with 16+ years of experience said AI-generated code is “not yet high quality,” and that they always refactor it. Another senior developer noted that AI often produces code that violates “clean code principles,” emphasizing that human involvement is essential.

This “distrust” is not a contradiction. Rather, it reflects a professional stance that stems from clearly understanding AI’s limits. They do not accept AI output as is; they evaluate and improve it based on deep experience and expertise.

Successful AI collaborators tend to build their own verification systems. One developer said they “make a commit checkpoint whenever possible before asking AI to work,” creating a traceable workflow that enables quick rollback and issue isolation.

Meanwhile, newer users—those still getting used to AI—learn the importance of critical validation through experiences like “fully trusting AI-written code and then spending a long time chasing down the error.”

### How Developers Perceive AI’s Role: From Junior to Strategic Partner

We also asked, “What does the current AI coding agent most resemble for you?” The responses show that collaboration with AI is layered and varies widely.

| Role | Response Ratio (Month 3) | Description |
| --- | --- | --- |
| Search tool | 6.3% | Mainly used to ask questions and get small code snippets or ideas. Functions like a complement to Google Search. |
| Junior developer | 37.9% | Handles boilerplate, simple functions, data parsing—well-defined, simple/repetitive tasks. |
| Competent teammate | 27.4% | Can be trusted with independent, clearly scoped but complex tasks (bug fixes, detailed test writing, refactoring legacy code). |
| Strategic partner | 23.2% | Goes beyond implementation; discusses design direction and architectural trade-offs, serving as an intellectual sparring partner. |
| Independent agent | 5.3% | Given high-level goals and core context, autonomously plans and executes complex tasks that take hours. |

Notably, about 65% of developers view AI as “junior developer” or higher (junior + competent teammate). The 23.2% who view AI as a “strategic partner” suggests collaboration is extending beyond task delegation into decision-making.

### Dependence: Becoming an Essential Tool

We asked, “Can you develop without AI tools?” (**Month 3**)

- It’s now difficult to develop without them: **68.4%**
- Inconvenient but manageable: **31.6%**
- No problem at all without AI tools: **0%**

Two-thirds say it’s difficult to develop without AI, suggesting AI has become essential. Considering that 65% view AI as at least a “junior developer,” this dependence is natural. For the 28.5% who see AI as a “strategic partner” (23.2%) or “independent agent” (5.3%), AI is more than a tool—it’s a key teammate. Its absence can feel like losing a team member.

This dependence need not be viewed negatively. Like relying on an IDE or search engine—which doesn’t diminish capability but frees cognitive space for higher-level work—AI tools help developers escape repetitive tasks and focus on creative, strategic work.

### Different Partnerships by Years of Experience and Job Function

**Dependence by Experience: The Correlation Between Experience and Trust**

A notable finding is that the more senior the developer, the more essential AI tools are perceived to be. Developers with 16+ years of experience most strongly considered AI indispensable and reported the highest rates of >50% reduction in lead time across the development process. This implies they can accurately recognize AI’s real value.

Developers with 4–6 years of experience showed a more selective approach—recognizing utility yet maintaining that they can still function without it. This suggests a prudent stance typical of those with moderate experience who are careful about new tools.

Junior developers (1–3 years) actively used AI as a learning accelerator and gap-bridging tool—critical for acquiring new skills and adapting to work.

Perceptions of AI’s “role” also varied by years of experience. Senior developers were more likely to view AI as a “strategic partner,” using it for design discussions and architectural reviews, even involving AI in decision-making processes. Mid-level developers showed the widest variance, still finding their way. Junior developers often trusted AI at the “competent teammate” level and were building upward partnerships.

**Patterns by Job Function**

Usage strategies naturally aligned with functional characteristics. Backend developers preferred to keep stable environments (e.g., IntelliJ) and progressively integrate AI features—balancing quality and stability with productivity gains. Frontend developers leaned into repetitive UI code generation and state management automation. In AI/ML and data engineering, participants reported significant efficiency gains in model creation, test automation, and pipeline construction.

These results suggest AI-native transformation is not merely tool adoption; it requires cultural change tailored to experience level and job function. As adoption scales, success will depend on sharing examples and practices fitting each group’s needs.

## Redefining the Developer Role

The AI Mileage Program revealed a fundamental shift: developers’ roles are being redefined. It’s not just “one more tool”—the way software is made is changing.

### A New Modality: “Collaborating with AI”

**From “Writing Directly” to “Instructing and Verifying”**

As collaboration with AI matures, the developer’s role expands from “coder” to “coach”—providing clear instructions and context, then verifying the output.

One senior developer described: “I ‘discuss’ design with ChatGPT and ‘delegate’ implementation to Claude Code. I’ll ask AI to start a task before a meeting, and review the results when I return.”

This isn’t mere task splitting—it’s a shift in mindset. Developers no longer type every line; they define what to build clearly and then evaluate and improve AI-generated results as experts.

**Asynchronous Parallel Work: Treating AI as an Autonomous Teammate**

Some of the most advanced patterns involved assigning time-consuming tasks to AI and reviewing results later—treating AI as an asynchronous partner.

A 10–15 year veteran said, “I keep three sessions open and run three projects in parallel.” Another senior developer said, “The AI is doing something almost 24 hours a day; meanwhile I handle CS or other tasks.” This workflow assumes trust in AI to autonomously handle multi-hour tasks.

## New Frontiers: Challenges and Expansion

### Overcoming Technical Barriers: Leveling Knowledge Asymmetry

AI dramatically lowers the entry barrier into unfamiliar domains, expanding developers’ capability boundaries.

An infrastructure engineer with 1-3 years of experience, typically comfortable in Python/Java, contributed to open source and edited Go code with only basic knowledge—thanks to AI. It felt like “skills skyrocketing overnight.”

Cross-domain work is also becoming normal. Backend developers handle unfamiliar frontend tasks with AI, sometimes by giving a screenshot and asking AI to reconstruct the UI—slashing time. A senior developer with 10–15 years of experience said they built a TypeScript web UI “knowing nothing about it” using only AI—an “aha moment.”

### Innovation in Legacy Analysis

AI also improves legacy code analysis—a time-consuming chore. A backend developer with 4-6 years of experience had AI analyze legacy UI code to save time and invest energy in core logic instead, shifting work from repetition to higher-value activities.

## Investing Time in Quality: A Virtuous Cycle of Efficiency

### Paying Down Tech Debt

AI’s impact goes beyond speed—it creates “surplus time and energy” that can be reinvested into long-term quality.

A senior with 16+ years said productivity gains allowed them to tackle tech debt that “always sat at the bottom of the backlog” and to write thorough integration tests. The result: not only 2–3x higher productivity, but also better quality.

### Expanding Test Coverage

Another developer (4–6 years) noted that writing 100–200 tests manually is hardly feasible, but with AI they produced hundreds or thousands of lines of test code they would “never have written,” boosting stability.

### Raising the Bar for Internal Tools

A senior with 16+ years of experience developed a CLI tool for manual batch operations—and, unlike before, implemented advanced features like auto-retry because AI cut overall development time. This enabled “higher-grade” internal tools beyond “good enough.”

## The Core of Role Shift: Evolving Interaction Patterns

### From “Vague Instructions” to “Specific Decomposition”

Effective AI collaboration requires changing how we work. A data engineer initially said “please build this feature,” which led to AI getting stuck in loops. They then switched to breaking down large tasks into smaller units—“assign one → validate → proceed”—and learned to work with AI effectively.

### Dialogue as a “Design Partner”

The most mature practitioners use AI as a thinking partner, not just an implementation tool. One senior developer delegates implementation to Claude but intentionally holds deep, “nitpicky” design conversations with ChatGPT, producing ideas “far better than working alone.”

### Core Capabilities for the New Role

The AI era clarifies key competencies for developers:

- **Clear requirements definition**: Communicating precisely what you want from AI
- **Context provision**: Supplying the background AI needs for optimal results
- **Critical validation**: Judging the quality and suitability of AI output as an expert
- **Task decomposition & orchestration**: Breaking problems into AI-manageable units and integrating results
- **Asynchronous management**: Coordinating multiple AI agents and tasks in parallel

This transition does not diminish a developer’s value; it elevates the bar for expertise and creativity. As AI handles repetitive, structured work, developers focus on problem definition, architecture, quality assurance, and user experience—more strategic and creative domains. The key is not the tool itself, but **how** we collaborate with it.

## Patterns of Trial and Error: What Determines AI Effectiveness?

A key lesson from the program is that AI is not a panacea. Across 100 participants, successes and missteps show that impact depends not only on tool performance but **how** and **where** it’s used.

### Root Causes of Failure: Five Patterns

**Lack of Context: The Limits of Context-Free Requests**

The most frequent failure is not providing enough context. Participants reported “too much unnecessary logic due to missing base code context” and “many incorrect changes to long-history code, increasing re-requests and validation time.” In large codebases and legacy systems, AI often makes poor suggestions when it lacks full context. This is less an AI limitation than a user skill that must be learned: how to provide sufficient context.

**Poor Tool–Platform Integration: Limits of Isolated Tools**

Comments like “We planned in a specific tool that lacked integrated AI features,” or “We didn’t connect company release systems to AI for safety, so we avoided it,” show that when AI tools aren’t integrated into existing workflows, effectiveness is limited. It’s not just about a tool’s capability; it’s the pipeline integration that matters.

**Learning Curve and Trust: Early Adoption Friction**

Some said “setup and adaptation took more time early on,” or couldn’t switch from IntelliJ to Cursor (e.g., Kotlin). Initial learning costs can be higher than expected—especially for those who are deeply accustomed to existing environments. This is a change management issue, not just a tool issue.

**Rising Validation Costs: The Quality Assurance Dilemma**

Developers noted that review time increased because the scope of AI’s impact was unclear, and that while only dozens of lines were actually changed, hundreds of lines of AI-generated tests had to be reviewed. As AI increases output volume and complexity, new burdens emerge in review and validation.

**Already Automated Areas: Diminishing Returns**

In already highly automated areas (e.g., CI/CD), AI’s marginal benefit can be limited. This suggests we should assess current automation levels and target areas where AI can truly move the needle.

## What the Experiment Tells Us

The AI Mileage Program shows we now need to work with AI colleagues.

### From Experimental Participation to Systematic Utilization

Initially, most participants experimented individually—trying different tools and discovering their own methods. Over time, those experiments formed patterns, and success cases propagated. Word of mouth increased preference for certain tools.

### Natural Diffusion of Success Stories

Surveys indicate many learned from official docs **and** informal conversations with peers. Good practices discovered individually were shared within teams—likely including not only success stories but also failures and lessons learned.

Through this program, we observed not just 100 individual successes, but how those experiences were learned, shared, and reproduced at the team level.