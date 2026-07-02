▶️[CLICK HERE TO TRY IT LIVE](https://Conchita-Presley.github.io/AI-Food-Resource-Navigator/)
# AI Food Resource Navigator
### An AI-Assisted Civic Tech Solution for Streamlining Emergency Food Intake & Public Benefits Access




## 📌 Project Overview
The **AI Food Resource Navigator** is a bilingual (English/Spanish), guided digital intake prototype built to bridge the gap between complex public benefit systems and individuals experiencing food insecurity in Edison and the surrounding towns of Middlesex County, NJ. Inspired by firsthand insights gained as a frontline community volunteer, this tool transforms a historically confusing, high-barrier intake process into an accessible, clear, and empathetic digital experience.

The tool combines a **structured, tap-through intake flow** — so results are fast, predictable, and don't depend on how well someone can phrase a question — with an **AI-powered follow-up assistant** for the situational questions a fixed form can't anticipate, like transportation, immigration status, or language access.

---

## 🛑 The Problem Space
Navigating emergency food systems is often overwhelming for families facing food insecurity. Traditional barriers include:
* **Information Asymmetry:** Distinguishing between emergency local pantries and long-term federal programs (SNAP/WIC) requires navigating dense, bureaucratic terminology.
* **Resource & Logistics Constraints:** High-volume community food systems are often understaffed, meaning frontline volunteers are stretched thin and unable to spend hours doing manual intake for every individual.
* **Technical Barriers:** Vulnerable populations often struggle with rigid, confusing application forms that lack real-time feedback or conversational context.

---

## 🧭 How It Works

1. **A data-first landing view.** Before any questions are asked, the tool surfaces real Middlesex County food insecurity statistics — residents affected, insecurity rate, average meal cost, annual food budget shortfall, and the share of food-insecure residents who earn too much to qualify for SNAP. This opens the experience with context, not a form.

2. **A four-step guided intake.** Instead of open-ended conversation, the user taps through four short questions:
   - What's going on right now? (immediate need / longer-term help / income change / unsure)
   - Household size
   - Current benefits (SNAP, WIC, or none)
   - Nearest town

   This tap-based format was a deliberate design choice: it's faster on mobile, gives every user a consistent result regardless of English proficiency or how they phrase things, and keeps the AI out of the data-collection step entirely.

3. **A results screen with categorized resources.** Based on the four answers, the tool displays pre-verified resource cards — this week's food (NJ 211, the county's REPLENISH pantry directory, Community FoodBank of NJ), Edison-specific programs when relevant, longer-term SNAP/WIC/county aid, and a recertification reminder for users already enrolled. These resources are fixed, human-curated content — never AI-generated.

4. **An embedded AI assistant for open-ended questions.** Below the results, a Claude-powered "Ask" box lets the user type or tap a follow-up question (e.g., *"I don't have a car, how do I get to a pantry?"*) and receive a direct answer informed by their household size, town, and stated situation — without having to repeat that context.

---

## 🛠️ Technical Approach & Core Competencies

* **Prompt Engineering (Claude):** Designed a system prompt scoped specifically to prevent the most likely failure mode in this domain — an AI inventing pantry names, addresses, or hours it isn't certain of. The prompt restricts responses to a fixed set of pre-verified resources (NJ 211, NJSNAP.gov/njhelps.org, NJ WIC, and the county's REPLENISH directory) and explicitly instructs the model to defer to NJ 211 or REPLENISH rather than guess.
* **Structural Hallucination Mitigation:** Rather than relying on the AI to get every resource detail right, the design keeps known, verified information (names, contacts, links) hardcoded in the app and limits the AI's role to the kinds of situational, context-dependent questions a fixed form can't anticipate.
* **Bilingual UX:** Every string in the interface — including the language the AI responds in — is controlled by a single language toggle, so a Spanish-speaking user gets a fully Spanish experience, AI answers included.
* **Systemic Logic / Conditional Routing:** The four intake answers drive which resource cards appear — for example, Edison-specific programs only surface for users near Edison, and a recertification reminder only appears for users already enrolled in SNAP or WIC.

---

## 📑 Core System Prompt (Actual, In-Use)

This is the system prompt that runs in the live "Ask" feature at the end of the results screen — deliberately narrow in scope:

\`\`\`text
You help people in Middlesex County, New Jersey find food assistance. Be warm,
brief, and dignified — never clinical or judgmental. Respond in the language
requested in the context. Use the household context provided, but only the
real NJ/Middlesex resources already known to be reliable: NJ 211 (call 211 or
text your ZIP to 898-211), NJSNAP.gov and njhelps.org for SNAP,
nj.gov/health/fhs/wic for WIC, and the Middlesex County REPLENISH food pantry
directory at middlesexcountynj.gov. Do not invent specific pantry names,
addresses, phone numbers, or hours you are not certain of — instead point the
person to NJ 211 or REPLENISH to find current, verified options. Keep answers
under 120 words.
\`\`\`

Each query is paired with runtime context — household size, town, current benefits, and stated situation — pulled from the four-step intake, so responses stay grounded without asking the user to repeat themselves.

---

## 📊 Data Sources
County-level statistics are drawn from the NJ Office of the Food Security Advocate's County Data Chartbook for Middlesex County, using Feeding America's *Map the Meal Gap* 2023 estimates.

---

## ⚠️ Known Limitations / Notes for Reviewers
* The "Ask" feature calls the Anthropic API directly from the browser and requires a valid API key to be wired in; as distributed, it will show a graceful fallback message pointing to NJ 211 rather than a live answer.
* The tool does not calculate SNAP/WIC eligibility — income limits vary by household and change annually, so it points users to the official application channels rather than making that determination itself.
* This tool provides directions, not decisions — a disclaimer to that effect is shown on every results screen, since no program's actual eligibility rules are being replicated here.
* Resource details (hours, contact numbers) are point-in-time and should be reverified against NJ 211 or REPLENISH before any public deployment.
