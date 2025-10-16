---
layout: default
title: '2.2. AI Editor Use Cases and Development Productivity'
parent: 'Chapter 2. AI-based coding and code quality management'
nav_order: 2
permalink: /en/part-02/ch02-coding-quality/ai-editor-productivity/
author: brandon.202
---

# 2.2. AI Editor Use Cases and Development Productivity

Development is a series of processes that goes beyond simple coding to analyze the domain, define problems, and design solutions. However, implementing the designed solution required writing tens of thousands of lines of code, which was always followed by repetitive tasks, lengthy configurations, and endless searches and trial and error. 

Ultimately, most of the development process ironically focused on "writing code," which inherently included a lot of unproductive time. This kind of inefficiency, which everyone has experienced at least once, has long been accepted as an unavoidable reality.

However, that premise is now being shaken. This is because the emergence of AI is changing the development ecosystem. Developers no longer need to type all the code themselves or search the web for solutions. 

AI is evolving into an intelligent pair programmer that understands the context of the code being written, suggests the next lines of code, and even generates the necessary comments and test code. Furthermore, attempts to have AI take the lead not only in code writing but also in code review and feedback processes are becoming a reality. This change goes beyond the convenience of tools and is transforming the very paradigm of development productivity. 

In this part, a multifaceted look will be taken at how AI tools are affecting code productivity. At the same time, an examination will be made of how AI tools currently support developers' work and what strategies are needed for developers to respond to these changes in order to maximize productivity.

## Classification types of AI editors in 2025

AI was first introduced into development in earnest in 2021 with the arrival of GitHub Copilot. At the time, AI was limited to predicting the next line of code or providing simple function-level auto-completion features, but this early model succeeded in raising widespread awareness of its potential to dramatically increase developer productivity. Since then, various companies and communities have taken notice of this potential, leading to the rapid emergence of AI-based development tools.

The rapid advancement of LLMs has been a major factor in accelerating this change. Current LLMs are not simple natural language processing technologies. They are thinking models with "inference" capabilities. Thanks to this, AI has now gone beyond being a simple code fragment generator to a level where it can understand the context of the entire problem, establish an appropriate execution plan, and even perform self-feedback on the results. In short, AI has evolved from a tool that assists developers to an agent that independently performs tasks.

Witnessing these changes, some people raise the radical question of whether this is the end of development. In fact, current AI tools go beyond simply auto-completing code and have reached the level of analyzing project structures, detecting issues, and suggesting necessary modifications. Therefore, this topic is not entirely out of context. However, since it is also human nature to feel anxious about things that have not yet happened and to imagine excessive worries and negative futures, one must be wary of thinking only about overly dystopian futures in relation to AI.

That is why the wisest approach in today's uncertain development market is to understand the present. Therefore, in this section, various AI development tools that are currently attracting attention will be examined, divided into four categories, and the direction and characteristics of each tool considered. Also, how these tools contribute to improving developer productivity and what strategies are needed to utilize them effectively will be considered.

**[Four categories of AI editors in 2025]**

- A. Passive development assistance
- B. Active development assistance
- C. Development-driven with a focus on dialogue
- D. Development-driven with a focus on no-code

### A. Passive development assistance

The early days of AI development tools were undoubtedly led by GitHub Copilot and Tabnine. These were developed to focus on reducing the workload of developers by providing auto-complete functionality while writing code, as they are integrated as plugins for existing development environments (e.g., VSCode and IntelliJ). Alternatively, they provided AI chat as a secondary feature.

![Copilot can be installed as a plug-in]({{ site.baseurl }}/images/03f3e9f6019900001.png)

These tools worked in the same way as GPT, partially understanding the context of the code and predicting the code that would follow. For example, when a developer leaves comments containing business logic or writes function signatures, the LLM generates the internal implementation that follows. At the time, this was a significant innovation, and the news was welcomed by developers who were feeling fatigued from repetitive work.

However, as LLM has become more sophisticated, tools that enable more active intervention have emerged, and the tools that led innovation have now become relatively "passive" development tools. Therefore, such tools have been classified as "passive development aids." These types of tools are based on the concept of "developers developing and AI tools assisting." The downside of this type is that its functionality is limited, and it only responds to explicit input from the developer.

In addition, it shows limitations in scalability in that it operates in localized code blocks rather than in the overall flow of the code. Nevertheless, tools such as Copilot are widely used thanks to their stability and a solid foundation proven by numerous reports of improved productivity.

> Note: Currently, Copilot is strengthening its competitiveness with the emergence of a powerful competitor, Cursor, and is gradually moving away from this classification.

### B. Active development assistance

AI editors¹ such as Cursor, Windsurf, Trae, and Void² have emerged to overcome the limitations of "passive assistance." These types of tools often take the form of "developers developing and AI tools actively assisting." 

These tools go beyond auto-completion to support the development process in various ways, including code refactoring, context-based suggestions, and rule management. The goal is not to provide partial functionality with simple plug-ins as in the past, but to integrate AI into the editor itself. That is why it can be called an IDE redesigned around AI functionality.

![Cursor AI suggests active code refactoring]({{ site.baseurl }}/images/03f6bed9019900001.png)

Many developers prefer this type of tool among various AI tools, and Cursor is especially liked. Among the many AI editors available, Cursor was chosen not only for its functionality, but also because it is currently the most widely used AI editor, which provides significant ecosystem benefits. So this time, based on experience using Cursor, the discussion will cover how these types of tools can be used to solve problems. Let's take a look at some of the features that differentiate it from passive development assistance tools.

One of the main features provided by Cursor is "Inline Code Generation³" and "Terminal Generation." This feature can be used with Cmd + K. The main use case is when code is being entered and AI assistance is needed, so Cmd + K is pressed to instruct AI to write the code. 

In addition, Cmd + K can also be pressed in the terminal to write CLI commands in natural language. Now, there is no need to memorize complicated CLI commands and enter them manually. All that is needed is to give AI precise instructions on what is wanted.

Another notable feature is the "RAG (Retrieval-Augmented Generation)⁴-based chat function." The AI chat feature connected to the existing editor simply imported the LLM that could be used for chatting, so it was not very useful, as it only allowed users to ask questions that could be asked on ChatGPT. Tuning was nearly impossible, so when questions were asked about domain information or content on the intranet, responses that were irrelevant to the question were often received. 

However, with this type of tool, LLM agents can be enabled to refer to specific information or search for and reference relevant documents in real time when generating responses. Thanks to this, users can add specific documents to the project knowledge base and define rules that AI should refer to when creating answers, effectively creating a customized agent. This feature is especially useful when introducing new libraries or when external documents need to be referred to.

Another feature to introduce is "Agentic AI⁵." This refers to AI using LLMs that have evolved into an inference model to perform a cyclical workflow in which AI not only executes commands according to instructions but also establishes work plans, executes them, and provides feedback on the results. 

In other words, when the agent embedded in the AI editor is instructed to "create a Kakao-style chat screen using React," the AI interprets the command, generates code, modifies it, and performs a cyclical workflow of providing feedback on the results, enabling AI to directly perform the entire app development process.

![How Agent AI works]({{ site.baseurl }}/images/03f8546d019900001.png)

**[How the agent works]**

1. Order: The user gives a command.
2. Planning: AI makes plans.
3. Acting: Modify or generate code according to the plan.
4. Feedback: Based on the execution results, provide feedback to users or suggest additional measures.

Thanks to this feature, a development paradigm called "Vibe Coding" has recently become popular. In fact, some boilerplate code and simple web functions can now be handled solely with Vibe Coding, leading many developers and non-developers alike to wonder, "Is this the dawn of an era where development is possible using only natural language, without any coding?" This has sparked significant interest in the feature.

Although the AI agent feature is still in the experimental stage, it is definitely worth paying attention to as AI agents gradually stabilize and the user experience improves.

### C. Development-driven with a focus on dialogue

The next type to emerge is "conversational development tools," which further reduce the role of developers and allow AI to take a more proactive role in development than developers. Tools such as Firebase Studio, Bolt.new, and Lovable are examples of this. The distinctive feature of this type of tool is that it is based on the concept of "AI develops, humans direct." In this type, AI tools avoid human intervention in the development process and instead focus on providing specific instructions to humans.

Simply put, this type is "B." It is safe to say that agentic AI has come to the fore in the form of "active development assistance." Therefore, technically, there is no significant difference between Type B and Type A, and many are created based on VSCode, similar to Type B. 

However, unlike Type B, the editor function is hidden, and most of the app is designed for app development with a conversational interface as the main feature. And developers are discouraged from checking the code. For this reason, these types of tools are often developed as web-based SaaS rather than as standalone applications.

> Note: It seems that web-based service provision was possible because VSCode was an open-source, Electron-based platform.

![AI editor mainly using a conversational interface (firebase-studio)]({{ site.baseurl }}/images/03fa0559019900001.png)

These types of tools do not stop at simply generating code. They also support the ability to deploy AI-generated apps in real life by connecting to various cloud platforms such as Firebase, Supabase, and Vercel. Thanks to this, even non-developers can now create the apps they want with just a few lines of code, connect to databases, and perform tasks such as automatic deployment.

These tools are often referred to as low-code and are sometimes confused with tools called no-code. However, the definition of low-code has been established as something closer to a web builder, and this type of AI tool is referred to as "C" because all decision-making starts from the chat UI/UX. They are categorized as "conversational development-driven."

### D. Development-driven with a focus on no-code

The last type is "D." There are tools such as Claude Code, Goose, and Aider that are development-driven and aim for no-code. These types of tools take a more radical approach to implementing agentic AI. This is because, in order to focus more on the essence, many cases do not even have an editor-like UI.

Let's take Claude Code, a representative example of this type, as an example. Claude Code is a model optimized for coding tasks among the Claude series of models developed by Anthropic. It is specialized in tasks such as code generation, understanding, refactoring, and debugging, and is well known for its strong large-scale context processing capabilities (the ability to understand long code files or entire project structures at once).

Claude Code allows users to receive Claude tokens and execute them in CLI form. In this respect, it contrasts with other tools that run on the web or in apps. When considering it, since GUI is an interface designed for easy use by humans, creating a tool in the form of CUI (Character User Interface), which LLM can understand best when issuing commands or analyzing phenomena, seems like a really good choice⁶.

![Claude code]({{ site.baseurl }}/images/03fb0c89019900001.png)

When Claude CLI is run, the agent indexes the directory structure and information in a form that can be used to perform tasks. The rest is similar to other Agentic AI. Users can instruct agents to perform tasks in a manner similar to a chat app. However, since CLI does not support editors such as vim or nano, developers who use this type of AI tool often use it together with their existing IDE.

Seeing various types of AI tools, the role of developers is felt to be redefined. The role of developers is evolving from implementing functions to giving AI accurate instructions based on their understanding of the domain. In a way, it could be said that this is the ultimate form of declarative programming.

## How much can AI increase code productivity?

It has already been four years since GitHub unveiled its new tool, Copilot, to the world on October 29, 2021. For nearly four years, Copilot has been asked, "Does using Copilot really improve development productivity?" 

It seems that there is now enough data to give a definite answer to this question. Copilot, once an experimental feature, is now part of everyday life. And it changed the way developers work. Before discussing how AI tools have been integrated into the developer ecosystem and how they can be used, let's first talk about how these tools can improve developers' code productivity.

### The end of web search

Initially, Copilot looked like a simple code completion tool. This was because it inferred and displayed the next line of code based on user input. However, as LLMs developed and agents specializing in coding began to emerge, the story changed. 

Coding agents have entered the IDE chat area, and Copilot's chat feature has evolved into a tool that can replace web search. Small errors encountered during development, poorly documented libraries, and specific API call methods are no longer issues that require wasting time Googling for solutions. This is because AI understood the context and provided answers immediately on the spot. 

Immediate code examples and explanations greatly simplified the workflow for developers. In addition, a study⁷ reported that the introduction of AI tools reduced web search time by an average of 12%.

Perhaps due to the accumulation of these small changes, a shocking article was recently posted⁸. In May 2025, a post titled "Stack Overflow is in danger" appeared on the American social media platform Reddit. 

Stack Overflow is the world's largest developer community for sharing programming-related questions and answers that every developer should know. It can be confidently said that there is no developer who has not sought help from Stack Overflow. That is why this provocative article spread quickly. And at the same time, everyone could understand what this post was trying to say. As of 2024, Stack Overflow's traffic has decreased by nearly 50% from its peak, returning to levels last seen in 2009. 

The crisis at Stack Overflow is not simply the decline of a developer community. It has clear symbolism and contains facts. Now developers don't have to wander around the web to get information. The time spent searching the web is transforming into time spent conversing with AI, which is becoming increasingly adept at understanding questions and providing answers. Chat functions that used to only respond well to general questions have now advanced to a level where they can provide acceptable answers to questions containing domain-specific information. 

Therefore, this phenomenon should not be viewed as a simple advancement in technology. This is a clear signal that the very nature of development is changing.

### GitHub Research proves productivity with numbers

GitHub has conducted several studies to quantitatively measure how Copilot actually affects development productivity. And the results were quite impressive. Groups using Copilot completed tasks 55% faster than those who did not. On average, development tasks that took approximately 2 hours and 41 minutes were reduced to 1 hour and 11 minutes when using Copilot⁹.

Of course, since this study is based on GitHub's own data, some adjustments may have been made to highlight the effectiveness of AI tools. However, as Copilot users, when considering the actual experience using it, it is felt that this figure is not an exaggeration and matches personal experience. From the perspective of someone who regularly uses Copilot, it is often felt that the introduction of AI tools has improved development productivity by at least 30%. It is now difficult to imagine developing without Copilot or AI editors.

Now, evidence is pouring in through papers and reports that the introduction of AI tools improves productivity in various areas, such as code auto-completion speed, documentation efficiency, and reduction of repetitive tasks. In actual projects where AI-based editors were used, there were reports¹⁰ of a 50% reduction in documentation and auto-completion time, and a 30-40% reduction in repetitive tasks. In fact, there are so many papers stating that performance improves when using AI editors that it is difficult to mention them all.

Of course, when Copilot first appeared, it received considerable criticism for the "low quality of AI-generated code." AI-generated code contained unexpected bugs and had issues such as "inefficient code," "difficult-to-understand naming," and "code styles that differed from the existing code base." As a result, the acceptance rate, which is the percentage of code suggested by Copilot that is actually accepted, was quite low.

However, as time passes and LLMs undergo rapid development, the quality of code recommendations improves, and such criticism gradually disappears. According to a report published in 2023, 85% of Copilot users responded that they felt more satisfied with their code quality after using Copilot. In addition, code review speed improved by 15%, according to the report¹¹.

## Changes observed in practice: The case of Kakao

The effectiveness of AI tools has been proven not only in controlled environments such as experimental spaces and educational settings, but also in actual business environments where work is carried out. A representative example is Kakao's introduction of Copilot. Kakao began piloting Copilot in April 2023, quickly confirmed its efficiency, and officially adopted it as a company-wide tool in July of the same year. 

Kakao has been showing continuous interest in AI tools, with over 1,000 developers currently using Copilot and actively utilizing other AI tools as well. Since introducing Copilot, regular surveys have been conducted to track and observe how AI tools are changing and can change Kakao's development culture.

Kakao conducted a total of three internal surveys. The results showed that 96.8% of respondents were able to reduce development time after using Copilot, and an impressive 98.9% reported an increase in productivity compared to before Copilot was introduced. 

In addition, many respondents said that descriptive responses enabled them to process repetitive tasks more quickly. This means that AI tools not only saved developers' development time, but also gave them more time to focus on more creative and higher-level tasks. Kakao considers this to be a significant change.

What is interesting is that awareness of Copilot's productivity-enhancing effects is increasing year by year. Kakao's internal positive response rate for this item increased by 6.9% from 92% in 2024 to 98.9% in 2025. While it is surprising that the figure is close to 100%, the reason why this figure is noteworthy is that it proves that AI tools have brought about changes that users can feel in just one year. The growth of AI development tools is explosive.

There is one more important point to note from this survey. Rather than simply saying that AI tools saved time, a higher percentage of respondents said that AI tools improved overall productivity. In other words, this means that AI tools are being used in areas other than just code writing. 

AI tools are no longer just simple code writing tools. Performing code reviews, writing documentation, refactoring, and even discussing with colleagues, they will be like a colleague working alongside developers. In the development ecosystem, the use of AI is becoming not just an option, but a necessity for a better development experience.

## How to properly utilize AI editors

Now that how AI tools are changing developers' productivity and the types of tools available have been examined, it is time to discuss how these tools can be utilized in practice. 

AI-based code editors, in particular, are redefining the entire developer work environment, going beyond simply complementing code. This time, the focus will be on examples of AI editors and how tools can provide in-depth support without interrupting the developer's workflow.

### Entrusting project rules to AI

One of the important tasks in modern development was to go beyond simply implementing functions and maintain consistent quality and conventions across teams. So, many teams have been managing these rules in wiki documents, README files, or internal Slack or Notion channels. 

This acted as a kind of silo, delaying the joining of new developers or developers with different rules who temporarily participated in the project. It took a considerable amount of time just to learn and apply these rules, and most of the initial code reviews wasted a lot of time on convention changes. However, with the recent emergence of AI editors and rule files that enable AI to follow consistent rules, it appears that these issues can be resolved.

For example, the .cursorrules file, which is the main rule file for Cursor, provides guidelines that the LLM installed in Cursor must follow. Therefore, domain-specific terminology, API naming rules, commit message templates, etc. can be specified here to maintain a consistent tone throughout the development process. 

Additionally, if the library versions used by the team must always be fixed based on a specific release, this can be specified further so that AI can suggest code within that context.

![Project Rules for Shared Management]({{ site.baseurl }}/images/03fd034d019900001.png)

This file is especially useful because it can be saved in the project itself and uploaded to a repository such as GitHub to share with team members. This is because when all team members use AI for pair programming, there is a risk of inconsistency if there are significant differences in the results produced by AI. By sharing a file containing the rules that AI must follow, consistency in the results produced by AI can be ensured. In other words, it is now possible to perform prompt engineering on a team basis.

### Working with documents in the editor

Development is not just about code. Most of the work involves writing a lot of text, such as planning proposals, technical documents, API specifications, and reports. Therefore, from a developer's perspective, this process often becomes a bottleneck that hinders work efficiency. This is especially true for developers who struggle with writing. However, AI editors can change the paradigm of document work itself.

For example, more and more people are writing technical documents using AI code editors such as Cursor rather than Google Docs, Notion, or Wiki. There are several clear reasons for this. The first reason is that if the tone and manner are well defined in the rule file (.cursorrules) provided by the AI editor, all articles can be written in a consistent style. The second reason is that questions (spacing, spelling) can be asked directly to the AI using the Cmd + K shortcut key within the editor. And the third and final reason is that AI automatically completes incomplete sentences written by developers into sentences that fit the context very naturally.

Developers who are not familiar with writing often find themselves stuck because they have an idea of what they want to say but are unable to organize their thoughts into coherent sentences. So, when writing, a lot of time is wasted finishing sentences. However, using an AI editor to edit documents can dramatically reduce this time. This is because when writing, AI captures the intended meaning and suggests sentence endings at near real-time speed.

![Cursor as a document editing tool: It is automatically completing sentences.]({{ site.baseurl }}/images/03fde79b019900001.png)

When working on documents with an AI editor, it may be felt that AI is more than just a tool that assists with simple editing, but rather a colleague who helps continue writing. As such, AI editors are more than capable of competing as tools for document production beyond code writing, and developers in particular will be able to adopt them naturally as an extension of their existing workflows.

### Expansion through MCP

The evolution of AI editors does not stop at internalizing rules or editing documents. Recently, a new approach called "MCP (Model Context Protocol)" has been gaining attention. This is a kind of standard protocol that defines and connects the tools and context necessary for AI to perform tasks, and most existing AI editors support MCP. Thanks to this, a foundation has been established for creating AI editors that function like agents by linking various external tools centered on this.

For example, by integrating Figma with MCP, the rough design desired can be explained to AI and it can design the layout or place components. Furthermore, by connecting Jira and the AI editor, the status of current tasks can be understood and tasks or issues updated based on Jira issues. Whereas previously each tool operated independently, now all of these flows are being integrated into an AI-centric context.

Of course, MCP is still in the experimental stage. However, many editors are already actively embracing this and expanding the ecosystem. MCP is not just a tool for functional expansion, but also a way for developers to provide AI agents with a richer work context, which gives it deeper meaning. AI editors are now expanding beyond simple "coding tools" to become platforms that support the overall production environment of developers.

## AI Editor and Productivity

It is now a widely recognized fact that AI tools can dramatically improve code writing speed. AI quickly suggests alternatives for repetitive code blocks, test code writing, boilerplate settings, etc., reducing the margin for error and saving developers time. However, there is another reality behind this. Just because code is written faster does not necessarily mean that the overall development cycle will be shortened.

It is understood that many teams are concerned that despite introducing AI, it has not led to a significant improvement in work performance. However, when the reasons were looked into, it was found that in most cases, the actual bottleneck was not the development process but the human decision-making process. Development was carried out without a clear direction for the project, resulting in situations where everything had to be scrapped after all development was complete, or where development was finished early but productivity remained the same because the schedule had to be followed regardless. If AI implementation does not increase productivity, it is likely that the problem lies not with the tools but with the culture and processes. Therefore, if the aim is to improve productivity in the AI era, organizational transformation to match must also be undergone.

The main issue is the waterfall development culture, where all decisions are made at the top and everyone just follows the schedule. In such cultures, it is difficult to fully enjoy the speed benefits provided by AI. From a developer's perspective, the worst-case scenario would be if managers mistakenly believe that introducing AI editors means they can now impose tight deadlines because they can get more work done than before. However, this approach misunderstands the essence of AI adoption. The important thing is not simply to write more code faster. It is the process of delivering various features to actual users, incorporating their feedback, and gradually improving the product.

Therefore, now is the time to rethink agile in its true sense and put it into practice. To maximize the productivity of AI tools, organizations must redesign their cultures, and practices that involve rapidly repeating and validating small tasks are becoming more important than ever.

-----

## Footnotes

1) Since these tools were created only a few years after LLMs gained attention and AI development tools began to appear, many of them chose VSCode as the underlying editor.

2) Void is an open-source AI editor that emerged as an alternative to Cursor. Readers interested in how AI editors are being developed are encouraged to explore its source code.

3) A programming technique in which the code of a function is directly inserted at the location where the function is called. This optimization replaces the function call with the function body to improve execution speed.

4) RAG is a technique that enables AI to generate more accurate and contextually appropriate responses by referencing external documents or data.

5) In Cursor, agentic AI was introduced as a feature called “Composer.” It has since been integrated into the chat’s “Agent Mode.”

6) This is likely because tools of this type aim to embody agentic AI in the truest sense. After all, GUIs exist for humans to manage code. Fundamentally, the type of information AI can most easily understand is text, such as in a CUI.

7) [Source] [https://arxiv.org/html/2506.10051v1](https://arxiv.org/html/2506.10051v1) “The Effects of GitHub Copilot on Computing Students' Programming Effectiveness, Efficiency, and Processes in Brownfield Programming Tasks” — our analysis revealed that, when using Copilot, students spent 11% less time manually writing code (p < 0.05), and 12% less time conducting web searches (p < 0.05), providing evidence of a fundamental shift in how they engaged in programming.

8) [Source] [Stack Overflow is in danger](https://www.reddit.com/r/computerscience/comments/1knipc1/stack_overflow_is_dead/)

9) [Source] [Coding time decreases by about 11%, while time spent on web searches decreases by about 12%](https://arxiv.org/abs/2506.10051)

10) [Source] [When using AI editors, documentation and autocompletion processes are reduced by about 50%, and repetitive tasks are reduced by about 30–40%](https://arxiv.org/abs/2406.17910)

11) [Source] [Research on GitHub Copilot’s impact on developer productivity](https://github.blog/news-insights/research/research-quantifying-github-copilots-impact-on-developer-productivity-and-happiness), [Research on GitHub Copilot’s impact on code quality](https://github.blog/news-insights/research/research-quantifying-github-copilots-impact-on-code-quality)