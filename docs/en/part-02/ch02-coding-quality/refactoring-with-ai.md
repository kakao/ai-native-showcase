---
layout: default
title: '2.3. Refactoring Safely with AI'
parent: 'Chapter 2. AI-based coding and code quality management'
nav_order: 3
permalink: /en/part-02/ch02-coding-quality/refactoring-with-ai/
author: jazz.k
---

# 2.3. Refactoring Safely with AI

The key to refactoring is for people to take the initiative in breaking down tasks into smaller pieces, repeating this process multiple times, and creating code that works exactly as intended. Here, three refactoring methods for this purpose will be discussed.

## 1. Human-driven development (HDD)

Collaboration with AI is rapidly changing the landscape of development. AI-generated code may look appealing, but the key to successful refactoring still lies with people. "Human-Driven Development (HDD)" refers to the principles and approaches for creating better software by proactively utilizing AI as a tool. In this chapter, specific methods for successfully refactoring while maintaining clear control and not being led by AI will be examined.

### Safety net for refactoring

The basic premise of refactoring is always the same: "Ensure that existing code continues to work." If the legacy code is good, automated testing and a testing environment will have been established. In such cases, refactoring can be completed by reinforcing existing tests.

Unfortunately, there are many legacy codes that do not have tests for various reasons. In such cases, it is recommended to write test code based on working code before refactoring. By writing test code first, it can be ensured that the code works and refactoring can proceed smoothly. The operation of existing services can be ensured through testing at any time, which is extremely helpful in understanding legacy code. Of course, this is also an excellent example of working with AI.

```
## 🛠 지시 항목 및 출력 형식
1. **테스트 가능 영역 식별**
- 코드에서 단위 테스트가 가능한 부분은 어떤 것인가?
- 조건 분기, 순수 함수, 핵심 비즈니스 로직이 명확히 분리되어 있는가?
- 만약 분리되지 않았다면, 테스트 가능성을 높이기 위해 어떻게 구조 개선이 필요한가?
- 🔍 출력 형식:
	✅ 테스트 가능: [예: validateEmail 함수 – 순수 함수]
	❌ 테스트 불가: [예: 결제 처리 로직 – DB 접근과 로직이 섞여 있음]
	→ 개선 제안: [예: DB 접근 부분을 Repository로 추출]
2. **테스트 우선순위 판단**
- 코드 중 테스트 우선순위가 높은 영역은 어디인가?
- 로직 복잡도, 변경 위험도, 외부 의존도(API/DB 등) 기준으로 판단.
- 🔍 출력 형식:
	🔺 우선순위 높음: [결제 승인 로직] – 외부 결제 API와 긴밀히 연관됨
	🔻 우선순위 낮음: [UI 애니메이션 전환] – 변경 위험도 낮고 사용자 가치 영향 적음
3. **테스트 어려움의 설계적 원인 분석**
- 테스트 작성을 어렵게 만드는 설계적 결함은 무엇인가?
- 전역 상태, 결합도, 의존성 등 구조적 장애요소를 진단하라.
- 🔍 출력 형식:
	❗ 전역 상태: globalConfig가 모듈 전체에 영향을 줌
	❗ 하드코딩된 의존성: FileWriter가 클래스 내부에 직접 생성됨
4. **테스트 레벨 판단**
- 각 영역에 대해 어떤 테스트 레벨(Unit / Integration / E2E)이 가장 적절한가?
- 가능한 경우 단위 테스트를 우선 고려하되, 제한이 있을 경우도 명시하라.
- 🔍 출력 형식:
	[결제 로직]
	- 추천 테스트: 유닛
	- Stub 대상: 외부 PG API
5. **Mock/Stub/Test Double 전략 수립**
- 어떤 부분에 Test Double이 필요한가? 가능한 경우 구조 개선으로 mocking 회피 유도.
- 각 Double에 대해 간단한 구현 예시와 목적을 제시하라.
- 🔍 출력 형식:
	Stub: PaymentGateway → 예시: class FakePaymentGateway { ... }
	목적: 결제 승인 응답을 시뮬레이션하여 실제 API 호출 제거
6. **테스트 보장 수준 및 한계**
- 위 전략으로 테스트를 작성했을 때, 리팩토링 시 보장할 수 있는 범위는 어디까지인가?
- 단위 테스트 커버리지의 강점과 한계는 무엇인가?
- 🔍 출력 형식:
	✅ 보장 가능: 내부 로직 변경 시 기능 안정성 유지
	⚠ 보장 한계: 외부 API 응답 형식이 변경될 경우 탐지 불가
---
## 💡 주의사항
- 테스트 레벨은 ‘가능한 최소 단위에서 시작’하는 것을 우선 원칙으로 할 것
- 구조 개선이 필요한 경우 **단계적 분리 전략**을 제안할 것 (ex: 추출 → 추상화 → 인터페이스 전환)
- 답변은 코드 예시, 판단 근거, 예상 리스크를 포함하여 실무 엔지니어가 바로 참조할 수 있도록 작성할 것
```

The phrase "without TDD" may seem puzzling. Due to the nature of analyzing legacy code, development is not done in a test-driven manner. This section has been intentionally added to minimize unnecessary suggestions.

It is also effective to research and specify a testing framework in advance in order to add tests effectively. If there is a testing framework that is familiar, or if the legacy code itself is old and requires specification of the testing framework version, AI can be asked for specific suggestions and appropriate recommendations received.

If the first test has been successfully completed, the next cycle can be moved to by submitting documents such as planning documents and policy documents along with the context to reinforce testing of business logic. There is no legacy code as reliable as legacy code that has been thoroughly tested.

### Plan and review repeatedly

In AI-powered code writing, refactoring is an area that is as useful as new development. In particular, legacy code refactoring is an area where AI can be utilized more effectively, as it involves modifying code that is already functioning. You can give the entire project to AI and have it refactor it. However, in this case, it may work well, but the results may differ from what you expected. This is likely to result in an overwhelming amount of changes in response to your request.

It is recommended to go through the stages of planning and reviewing rather than entrusting refactoring to AI right away. Plans should be reviewed as if talking to a colleague, and AI will gladly review them.

```
<프롬프트>
# 역할
너는 비판적이면서도 노련한 시니어 소프트웨어 엔지니어이자 아키텍트다. 나는 너와 함께 코드를 리팩토링하려고 한다.

# 절차 (모든 단계를 반드시 순차적으로 따르도록 해)
1.  **코드 구조 분석**
	- 내가 제공하는 코드를 아키텍처 관점에서 구조적으로 분석해줘.
	- 모듈 구성, 레이어 구분, 의존 관계 등을 파악해.
2.  **구체적인 문제점 진단**
	다음 항목별로 **구체적인 문제점**을 지적해줘:
	- 설계 및 책임 분리 (SRP 위배 여부 등)
	- 추상화 수준과 중복도
	- 네이밍 일관성과 의도 전달력
	- 테스트 용이성 및 결합도
	- 유지보수성과 확장성
3.  **리팩토링 계획 수립 (코드 변경 전 단계)**
	- 단순 작업 목록이 아닌, **전반적인 리팩토링 방향성과 단계별 전략**을 제시해줘.
	- 각 단계의 우선순위, 예상 리스크도 간략히 알려줘.
4.  **설계적 근거 제시**
	- 위 계획이 왜 타당한지 아래 원칙들을 바탕으로 설명해줘:
		- SOLID, KISS, DRY
		- 클린 아키텍처 / 계층형 구조 / 도메인 중심 설계
		- 테스트 전략 및 의존성 분리
5.  **대안적 방향 제시 (선택 사항)**
	- 가능하다면 다른 설계 접근 방식도 제안해줘.
	- 각각의 장점/단점을 간결하게 요약해줘.
6.  **내 확인 후 다음 단계 진행**
	- 내 동의 없이 다음 단계로 넘어가지 마. 반드시 "진행해도 될까요?"라고 물어봐.

# 리팩토링 철학 (모든 판단의 기준으로 삼을 것)
- 비즈니스와 도메인에 맞는 책임 분리
- 테스트 가능한 구조와 의존성 분리
- 의도가 명확히 드러나는 코드
- 미래의 요구 변경에 유연하게 대응할 수 있는 설계
```

If the scope of the code to be refactored is provided using the prompt above, the AI will respond kindly. Based on the first response, further review is necessary. It's only been a few seconds since the refactoring code was given to AI. 

It is recommended to repeat the process of discussing the reasons for refactoring and the expected risks with AI until the desired level of design is achieved. If code proposals based on hasty decisions are received, more time will be spent reviewing the proposed code. If any problems are found during review, the cause should be clearly explained and AI requested to review again.

The productivity that AI brings can sometimes seem like magic. However, it is safer to treat AI that assists with refactoring as an enthusiastic new employee rather than an experienced senior employee. This is because if there are no restrictions, people tend to start tinkering with things and end up changing the structure. AI provides probabilistic answers, so the proposed structure may seem good at first glance. 

However, unless the structural changes are part of the original plan, they should be approached conservatively. This is because unplanned structural changes can disrupt the harmony of the entire system. As conversations with AI are repeated, things that should and should not be done will emerge. These should be reflected in the prompt and the discussion continued.

While exchanging messages, it is important to remember to make clear requests to the AI. It is beneficial to ask AI questions as if you were asking yourself what parts you would like to refactor in order to refine your thinking, but if vague requests are made, only plausible suggestions will be received. An example of an ambiguous request is "Please improve this code."

Like TDD (Test Driven Development), HDD (Human Driven Development) must be practiced. Since accepting code suggestions is also done by humans, how AI is handled depends entirely on humans.

## 2. Repeat refactoring

Refactoring with AI is not like moving a huge rock all at once, but rather like breaking it into smaller pieces and moving them several times. The key to this process is "iteration."

### Request in small units and commit

After reviewing the refactoring plan, a clear understanding of what needs to be changed and where to start should be had. The next step in the refactoring plan is to address requests such as "Please fix this," which can lead to too many changes and require complex review of multiple contexts at once.

Instead of saying, "Please refactor this class," it is much safer and more effective to request specific changes in small, clear units, such as "Please improve the readability of this method (specifying the specific method)" or "Please remove duplicate code from this function." If the code suggested by AI is satisfactory and passes testing, the refactoring details should be committed. There is always a possibility that AI will ruin the code beyond the scope of the request.

### Refactor again at a faster cycle

What does it mean to refactor again at a faster cycle? Even if AI is asked to refactor code that has been carefully refactored, it will gladly comply. This means that the implementation details can be quickly reviewed while reviewing the newly implemented results. This also means that lessons learned through refactoring can be applied again without having to wait too long. At this point, it is useful to compare specific commits with the current version, reconfirm requirements, and make new requests.

By revisiting the initial purpose of refactoring and incorporating the technical insights gained during the refactoring process into the initial purpose, a better plan can be created from scratch. Without AI, these tasks would have required a significant investment of time and mental energy. "Refactor what was just refactored from scratch?" AI kindly optimizes this process, which can be exhausting for humans.

## 3. Adjusting the size of the task

By communicating clear intentions to AI and exchanging feedback, a huge amount of code can be generated in no time. However, the essence is not to create a lot of new code, but to maintain the quality of the service and the code itself so that it works exactly as intended.

### Trust productivity and avoid over-engineering

Once you experience how well refactoring works after a few conversations, you may develop more advanced desires. An example of this would be pursuing engineering beauty beyond code that works well. Requirements that go beyond the scope planned at the beginning of refactoring, such as adding unnecessary design patterns or considering unnecessary scalability, should be avoided. Such changes not only undermine the consistent design of the entire service code, but also increase uncontrolled complexity wherever refactoring is performed. If something is realized while refactoring, it should not be reflected spontaneously, but rather refactored while considering harmony with the entire service code.

### Refactoring based on PR

Talking to AI isn't just about getting code. It should be proceeded by clearly stating the intent and details of the changes, as if writing a PR (Pull Request) to send to a colleague. The proper role of AI is to assist developers in writing code, not to boast about the superiority of the model it uses to fellow developers who are reviewing the code.

```
<프롬프트>

# [리팩토링 PR 리뷰 요청]
아래 GitHub Draft PR의 설명과 코드 diff를 참고하여 다음을 도와줘:
1. PR 설명을 바탕으로 **리팩토링의 범위와 핵심 의도**를 간결히 요약해줘.
2. 코드 diff를 구조적으로 분석하고, 다음 관점에서 평가해줘:
	-  **책임 분리 (SRP)**
	-  **설계 원칙 준수 여부 (예: OCP, DRY, KISS)**
	-  **코드 일관성과 테스트 가능성**
3. 개선이 필요하다면 아래 항목을 포함해 구체적으로 제안해줘:
	-  **리팩토링 계획 (단계별 제안 포함)**
	-  **설계적 근거 (SOLID, 클린 아키텍처 등 기반)**
	-  **대안 전략**과 그 **장단점 요약**
4. 리팩토링의 안정성을 높이기 위한 **테스트 보완 필요 여부**와 그에 대한 **테스트 전략**을 알려줘.
※ 이 PR은 리팩토링의 초기 단계이며, 전체 구조 개선과 확장성 확보를 목표로 한다는 점을 고려해 분석해줘.

---
# 다른 프롬프트와 함께 쓸 수 있도록 지침을 간소화 해놨다.
```

If refactoring criteria and scope are discussed with colleagues in advance, a draft PR written, and refactoring proceeded based on the draft PR information, it will be clearer when refactoring should be completed.

## The Essence of Refactoring with AI

While it is true that AI reduces the time spent writing code, it does not eliminate the time spent thinking and reviewing. A significant portion of the time spent writing code is spent reviewing code. It must be carefully checked that the request has been properly reflected, that there are no logical contradictions, and that there are no potential side effects. In order to critically accept the code generated by AI, additional time is required to ask questions and check whether it has been implemented correctly. 

Including these times, the time spent on refactoring may not have decreased significantly. Therefore, it is not recommended to place excessive trust in AI productivity and set refactoring periods that are too short or plan an unmanageable amount of refactoring.

Refactoring with AI is certainly an attractive development method, but in order to fully utilize AI's potential, it is necessary to recognize its clear limitations and approach it wisely. AI cannot read minds, nor can it put the results it has produced into heads. Even if the code is generated by AI, the final ownership and responsibility for the code lies with the developer. 

AI-generated code must be able to understand every line and explain the design intent just as well as code written by oneself. That is why it is important to review the refactoring design process several times and devote a lot of time to it.

If AI is given even the slightest ambiguous request, it will only give plausible answers. It is important to remember that the system provides results with the highest probability based on the user's request. Without clear goals, specific instructions, and critical review, AI responses will remain at the level of functioning wrong answers.

Although AI can assist in the process of deploying refactoring results and in operations, troubleshooting can be difficult due to unrecognized environmental complexities. There are other reasons why refactoring time cannot be kept short. In such cases, traditional analysis and experience may still be necessary.

Despite these limitations, AI makes it easier to overcome the biggest psychological barrier to refactoring: getting started. When developers are faced with complex legacy code and don't know where to start, AI can help analyze the entire project and diagnose and propose solutions to problems that were not previously identified. AI is also extremely helpful in performing repetitive tasks.

Ultimately, refactoring in the AI era boils down to the essence of "collaboration between humans and AI." Rather than relying on one side, developers should take on the role of "architects," providing direction at a higher level, making important design decisions, and taking responsibility for the quality of the final product. AI is a passionate partner that provides multiple high-potential alternatives and never shies away from repetitive tasks.
