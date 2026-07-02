▶️[CLICK HERE TO TRY IT LIVE](https://Conchita-Presley.github.io/AI-Food-Resource-Navigator/)
# AI Food Resource Navigator
### An AI-Assisted Civic Tech Solution for Streamlining Emergency Food Intake & Public Benefits Access


 ## 📌 Project Overview
The **AI Food Resource Navigator** is an end-to-end designed, conversational AI prototype built to bridge the gap between complex public benefit systems and individuals experiencing crisis. Inspired by firsthand insights gained as a frontline community volunteer, this tool transforms a historically confusing, high-barrier intake process into an accessible, clear, and empathetic digital experience.
 
The tool acts as an automated workflow assistant, guiding non-technical community members through local food pantry resources while pre-screening their eligibility for long-term support systems like SNAP (Supplemental Nutrition Assistance Program) and WIC.
 
---
 
## 🛑 The Problem Space
Navigating emergency food systems is often overwhelming for families facing food insecurity. Traditional barriers include:
* **Information Asymmetry:** Distinguishing between emergency local pantries and long-term federal programs (SNAP/WIC) requires navigating dense, bureaucratic terminology.
* **Resource & Logistics Constraints:** High-volume community food systems are often understaffed, meaning frontline volunteers are stretched thin and unable to spend hours doing manual intake for every individual.
* **Technical Barriers:** Vulnerable populations often struggle with rigid, confusing application forms that lack real-time feedback or conversational context.
---
 
## 🛠️ Technical Approach & Core Competencies
 
This civic tech project was independently scoped, designed, and prototyped using generative AI capabilities. Key methodologies deployed include:
 
* **Prompt Engineering (Claude):** Designed a robust system prompt utilizing advanced context-setting, role-prompting, and behavioral constraints to ensure the AI remains empathetic, highly accurate, and legally compliant (noting that it provides information, not legal binding decisions).
* **Iterative Prompt Testing:** Conducted multiple rounds of testing simulating edge cases, ambiguous user inputs, and non-technical phrasing. Iterated on prompt instructions to eliminate "AI hallucinations" regarding local pantry hours and benefit eligibility metrics.
* **Workflow Automation & Systemic Logic:** Integrated localized public benefit frameworks into the core logic of the system, automating the data-gathering workflow so a user's answers naturally trigger the correct next steps and local resource recommendations.
---
 
## 📑 Core System Prompt Logic (The Blueprint)
 
Below is the structured instruction block engineered to guide the AI's interaction model:
 
```text
You are the AI Food Resource Navigator, an empathetic, clear, and culturally competent digital intake assistant. Your goal is to help individuals navigate immediate food crisis resources and long-term public benefits (SNAP/WIC).
 
OPERATIONAL CONSTRAINTS:
1. Speak in accessible, plain language. Avoid dense, bureaucratic jargon.
2. Maintain strict confidentiality and absolute empathy. Acknowledge the user's stress without being patronizing.
3. Distinguish clearly between immediate relief (local food pantries) and systemic aid (SNAP/WIC registration processes).
4. If a user expresses an absolute immediate emergency, prioritize displaying emergency hotlines and local pantry operating hours first.
 
INTERACTION WORKFLOW:
- Step 1: Greet warmly and assess immediate safety/food needs.
- Step 2: Gather basic community context (e.g., zip code, household size) through natural conversation.
- Step 3: Match user needs against built-in criteria for local pantry access and regional SNAP income eligibility guidelines.
- Step 4: Output clear, bulleted, actionable next steps.
```
