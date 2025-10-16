---
layout: default
title: '1.2. Building an AI-based Hackathon Review System: Rapid Development Methodology and Operational Lessons'
lang: en
parent: 'Chapter 1. Development environment and evaluation system'
nav_order: 2
permalink: /en/part-03/ch01-dev-env/ai-review-system/
author: robin.hwang
---

# 1.2. Building an AI-based Hackathon Review System: Rapid Development Methodology and Operational Lessons

The development paradigm in the AI-native era is fundamentally different from traditional methods. By actively utilizing AI in the entire process from ideation to planning, design, development, deployment, and operation, it is possible to achieve remarkable speed and efficiency. 

The example of building an AI screening system with a capacity of 250 people in 48 hours at the “10K Hackathon” on the Kakao AI campus showcases both the possibilities and realistic challenges of this new development method.

## Rapid planning and prototyping using AI

The success of a project starts with a clear plan. In this hackathon review system construction project, AI was used as a key tool from the planning stage to dramatically accelerate decision-making.

### Automatic generation of proposals based on meeting minutes

The minutes of the review process discussion meeting with project stakeholders were fed into Gemini, and a system planning document v1.0, containing the goals, key functions, and step-by-step checklists for AI audits, was obtained in just a few minutes.

### Interactive UI/UX prototyping

Using generative UI development tools such as 'v0' based on the planning document, we completed a 14-page screen design in 3 hours through interactive commands. Beyond simple mockups, development continuity was secured by preprocessing some technical implementations, such as maintaining sessions on the front-end and virtual (mock) data binding, assuming API calls.

![Automatically generated proposal]({{ site.baseurl }}/images/4af221a6019900001.png)

![]({{ site.baseurl }}/images/4af3f0ef019900001.png)
![]({{ site.baseurl }}/images/4af42975019900001.png)
![]({{ site.baseurl }}/images/4af448fc019900001.png)
![Screen design image]({{ site.baseurl }}/images/4af461ae019900001.png)

## Automate full-stack development with AI agents

In the full-scale development phase, we adopted a strategy to simultaneously build the frontend and backend by using AI as an AI agent that is the subject of code generation rather than a simple auxiliary tool.

### Automatic design of API specifications

Based on the virtual (mock) data structure defined during the prototyping phase, Claude Code automatically designed all required API specifications. This had the effect of clarifying the relationship between development tasks and pre-determining the interface between backend and frontend.

### Code generation based on project context

Generated API specifications and Spring AI and Kotlin-based backend template projects were provided to AI agents, who then received instructions to design the entire backend code and database schema, including Controllers, Services, Repositories, and Entities, according to the specifications. AI analyzed existing project structures and generated consistent code in context.

![]({{ site.baseurl }}/images/4af54f6b019900001.png)

### Frontend integration automation

Shortly after the backend API implementation was completed, we asked the AI agent to transform virtual (mock) data from the frontend project into actual API calls. In this process, AI completely replaced the mock data with code linked to the actual API by referencing the backend controller code itself, achieving a state where all functions, from login to dashboard, operated normally with just one execution in the local environment.

## Building an operating environment and overcoming technical challenges

We received help from AI in the deployment and configuration process for stable service operation beyond development. At the same time, it was an opportunity to confirm AI's limitations and the importance of deep developer intervention.

### Using AI in DevOps

The code required for infrastructure configuration, such as creating a Dockerfile and generating a Kubernetes deployment configuration file, was quickly obtained through AI. However, to reflect the specificities of the in-house cluster environment, the developer's revision and verification process was essential.

### Limitations of AI debugging in complex environments

An issue occurred where Google OAuth2 based login did not work in the deployment environment. This was the result of a combination of session mismatch issues in the load balancer environment and AI-generated Kubernetes proxy configuration errors. AI became bogged down in this single problem and couldn't find a solution, eventually requiring developers to identify and address the root cause through log analysis and code reviews. This shows that AI still has clear limitations in debugging complex and abstract system-level problems.

## System upgrade based on operating scenarios

Following the successful development of the initial version, a major system overhaul was carried out to account for the actual operating scenario on the day of the event. This process was an experience of quickly reflecting complex requirements through collaboration with AI while facing new challenges as the codebase grew.

### Rapid expansion of needs-based functionality

We planned admin functions such as team management, submission management, AI review step-by-step control, and peer review management, which are essential for event management. We also redesigned role-based access control (RBAC) for users and administrators. These complex and vast requirements were implemented in a short period through intensive interaction with AI agents.

### AI performance decreases as the codebase grows

As the size of the project grew, AI was unable to fully grasp the context of existing code, and there was a tendency to duplicate code similar to functionality that had already been implemented. From this point on, detailed instructions that clearly specified the functions to be implemented and the code to be referenced became more important than a comprehensive "vibe coding" approach. This means that for effective collaboration with AI, human intervention methods must vary depending on the complexity of the project.

It's clear that the AI-driven development method represented by 'vibe coding' is a powerful weapon that dramatically shortens the time it takes to turn an idea into reality. This is evidenced by the fact that a complex system was built in about 48 hours based on the commit record. 

However, in the final step of completing a stable and advanced system, we were able to reaffirm that the developer's deep experience and insight in diagnosing complex problems, making architectural decisions, and responding to exceptional situations still play a key role.

![Time required to establish a screening system]({{ site.baseurl }}/images/4af68737019900001.png)

![Final summary screen]({{ site.baseurl }}/images/4af69f21019900001.png)

## Fully prepared for AI collaboration: the beginning of sustainable innovation

So far, we've explored how Kakao is building and evaluating an 'innovative development environment' suitable for the AI era. In this chapter, we confirmed that alongside the possibility of AI-led development, deep insight and experience from developers are still essential, as demonstrated by the example of building an AI-based hackathon screening system.

These efforts are not just technology in the hands of a few experts, but are a core competency for the entire company and the foundation for all members to create greater value with AI. In the next chapter, we will share specific concerns and efforts on how to sustainably maintain and develop the AI collaboration environment built in this way, covering everything from AI ethics issues to strategies for adapting to constant technological changes.
