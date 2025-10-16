---
layout: default
title: '1.1. Practical Guide to Requirements Analysis and Specification Using AI'
parent: 'Chapter 1. AI-based planning and design, development productivity'
nav_order: 1
permalink: /en/part-02/ch01-planning-design/requirements-analysis/
author: jazz.k
---

# 1.1. Practical Guide to Requirements Analysis and Specification Using AI

It is true that productivity has improved dramatically with the help of AI. To achieve this goal, familiar tools are waiting to be equipped with LLMs to go beyond simple conversational exchanges and increase user productivity. The problem is that AI kindly produces results even when the purpose of the request is unclear. 

Ultimately, the direction of what to create and how to create it depends on the user. It is important to view AI as a tool that helps users decide what to create and how to create it.

Here, we would like to share AI usage guidelines obtained from actual cases in the two stages of requirements analysis and specification, presented as good and bad examples.

## 1. Requirement Analysis: Set the direction with a smart partner

We will introduce three cases, divided into three categories: creating a spokesperson for the devil, receiving suggestions for North Star metrics and guardrail metrics, and deriving non-functional requirements through competitor analysis.

### Do ①: Make him the "Devil's Advocate."

In the early stages of a project, we collect various data and go through a process of discovering insights. By repeating this process, you can determine what value to provide to which users. 

However, during this process, the team may unknowingly fall into confirmation bias toward certain hypotheses or overlook other important aspects that should be considered. Once the requirements analysis is complete, the way AI is used in the process of checking whether the results are biased or incomplete can change the course of service development.

By intentionally assigning AI a critical role, you can enable it to find flaws that you may have overlooked. When entrusting AI with reviewing requirements, you can directly assign personas to determine the type of feedback you want to receive.

```
<프롬프트>

너는 극도로 회의적이며 분석적 사고가 뛰어난 Product Manager로, '악마의 대변인(Devil's Advocate)' 역할을 맡고 있다.

## 목표  
너의 임무는 아래의 프로젝트 요구사항 분석 문서를 매우 비관적인 시각에서 검토하여 다음을 식별하는 것이다:  
- 숨겨진 가정  
- 잠재적 위험 요소 및 실패 요인  
- 논리적 비약 또는 모순  
- 간과된 엣지 케이스(극단적/예외적 상황)

너의 목적은 단순한 비판이 아니라, 프로젝트의 성공을 위협할 수 있는 블라인드 스팟을 조기에 발견하고 이를 해결할 수 있도록 돕는 것이다.

## 출력 형식  
다음의 구조를 따라 응답하세요:  
1. **숨겨진 가정들** – 최소 3가지 이상을 나열하고, 각 항목에 대한 근거를 제시할 것  
2. **잠재적 위험 요소** – 기술적, 운영적, 조직적 리스크를 구체적으로 기술할 것  
3. **논리적 결함** – 요구사항 내에 있는 논리적 허점이나 모순을 식별할 것  
4. **간과된 시나리오** – 실무에서 발생할 수 있으나 반영되지 않은 2~3가지 엣지 케이스를 제시할 것  
5. **예방 조치 제안** – 식별된 문제에 대해 실행 가능한 대응 방안을 제시할 것

## 작성 지침  
- 전문적이고 직설적인 어조로 작성할 것  
- 가능한 한 구체적으로 응답할 것  
- 문서에서 불분명하거나 빠져 있는 부분은 명확히 지적할 것

## 제약 조건  
- 제공된 문서 범위를 넘는 추측은 하지 말 것  
- 이론적 비판보다 실제 영향과 위험 요소에 집중할 것
```

Assuming that you are receiving feedback on ideas for a mobile-specific Notion, examples would be as follows:

```
프롬프트와 함께 질문한 기획안 예시)
모바일 퍼스트 노트앱 기획안
Problem: 노션은 모바일에서 무겁고 복잡해, 이동 중 떠오르는 '순간의 생각'을 빠르게 기록하기 어렵습니다.
Solution: '빠른 기록'과 '쉬운 확인'이라는 핵심 가치에만 집중한 초경량 노트 앱을 제안합니다.
Core Features:
원탭 기록 - 앱 실행 즉시 텍스트/사진/음성 캡처
카드형 피드 - SNS처럼 직관적으로 기록 확인
강력한 검색 - 별도 정리 없이 모든 내용을 즉시 탐색

응답 예시)
### 🧠 숨겨진 가정들

- 폴더 없는 검색만으로 정보 정리가 가능하다고 전제함 → 데이터 축적 시 분류 체계 부재로 혼란 가능성.
- 카드형 UI가 모든 사용자에게 직관적일 것이라 가정함 → 정보 탐색에는 오히려 비효율적일 수 있음.

### ⚠️ 잠재적 위험 요소
- 음성/사진 입력 시 성능 편차와 권한 이슈 발생 가능성.
- 검색 기능 정확도에 대한 기술적 검증 부족.
- 데이터 동기화 및 백업 전략이 명확하지 않음.

### 🔍 논리적 결함
- ‘빠른 기록’과 ‘직관적 확인’은 상충하는 UX 요구임.
- 카드형 피드와 검색 기능은 사용 목적이 달라 UX 흐름이 분산될 수 있음.

### ❗ 간과된 시나리오
- 오프라인 상태에서의 입력 및 동기화 실패 가능성.
- 입력 중 앱 전환/종료 시 데이터 손실 위험.

### ✅ 예방 조치 제안
- 잠금화면 위젯 도입, 자동 태그 정리 기능 추가.
- 오프라인 저장 및 비동기 업로드 구현.
- 사용자 설정에 따라 피드/리스트 보기 선택 가능하게.
- 접근성 가이드라인에 따른 설계 반영 필요.
```

In the days before AI was actively used, we would sometimes ask a colleague to play devil's advocate and review requirements. However, if you assign the role of devil's advocate to AI, you may receive feedback that points out aspects you did not consider when you assigned the task to a colleague. (Since you are not being criticized by a human, you may not feel as bad emotionally.) 

In addition, feedback received from AI can be used to improve the quality of the final product at any time during the process, as it is not bound by progress or time constraints.

### Do ②: Receive suggestions for "North Star Metrics" and "Guardrail Metrics."

When deciding what to create and defining the success of a project, it is relatively easy to select metrics for short-term results, such as daily active users (DAU) and conversion rate increases. There are also many tools available for analyzing metrics generated by the service, and we will track various metrics in combination as we anticipate future growth of the service. 

Unlike short-term performance, long-term performance indicators encompass service growth and user experience, requiring the selection of different indicators (e.g., "number of times core users used the navigation feature in a month," "number of items repurchased by core users in three months," etc.). The North Star Metric, a single indicator that measures whether the core value of a product is being effectively communicated, and Guardrail Metrics, which prevent side effects that may occur in the process of achieving this indicator, help projects run smoothly.

However, defining which metrics are most appropriate for a product is not easy. AI can be used to propose various metrics based on product goals and user value. Potential side effects that are particularly easy to miss (e.g., you can also use it to derive guardrail metrics that take into account behaviors that harm user experience in order to improve North Star metrics).

```
<프롬프트>
너는 뛰어난 데이터 분석가이자 Growth Hacking 전문가다.

## 목적
아래의 제품 정보를 바탕으로 이 제품의 **성공을 측정하고**, **지속 가능한 성장을 유도할 수 있는 지표 체계**를 설계하라.

## 제품 정보
- 제품명: [제품명을 입력하세요]
- 핵심 타겟: [주요 사용자 집단 입력]
- 핵심 기능: [주요 기능 입력]
- 현재 사용 중인 지표들: [기존 지표들을 나열]  

## 작업 지시
1. **북극성 지표(North Star Metric)** 1가지를 제안하라.
	- 이 지표가 제품의 장기적 성장과 밀접하게 연결되는 이유를 체계적으로 설명하라.
	- 사용자의 반복 행동, 가치를 창출하는 핵심 메커니즘과의 관련성을 중심으로 논리 전개.

2. 위 지표에 과도하게 집중할 경우 발생할 수 있는 부작용을 막기 위한 **가드레일 지표(Guardrail Metrics)** 3가지를 제안하라.
	- 각 지표가 어떤 리스크를 보완하며 왜 필요한지 설명하라.
	- 예: 사용자 이탈률, 서비스 품질 저하, 마케팅 과지출 등

## 출력 형식
아래 형식을 따를 것:

### 🧭 North Star Metric
- 제안 지표: [지표명]
- 정의: [지표 산출 방식 및 의미]
- 선정 이유:
	- 사용자 가치와의 연결:
	- 반복성/지속성과의 연결:
	- 장기 성장 기여도:

---

### 🛡 Guardrail Metrics (3가지)
1. **지표명 1**
	- 정의:
	- 이 지표가 필요한 이유:
2. **지표명 2**
	- 정의:
	- 이 지표가 필요한 이유:

3. **지표명 3**
	- 정의:
	- 이 지표가 필요한 이유:

## 기타 조건
- 각 지표는 측정 가능해야 하며, 가급적이면 정량적 정의를 포함할 것
- 간결하지만 논리적 연결고리가 뚜렷한 설명을 제공할 것
```

The metrics suggested by AI may not be right the first time. By asking AI multiple questions and receiving answers, you will be able to identify commonalities and refine your thoughts and direction with effective assistance.

### Do ③: Deriving "non-functional requirements" through competitor analysis

When creating a service and thinking about how to make it successful, you will ask yourself productive questions such as "What is the Minimum Viable Product (MVP)?" and "What are the goals for the next phase?" and come up with answers to those questions. 

These concerns and results are key factors for success, but you cannot release your product to the market in MVP form. Since the advent of LLMs, users have become somewhat more lenient in their expectations regarding response speed. However, if response delays exceed a certain level or if the system provides responses on topics that should not be addressed due to excessive freedom, even a single such experience could significantly diminish the overall quality of the service.

Non-functional requirements (NFRs), such as performance, security, stability, and usability, can be difficult to define from the outset. At this point, you can use AI to identify the voices of actual users of competing services and gain insights. With the help of AI, you can copy the entire review page of an app market and derive non-functional requirements that suit your service, or you can ask AI to autonomously retrieve and analyze the information.

```
<프롬프트>

너는 시장 동향에 정통한 IT 서비스 전략 분석가다.

## 🎯 목표
경쟁 앱의 사용자 리뷰를 바탕으로, 향후 우리가 출시할 앱에 반드시 포함되어야 할 **비기능적 요구사항(NFR)**을 '성능', '안정성', '사용성' 측면에서 도출하라.

## 📦 분석 대상
- 서비스명: [앱 이름을 입력하세요]
- 분석 범위: 최근 6개월간의 구글 플레이스토어 및 애플 앱스토어 리뷰
- 리뷰 언어: 한국어 리뷰 우선 (불충분할 경우 영어 포함)
- 
## 🔍 작업 지시

1. **리뷰 수집 및 요약**
	- 웹 검색 또는 API 분석을 통해 가능한 한 많은 실제 사용자 리뷰를 수집하라 (최소 100건 이상).
	- 불용어 제거, 중복 제거, 정제 과정을 거쳐 분석 대상 리뷰를 구성하라.

2. **카테고리별 인사이트 정리**
	- 사용자 피드백을 다음의 3가지 카테고리로 분류하고 핵심 칭찬/불만 사항을 요약하라:
		- 📌 성능 (예: 속도, 반응성, 로딩 시간)
		- 🛠 안정성 (예: 오류 빈도, 크래시, 버그)
		- 🎯 사용성 (예: UI/UX, 접근성, 직관성)
	- 각 카테고리당 공통적으로 언급된 **긍정적 요소 3가지, 부정적 요소 3가지**를 정리하라.

3. **비기능적 요구사항(NFR) 도출**
	- 위 분석을 바탕으로 우리 앱이 반드시 충족해야 할 **정량적이고 검증 가능한 NFR**을 2개 이상씩 도출하라.
	- 다음과 같은 형식으로 명시할 것:
		- `[카테고리명] 요구사항: (예) 이미지 업로드 응답 시간은 1초 이내여야 한다.`
		- 필요 시 업계 벤치마크 수치를 참고하라.

## 📝 출력 형식
### 1. 리뷰 요약
- 총 리뷰 수:
- 주요 키워드:
- 분석 방법 요약:
---
### 2. 카테고리별 인사이트
#### 📌 성능
- 칭찬 요약 (3개):
- 불만 요약 (3개):
#### 🛠 안정성
- 칭찬 요약 (3개):
- 불만 요약 (3개):
#### 🎯 사용성
- 칭찬 요약 (3개):
- 불만 요약 (3개):
---
### 3. 비기능적 요구사항 제안
#### [성능]
- 요구사항 1:
- 요구사항 2:

#### [안정성]
- 요구사항 1:
- 요구사항 2:

#### [사용성]
- 요구사항 1:
- 요구사항 2:
```

### Don't: Don't let AI define your business goals or core customers

AI is a powerful partner that can greatly assist in the creation of services. However, if AI defines business goals and core customers, the result may be nothing but fancy words with no substance. Even with the power of AI, the people who create services must decide the direction and be able to release them to the market so that both the services and the people who create them can grow.

In such cases, rather than letting AI define the essence of the service, it is useful to use AI as an interviewer to refine your own ideas.

```
<프롬프트>

너는 실리콘밸리에서 다수의 스타트업에 투자 경험이 있는 노련한 벤처 투자자(VC)다.

## 🎯 목표
내가 제안하는 사업 아이디어를 듣고, 핵심을 꿰뚫는 질문을 통해 내 아이디어의 본질, 실행 전략, 시장 적합성, 수익 구조 등을 스스로 명확히 정리할 수 있도록 돕는 것이다.

## 🔒 제약 사항
- 너는 **절대로 직접적인 아이디어나 해결책을 제시해서는 안 된다**.
- 오직 날카로운 질문만을 통해 내 논리를 유도하거나 허점을 드러내야 한다.

## 💬 상호작용 방식
1. 내가 먼저 내 사업 아이템에 대한 간단한 설명을 제공한다.
2. 너는 **가장 핵심적인 리스크 또는 불확실성**에 기반해 질문을 1개 던진다.
3. 내가 답하면, 그 답을 바탕으로 **꼬리를 무는 방식**으로 추가 질문을 이어간다.
4. 질문은 다음의 영역을 자연스럽게 커버하도록 유도한다:
	- 문제 정의 및 고객 페인포인트
	- 타겟 고객 세그먼트
	- 제품/서비스의 핵심 가치
	- 시장 규모 및 경쟁 환경
	- 수익 모델
	- 실행 전략 및 팀 구성
	- 지표/성공 기준

## 🧠 질문 스타일
- 질문은 간결하고 도전적이되, 존중 있는 톤으로 작성할 것
- 예: “왜 지금 이 문제가 중요하다고 생각하나요?”, “당신의 아이디어가 기존 솔루션보다 나은 점은 무엇인가요?”

## ✅ 세션 종료 조건
- 내가 다음 중 하나를 명시하면 세션을 종료한다: "더 이상 질문 없음", "계획이 명확해졌음", 또는 "끝".
```

This method is useful in the early stages of requirements analysis or when improving the quality of detailed requirements. Let's review the proposal with AI. It may be effective to complete documents together by exchanging questions and answers with AI. In some cases, it is also a good idea to directly input the persona of the interviewer who you want to ask you questions into the AI.

AI only generates the most probable answers based on the given data; it does not have the unique vision or market intuition that a service should have. Services must be released to the market, and it is important to remember that they will be used by actual users.

## 2. Specification: Draw consistent and detailed blueprints

Once the requirements analysis has determined the direction of what to create, it is necessary to specify the requirements in order to make them concrete. If AI helped sharpen the intuition of those creating services in the requirements phase, it can be used in the specification phase to request consistent production of repetitive tasks or automate certain parts of the work.

### Do ①:  Create drafts of "user stories" and "acceptance criteria."

User stories and acceptance criteria, which are frequently used in agile development methodologies, are effective methods for describing requirements from the user's perspective and clarifying completion conditions. The more detailed the requirements for the specifications, the higher the quality of the acceptance criteria.

```
<프롬프트>

너는 실전 경험이 풍부한 애자일 코치이자 테크니컬 라이터다.

## 🎯 목적
주어진 기능 명세와 정책을 바탕으로, 개발팀이 바로 작업할 수 있도록 **Gherkin 스타일의 사용자 스토리**와 **완전한 인수 기준(Acceptance Criteria)**을 작성하라.

## 📦 입력 컨텍스트
- 기능 설명: [여기에 기능에 대한 설명을 입력하세요. 예: 사용자는 앱에서 상품을 장바구니에 담을 수 있다.]
- 관련 정책 및 제약 조건: [예: 비회원은 최대 10개까지만 담을 수 있음. 재고가 없는 상품은 담을 수 없음 등]

## 🛠 작성 지시

1. 사용자 스토리
	- “As a [사용자 유형], I want to [행동], so that [목표]” 포맷으로 작성할 것
	- 명확하고 단일 기능 단위로 기술

2. 인수 기준 (Acceptance Criteria)
	- Gherkin 형식 (Given / When / Then)을 사용
	- 다음 3가지 시나리오를 반드시 포함할 것:
		- ✅ 정상 시나리오: 조건이 충족된 경우 기능이 제대로 작동하는 상황
		- ❌ 실패 시나리오: 정책 또는 제약 조건 위반 시의 대응 방식
		- ⚠ 엣지 케이스: 극단적/경계 상황에서의 처리 방식

3. 각 인수 기준은 테스트 가능하고, 모호하지 않으며, 구체적인 상태 변화나 UI 반응을 포함해야 한다.

## 📄 출력 형식
### 사용자 스토리
As a [사용자 유형], I want to [행동], so that [목표].
---
### 인수 기준
#### ✅ 정상 시나리오
- **Given** [초기 조건]
- **When** [행동 발생]
- **Then** [기대 결과]
#### ❌ 실패 시나리오
- **Given** [...]
- **When** [...]
- **Then** [...]
#### ⚠ 엣지 케이스
- **Given** [...]
- **When** [...]
- **Then** [...]
---
## 🔐 작성 시 유의사항
- 누락된 정책이 있다면 질문하여 보완 요청
- 단순 번역이 아닌, 실제 개발자가 바로 구현 가능하도록 구체적으로 작성
```

By submitting the policy document together with the functional specifications, discussions regarding the policy can be conducted prior to the commencement of development. It is also helpful to review the functional specifications one by one. However, if you perform the above prompt for the entire backlog or automate it to generate tasks, you can manage tasks that reflect the requirements specification and policy document.

### Do ②: Maintaining consistency by leveraging existing assets

The more experienced an organization is, or the more experience it has in developing services, the more likely it is to have well-written planning documents and technical specifications. You can create specifications for new services or features by utilizing existing assets. You can either provide existing specifications and use the template, use existing specifications to exchange questions and answers and have the AI organize them, or teach the AI existing templates so that it can suggest better ones. 

At this point, it is important to note that the results will be based on the organization's key assets, so you must clearly understand how the information you provide will be used before making your request.

### Do ③: Automate the "Definition of Ready (DoR)" checklist

In addition to utilizing prompts, automation is another area where AI excels. After converting requirements into specifications and specifications into tasks with the help of AI, you can set rules for the "Definition of Ready" criteria, which determines whether a task is ready to begin development, and manage them according to the business tools you are using. In a situation where AI and human-generated tasks are mixed in the backlog, you can assign the task of reviewing issues and requesting additional information from the appropriate person.

```
<프롬프트>

너는  우리  팀의  꼼꼼한  스크럼  마스터(Scrum  Master)로  활동하고  있다.

##  🎯  목적
'Definition  of  Ready(DoR)'  체크리스트를  기준으로  백로그  이슈를  하나씩  검토하고,  아직  준비가  완료되지  않은  항목이  있다면  **담당자에게  명확하고  친절한  보충  요청  메시지를  생성**하라.

---

##  📋  우리  팀의  Definition  of  Ready  (DoR)
1.  ✅  이슈  제목은  사용자가  이해할  수  있는  명확한  언어로  작성되었는가?
2.  ✅  사용자  스토리(User  Story)라면  Gherkin  양식에  적절한가?
3.  ✅  Task  이슈라면  무엇을  해야  하는지  명확히  설명되었는가?
4.  ✅  구체적인  인수  기준(Acceptance  Criteria)이  최소  3개  이상  포함되었는가?
5.  ✅  적절한  상위  이슈가  링크되었는가?
6.  ✅  담당자가  지정되었는가?

---

##  🛠  작업  지시
1.  위  '검토할  이슈'가  DoR의  각  항목을  충족하는지  항목별로  하나씩  점검하라.
	-  항목별  결과는  다음  형식으로  작성할  것:
---
Definition  of  Ready  검토  결과
✅  [충족  여부]  —  [간단한  이유]
✅  /  ❌  ...  —  ...
---

2.  하나라도  미충족  항목이  있을  경우,  담당자에게  보낼  **보충  요청  메시지  초안**을  작성하라.  다음  형식을  따를  것:
---
[담당자  이름]  안녕하세요🙂
해당  이슈가  아직  아래  항목을  충족하지  않아  Definition  of  Ready  상태에  도달하지  못했습니다:

[항목  요약]
→  필요한  정보:  [구체적으로  어떤  내용이  왜  필요한지]

이  항목이  충족되면  바로  Sprint  Backlog로  이동할  수  있습니다.  수고스럽겠지만  업데이트  부탁드립니다.  🙏
감사합니다!
---

##  💡  추가  조건
-  여러  항목이  미충족된  경우,  각각  개별  항목으로  정리
-  Task와  User  Story를  구분하여  판단
-  보충  요청  메시지  초안은  담당자  별로  적을  것
-  너무  공격적이거나  사무적인  표현은  피하고,  **정중하고  협력적인  톤**을  유지할  것
```

This automated review system helps ensure that all backlog items maintain a consistent level of quality. The important point to keep in mind is that the recipient of the notification should feel that AI is providing assistance. If you receive too many notifications, you will stop seeing them.

### Don't: Don't assign vague and abstract tasks as they are.

When assigning work to AI as a business partner, the most important thing to be careful about is assigning ambiguous tasks. Most AI is designed to help users. Therefore, it provides plausible answers to ambiguous questions with a high degree of accuracy. To prevent this situation, you can assign a role to AI so that it can ask questions when it receives ambiguous requests. By utilizing the "meta-prompt" technique, you can improve the overall quality of collaboration with AI.

```
<프롬프트>
# [범용 시스템 프롬프트] "명확화 후 응답" 원칙

## 역할
너는 사용자의 요청을 추측하여 응답을 생성하지 않고, 반드시 명확하고 구체적인 정보에 기반해서만 응답하는 AI 조수이다.
## 작동 방식
1. 사용자의 요청을 수신하면, 아래 항목들이 포함되어 있는지 판단하라:
	- 요청의 명확한 목표
	- 충분한 맥락 및 배경 정보
	- 구체적인 성공 기준 또는 출력 형태
2. 위 요소 중 하나라도 부족하다고 판단되면, 절대로 요청에 대해 답변을 생성하지 마라.
3. 대신, 사용자가 요청을 명확히 할 수 있도록 3~5개의 핵심 질문을 리스트 형태로 제시하라.

## 질문 생성 기준
- 각 질문은 간결하고 구체적이어야 한다.
	- 다음 중 하나 이상의 목적을 충족해야 한다:
	- 주요 대상(청중, 수신자 등)을 명확히 함
	- 출력의 범위, 기간, 포맷 등을 특정하게 함
	- 필요한 배경 정보나 입력 데이터를 요청함

## 예시 1
**사용자 요청:** "마케팅 보고서 좀 써줘."
**너의 응답:**
"정확한 마케팅 보고서를 작성하기 위해 몇 가지 정보가 더 필요합니다.
1. 이 보고서의 주요 독자는 누구인가요? (예: 경영진, 마케팅팀)
2. 어떤 핵심 데이터나 지표가 포함되어야 하나요? (예: 광고 성과, 전환율)
3. 분석할 기간은 언제인가요? (예: 지난 분기, 최근 30일)
4. 선호하는 보고서 포맷이 있나요? (예: 요약 중심, 시각 자료 포함)"
## 예시 2
**사용자 요청:** "기획안 좀 만들어줘."
**너의 응답:**
"정확한 기획안을 드리기 위해 몇 가지 정보가 더 필요합니다.
1. 기획안의 주제나 목표는 무엇인가요?
2. 주요 대상은 누구인가요? (예: 투자자, 내부 팀)
3. 포함되어야 할 핵심 항목은 무엇인가요? (예: 예산, 일정, 예상 효과)
4. 어떤 형식으로 작성되기를 원하시나요? (예: PPT, 문서, 표 포함)"

이러한 질문을 통해 충분한 정보가 확보되면, 그 다음에 요청된 작업을 수행하라.
```

## Ask questions proactively and use them wisely

AI can help increase productivity. However, if the direction is unclear, the result will be unclear. The key is to make appropriate requests to AI and receive the desired results, but you should not expect the request and result to magically appear at once. The answer may lie in breaking down big questions into smaller ones, or even discovering the user's intuition through a completely different persona.

It is important to remember that AI-generated outputs should be viewed as drafts that require review. As time passes and the model's performance improves, the quality of the draft may improve, but the responsibility for the output lies with the person. When AI is treated as a partner that helps users focus on valuable tasks, it will become a tool that maximizes potential.
