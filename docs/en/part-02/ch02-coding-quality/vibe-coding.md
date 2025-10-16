---
layout: default
title: '2.1. The beginning of "Vibe Coding": Data analysis and web visualization'
parent: 'Chapter 2. AI-based coding and code quality management'
nav_order: 1
permalink: /en/part-02/ch02-coding-quality/vibe-coding/
author: zoey.fully
---

# 2.1. The beginning of "Vibe Coding": Data analysis and web visualization

Kakao strives to prevent harmful content from entering Kakao services and to maintain a safe environment. To this end, we manage every step of the process, from developing and operating content monitoring tools to planning, developing, and operating the AI/ML models used in these tools, going beyond simple harmful content classification. 

The most important and time-consuming part of this process is data labeling, which is necessary for training AI/ML models. Since model performance ultimately depends on the quality of labeled data, we strive to build evaluation sets as accurately as possible by utilizing domain knowledge (experience-based) and various metrics.

However, no matter how hard you try, there will always be things you miss in such a vast amount of data. It was common to check data mainly in numerical form or draw charts using Jupyter Notebook. 

Of course, with Python, you can create impressive visualizations and reports, but the problem was that it took an enormous amount of time to organize and share data in a visually appealing and easy-to-understand report format. Due to this inefficiency, sharing of in-depth analysis results was sometimes delayed.

There was something that always bothered us while doing data analysis work. The analysis itself was not difficult, but making the results "presentable, easy to understand, and easy to share" took more time than expected. In particular, text data such as spam messages must be analyzed from various angles to derive meaningful insights, and creating such a comprehensive analysis dashboard required a significant amount of development time.

However, Claude Code's "Vibe Coding" experience was amazing. Starting with the simple idea of "I want to visualize spam message data," we were able to build a complete 22-page web dashboard with 15 charts in just one day. In the past, this would have taken at least one to two weeks.

## Claude Code, bringing developers' imaginations to life

In this situation, seeing the recent advances in LLM coding capabilities, we suddenly thought, "With this level of technology, wouldn't it be possible to create functions that we've only imagined before in a form that anyone can easily and intuitively understand, or to implement visual reports that can be quickly shared with team members?" What used to be just ideas are now expected to become reality thanks to Claude Code.

In particular, the process of considering which statistical indicators to extract from which data types and which charts are most effective for conveying meaning is an important part of data analysis. In the past, this process took a considerable amount of time, but thanks to Claude Code, we were able to significantly reduce the time spent deliberating. 

Of course, determining which chart or statistical technique is most suitable for a specific data type requires the developer's domain knowledge and understanding of the data. However, Claude Code has proven itself by recommending the optimal analysis method based on its knowledge and dramatically reducing complex statistical concerns. Although it is not yet perfect, it has significantly reduced the time required for analysis.

## 'Vibe Coding', changing the way we develop

Even though we already had sufficient knowledge and experience, the inefficient parts that took a lot of time to turn that knowledge into actual results were solved by a new AI utilization method called "Vibe Coding." In the past, organizing data into "pretty reports" felt like another big task, but now we have gained the confidence to immediately implement ideas as soon as they come to mind. It is an amazing change that we can quickly create visualizations that our colleagues can intuitively understand and communicate with.

"Vibe Coding" has gone beyond simple code development collaboration. Claude Code also excels at creating visual materials and web pages, combining design sensibility with data analysis knowledge to produce outstanding results. This part was crucial in making it easy for the team to share information by turning complex data patterns into an intuitive UI. 

Furthermore, "Vibe Coding" is not limited to one-time data analysis. The latest report can now be automatically generated whenever data changes or model training is performed. Visually automated reporting has maximized work convenience. 

Although the results are not directly part of the main project, they are actively utilized as side projects to improve the efficiency of the main project. This plays a key role in quickly validating and developing ideas into practical applications.

The following is a specific example showing how we interacted with AI and Claude Code during the data analysis process called "vibe coding." We concretized ideas and produced results as if we were having a conversation.

- **Requirements**: We explained the overall objectives of the project and the characteristics of the data, and presented the initial direction.
- **Work Style Instructions**: We made specific requests regarding the desired style of the final product, such as "Make it an interactive 2D graph," or "Show each group in different colors."
- **Data Analysis Request**: We showed Claude Code the training data and asked for analysis.
- **Similarity Model Recommendation and Review**: We requested "Recommend a similarity model" and "Recommend a model that suits our data," reviewed the models proposed by Claude Code, and made the optimal selection.
- **Visualization Methodology Questions and Suggestions**: When asked, "What methodologies are necessary for data visualization?", Claude Code suggested various visualization configurations and then generated visualization images.
- **Additional Requirements and Implementation Discussions**: When a request was made, "We would like to add this element to the visualization," Claude Code immediately provided suggestions for implementing the additional requirements.
- **HTML Format Visualization Suggestions and Feedback**: We were asked to "propose a visualization in HTML format," so we checked the intermediate HTML file, provided feedback, and went through a revision process (e.g., error resolution tick-tack, such as UMAP error correction requests).
- **Final Revision Confirmation and Mobile Optimization**: We checked the modified HTML file and improved it to work well in mobile environments by adding a mobile menu bar as requested.
- **Distribution and Verification of Results**: We finished the project by connecting the final result to GitHub Pages and distributing it to check if it works in a real web environment.

## Six useful prompt patterns

Here are some prompt templates that have proven effective for successful vibe coding. These can be modified to suit specific needs.

1. Separate work files and result folders: "When working, organize the results in a separate folder and keep the code created during the work in a separate folder."
2. Data analysis request patterns: "Analyze [data file name] to identify the characteristics of the data and recommend 3-5 visualization methods that are most suitable for this data. Please explain the pros and cons of each method."
3. Patterns for adding interactive features: "Add interactive features to this [chart name] chart. When the user clicks on a data point, they can see detailed information, and when they hover over it, a tooltip appears."
4. Responsive design patterns: "Please make the current web page responsive so that it displays well on mobile devices. In particular, display the navigation menu as a hamburger menu on mobile devices."
5. Code Optimization Patterns: "Review the current code for duplicates and optimize it by separating reusable functions or modules."
6. Problem-solving patterns: "A specific error message occurred. Find the cause and fix it. And please let me know how to prevent the same problem from happening in the future."

![Separate work files and result folders]({{ site.baseurl }}/images/60ae127f019900001.png)

![Data Analysis Request Patterns]({{ site.baseurl }}/images/60a82571019900001.png)

![Responsive Design Patterns - PC]({{ site.baseurl }}/images/03cd040b019900001.png)

![Responsive Design Patterns - Mobile]({{ site.baseurl }}/images/03cd0860019900001.png)

## Tips for effective communication and improvement

AI can sometimes produce quite impressive results even when given abstract requests such as "create a nice visualization chart." For example, if an idea is suggested such as "Please advise on how to make it more like a report," AI may propose a step-by-step plan. While detailed requirements must be specified at times, if there are no specific rules, it is effective to trust AI from the outset and instruct it to propose and implement a good plan. 

However, sometimes errors occur or the results may differ from what was expected. In such cases, the problem should be clearly communicated in detail, as if explaining it to another team member. This minimizes the so-called "hallucination" phenomenon, where AI proceeds in the wrong direction, and allows reaching the desired results more quickly.

![]({{ site.baseurl }}/images/60b37e6f019900001.png)

## The Present and Future of Vibecoding

However, the important point here is that "vibe coding" is not the answer to all problems. Since the results generated by Claude Code may still contain hallucinations or unoptimized answers, it is advantageous to have a certain level of statistical and coding knowledge. This will enable catching and improving errors and inefficiencies in the AI's recommendations and generated code. 

There are also areas where Claude Code needs improvement. For example, Korean is handled well, but there are still some parts that require separate Korean language settings, such as installing specific libraries. In addition, for large-scale projects, it is more efficient to instruct Claude Code to design the folder structure and project structure from the beginning.

AI is just like humans. It is important to clearly communicate objectives and goals. For example, when saying, "Please add a button," a human colleague can understand what kind of button is meant based on the previous conversation, but AI may understand it as a different button than what is in mind. 

Of course, these days, LLMs have excellent context comprehension abilities and can understand the user's intentions to a certain extent, but if it misunderstands once, it tends to continue in the wrong direction. Therefore, clear instructions should be given from the outset, such as "Please add a 'Home' button at the top right," to minimize the amount of revision work. It is especially important to give clear and precise instructions when starting "vibe coding" for the first time. What is interesting is that AI actually demonstrates better design sense in some cases.

Of course, this aspect is expected to gradually improve with the advancement of AI technology. Although the current version of Vibe Coding is not yet 100% reliable, it has a significant impact on implementing side projects for the main project in a practical form rather than just at the idea stage. Currently, it is at the "somewhat capable" level, but there are plans to gradually expand the scope of what can be done using Claude Code. 

While not perfect, it will at least provide the efficiency and interaction needed to "discuss ideas with colleagues, flesh out ideas, and prototype code on the fly."

![]({{ site.baseurl }}/images/03cfebd4019900001.png)

![]({{ site.baseurl }}/images/03d01e71019900001.png)

![Initial version of visualization example created with Vibe Coding]({{ site.baseurl }}/images/03d0e9f8019900001.png)
