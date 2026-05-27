# 🧠 Prompt Engineering 
 
> A structured learning guide covering core techniques, real-world patterns, and production best practices for working with AI language models.
 
---
 
## 📌 What Is Prompt Engineering?
 
**Prompt engineering is the skill of writing precise instructions for AI so it gives you accurate, useful, and consistent results.**
 
That's the simple version. The deeper version: it's *specification design* — the same way a good job description helps you hire the right person, a well-crafted prompt helps an AI produce the right output.
 
You're not coding algorithms. You're not training models. You're communicating — clearly, deliberately, and strategically — with a system that does *exactly* what you say, nothing more, nothing less.
 
---
 
## 🤔 Why Does It Matter?
 
The same AI model can give you a brilliant answer or a completely useless one — and the **only difference is how you asked**.
 
Here's what poor prompting costs you in real systems:
 
| Problem | Real Impact |
|---|---|
| Vague task | AI guesses wrong, you redo the work |
| No output format | Can't plug response into your app |
| Missing context | AI invents facts (hallucination) |
| Too many instructions | Unreliable, inconsistent results |
| No examples | Output doesn't match your style or format |
 
And here's what good prompting *gives* you:
 
- **Better quality** — accurate, relevant, on-format answers
- **Lower cost** — fewer wasted tokens, fewer retries
- **Faster results** — shorter, focused prompts process quicker
- **Reliability** — same quality on run #1,000 as run #1
---
 
## 🏗️ How a Prompt Is Built
 
Every great prompt is made of up to **7 components**. You don't always need all seven — but knowing each one helps you diagnose *why* a prompt is failing.
 
| Component | What It Does | Example |
|---|---|---|
| **Role** | Tells AI who it's being | *"You are a senior data analyst..."* |
| **Task** | The specific job to do | *"Summarise this report in 5 bullets"* |
| **Context** | Background the AI needs | *"This is for a non-technical audience"* |
| **Constraints** | Rules and limits | *"Max 100 words. No jargon."* |
| **Examples** | Show what good looks like | *"Here's a sample output: ..."* |
| **Output Format** | Shape of the answer | *"Return as JSON: {summary: ..., risk: ...}"* |
| **Evaluation Criteria** | What success looks like | *"Must cite at least 2 data points"* |
 
### A Quick Before & After
 
**❌ Weak prompt:**
```
Write something about our product.
```
 
**✅ Strong prompt:**
```
You are a B2B copywriter. Write a 150-word LinkedIn post announcing 
our new inventory management software. Audience: operations managers 
at mid-size manufacturers. Tone: professional but energetic. 
End with a call to action.
```
 
Same AI. Completely different result.
 
---
 
## 🔄 How to Use It — The Core Loop
 
Prompt engineering is not a one-shot process. It's a loop:
 
```
Write prompt → Test with real inputs → Identify what broke → Fix it → Repeat
```
 
In practice this means:
 
1. **Start simple** — try a basic zero-shot prompt first
2. **Measure the output** — does it do what you actually needed?
3. **Add what's missing** — examples, constraints, format, context
4. **Test edge cases** — what happens with unusual or tricky inputs?
5. **Lock it down for production** — version it, monitor it, maintain it
Most beginners try once, it doesn't work perfectly, and they give up. The professionals iterate — and that's the entire difference.
 
---
 
## 🚀 What's in This Guide
 
This repository covers **15 core techniques** — from beginner-friendly basics to production-grade advanced patterns — along with real-world prompt templates, debugging playbooks, and enterprise best practices.
 
| Level | Techniques Covered |
|---|---|
| 🟢 Beginner | Zero-Shot, Role, Constraint, Output Format, Few-Shot |
| 🟡 Intermediate | Chain of Thought, Reflection, Delimiter, Step-Back, Prompt Chaining |
| 🔴 Advanced | RAG, Self-Consistency, ReAct, Tree of Thoughts, Meta Prompting |

# 🧠 Prompt Engineering Techniques 
 
> 15 techniques. Every accuracy range. Clear comparisons. Production-ready skeletons.
 
---
 
## 📊 Master Comparison Table
 
| # | Technique | Level | Accuracy | Token Cost | Speed | Best Single Use Case |
|---|-----------|-------|----------|------------|-------|----------------------|
| 01 | Zero-Shot | 🟢 Beginner | 65–78% | 1× | ⚡⚡⚡⚡⚡ | Simple Q&A, translation |
| 02 | Role Prompting | 🟢 Beginner | 72–85% | 1× | ⚡⚡⚡⚡⚡ | Domain expertise tasks |
| 03 | Constraint Prompting | 🟢 Beginner | 75–88% | 1× | ⚡⚡⚡⚡⚡ | Legal/compliance content |
| 04 | Output Format | 🟢 Beginner | 80–95% | 1.2× | ⚡⚡⚡⚡⚡ | API integrations, pipelines |
| 05 | Few-Shot | 🟢 Beginner | 82–90% | 2× | ⚡⚡⚡⚡ | Brand voice, classification |
| 06 | Delimiter Prompting | 🔵 Intermediate | 78–90% | 1.1× | ⚡⚡⚡⚡⚡ | Document processing |
| 07 | Step-Back | 🔵 Intermediate | 80–89% | 2× | ⚡⚡⚡ | Diagnostics, strategy |
| 08 | Chain of Thought | 🔵 Intermediate | 83–92% | 3× | ⚡⚡⚡ | Multi-step reasoning |
| 09 | Reflection | 🔵 Intermediate | 85–92% | 3.5× | ⚡⚡ | High-stakes documents |
| 10 | Prompt Chaining | 🔵 Intermediate | 84–93% | 3× per step | ⚡⚡ | Production workflows |
| 11 | Meta Prompting | 🔵 Intermediate | 76–87% | 2.5× | ⚡⚡⚡ | Building prompt libraries |
| 12 | RAG Prompting | 🟠 Advanced | 88–96% | 4× | ⚡⚡ | Internal knowledge bases |
| 13 | Self-Consistency | 🟠 Advanced | 88–95% | 5× | ⚡ | Medical/legal/financial |
| 14 | ReAct | 🟠 Advanced | 87–93% | 6× | ⚡ | AI agents with tools |
| 15 | Tree of Thoughts | 🔴 Expert | 90–96% | 8× | ⚡ | Strategic decisions |
 
---
 
## 📈 Accuracy vs Cost — Visual Map
 
```
Accuracy
  96% ┤                                          ToT ●
  94% ┤                              RAG ●
  92% ┤                   CoT ●   Reflection ●         Self-Consistency ●
  90% ┤         Delimiter ●    Prompt Chaining ●                  ReAct ●
  88% ┤    Few-Shot ●  Output Format ●
  86% ┤              Meta Prompting ●
  84% ┤  Role ●  Constraint ●
  78% ┤  Zero-Shot ●
      └────────────────────────────────────────────────────────────────▶
          1×       1.5×      2×      3×      4×      5×      6×      8×
                                                               Token Cost
```
 
**Key insight:** Zero-Shot → Few-Shot is the cheapest accuracy jump (+10–15% for +1× cost).
Few-Shot → Self-Consistency is the biggest reliability jump (+5–10%) — but at 5× the cost.
**Rule:** Always start left, move right only when your data justifies it.
 
---
 
## 🗺️ Quick Decision Map — Which Technique for My Situation?
 
| Situation | Recommended Technique(s) |
|-----------|--------------------------|
| Simple, well-defined task | Zero-Shot → Role Prompting |
| Need consistent format or style | Few-Shot + Output Format |
| Multi-step reasoning or calculations | Chain of Thought |
| High-stakes document before publishing | Reflection |
| Domain expertise matters | Role Prompting |
| Compliance / safety limits | Constraint Prompting |
| Output feeds into another system | Output Format + Delimiter |
| Diagnostic or strategic reasoning | Step-Back |
| Multi-stage production workflow | Prompt Chaining |
| Proprietary or current knowledge | RAG Prompting |
| High-stakes, must-be-right answers | Self-Consistency |
| AI agent with tools / APIs | ReAct |
| Strategic decision with real trade-offs | Tree of Thoughts |
| Building or improving prompts at scale | Meta Prompting |
 
---
 
## ⚖️ Head-to-Head Comparisons
 
### Chain of Thought vs Tree of Thoughts
 
| | Chain of Thought | Tree of Thoughts |
|---|---|---|
| **Approach** | One linear reasoning path | Multiple branches explored simultaneously |
| **Best for** | Step-by-step math, logic, compliance checks | Strategy, design decisions with real trade-offs |
| **Accuracy** | 83–92% | 90–96% |
| **Cost** | 3× | 8× |
| **Use when** | One clear method exists | Multiple valid approaches exist |
| **Avoid when** | Speed is critical | Simple/single-path problems |
 
> **Rule of thumb:** If you'd solve it the same way twice, use CoT. If an expert might disagree on the approach, use ToT.
 
---
 
### RAG vs Self-Consistency (for high-accuracy needs)
 
| | RAG Prompting | Self-Consistency |
|---|---|---|
| **What it solves** | Hallucination on proprietary/current info | Unstable or variable answers on hard problems |
| **How it works** | Injects retrieved documents into the prompt | Runs same prompt 3–5×, picks majority answer |
| **Accuracy** | 88–96% | 88–95% |
| **Cost** | 4× | 5× |
| **Best for** | Internal knowledge bases, live docs | Medical/legal/financial reasoning |
| **Fails when** | Retrieval quality is poor | Cost or speed is priority |
 
> **Rule of thumb:** If the answer exists in a document you own → RAG. If the answer requires hard reasoning with no ground-truth doc → Self-Consistency.
 
---
 
### Zero-Shot vs Few-Shot (the most common upgrade decision)
 
| | Zero-Shot | Few-Shot |
|---|---|---|
| **Examples provided** | None | 2–5 input/output pairs |
| **Accuracy** | 65–78% | 82–90% |
| **Cost** | 1× | 2× |
| **Consistency** | Variable | High |
| **Setup time** | Seconds | Minutes (crafting examples) |
| **Best for** | Well-known tasks, generic formats | Custom formats, brand voice, niche classification |
 
> **When to upgrade:** If Zero-Shot keeps giving the right *type* of answer but wrong *format or tone* → Few-Shot will fix it immediately.
 
---
 
## 🟢 Beginner Techniques
 
> Low cost · Fast · The foundation everything else builds on
 
---
 
### 01 — Zero-Shot Prompting
**"Just ask. No examples needed."**
 
The baseline. Give the model a task using only your instruction. Uses purely pre-trained knowledge. Always your starting point — if it works, stop here.
 
**Why it fails:** Vague tasks, unusual output formats, niche domains.
- ❌ "Summarise this" → could be anything
- ✅ "Summarise this in 3 bullets for a non-technical executive" → precisely what you need
**Accuracy:** 65–78% · **Cost:** 1× · **Speed:** ⚡⚡⚡⚡⚡
 
```
Classify the following customer message into one of these categories:
[Flight Issue / Hotel Issue / Refund Request / Baggage / Other]
 
Message: "My bag never arrived at the carousel after my flight from Dubai."
 
Return only the category name.
```
 
| ✅ Use for | ❌ Avoid when |
|---|---|
| Summarisation, translation, simple classification, standard Q&A | Unusual format required · Niche domain · Consistency is critical |
 
**Upgrade path:** Inconsistent output → add Few-Shot. Format wrong → add Output Format.
 
---
 
### 02 — Role Prompting
**"Put the right expert in charge."**
 
Assign an expert identity before the task. One sentence shifts vocabulary, reasoning depth, assumptions, and tone simultaneously. Highest ROI single upgrade in prompt engineering.
 
**The specificity rule:**
- ❌ "You are an expert" — too vague
- ✅ "You are a senior PostgreSQL developer specialising in query optimisation for high-volume financial systems" — shifts everything
**Accuracy:** 72–85% · **Cost:** 1× · **Speed:** ⚡⚡⚡⚡⚡
 
```
You are a senior data engineer with 10 years of experience
in SQL optimisation and ETL pipeline design for financial systems.
 
Review this slow query and explain:
1. Why it's slow (identify specific issues)
2. How to fix each issue
3. The optimised version
 
Write for someone who knows SQL basics but hasn't studied optimisation.
```
 
| ✅ Use for | ❌ Avoid when |
|---|---|
| Technical writing, domain accuracy, customer-facing tone control | Role conflicts with task · Need neutral multi-perspective output |
 
> 💡 **Tip:** Add communication style for customer roles: "calm, empathetic, professional"
 
---
 
### 03 — Constraint Prompting
**"Set the rules before the game starts."**
 
Explicit limits — word count, tone, what to avoid, required phrases. Reduces the output space and makes results reliable, consistent, and safe for production.
 
**The contradiction trap:** "Be comprehensive but stay under 50 words" is impossible. Review your constraints list — if any two conflict, remove one. Maximum 3–5 constraints.
 
**Accuracy:** 75–88% · **Cost:** 1× · **Speed:** ⚡⚡⚡⚡⚡
 
```
Constraints:
- Maximum 150 words
- Do not recommend specific financial products
- Do not give personalised investment advice
- Always end with: "For personalised advice, speak to a certified financial adviser."
- Tone: warm, informative, non-alarming
```
 
| ✅ Use for | ❌ Avoid when |
|---|---|
| Legal/medical/financial content, brand voice, hard character limits | Creative brainstorming · Constraints contradict each other |
 
---
 
### 04 — Output Format Prompting
**"Tell it what container to fill."**
 
Specify the exact shape of the answer — JSON schema, table structure, bullet format. Critical when AI output feeds into another system. Showing an example schema is far more reliable than just naming the format.
 
**Accuracy:** 80–95% · **Cost:** 1.2× · **Speed:** ⚡⚡⚡⚡⚡
 
```
Extract key information and return as JSON using this exact schema:
{
  "customer_id": "string or null",
  "complaint_category": "billing | technical | delivery | other",
  "severity": "low | medium | high",
  "summary": "max 50 words",
  "suggested_action": "string"
}
```
 
| ✅ Use for | ❌ Avoid when |
|---|---|
| API integrations, data pipelines, CRM feeds, any structured repeatable output | Casual one-off questions · Format rigidity hurts creative quality |
 
> 💡 **Tip:** Add `"Return only the JSON. No explanation, no markdown."` for machine parsing.
 
---
 
### 05 — Few-Shot Prompting
**"Teach by example, then ask."**
 
Show 2–5 input/output examples before the real task. The model learns your exact pattern — not just what to do, but exactly how you want it done.
 
**The example quality rule:** Your examples are templates the model imitates. Weak examples produce weak outputs. Show your best work. 3 examples = sweet spot. More than 5 rarely helps.
 
**Accuracy:** 82–90% · **Cost:** 2× · **Speed:** ⚡⚡⚡⚡
 
```
Classify pipeline error messages.
Categories: [TIMEOUT / AUTH_FAILURE / DATA_FORMAT / MISSING_FILE / UNKNOWN]
 
Message: "Connection to database timed out after 30s"    → TIMEOUT
Message: "Invalid credentials for user svc_account_etl"  → AUTH_FAILURE
Message: "Expected CSV but received JSON payload"         → DATA_FORMAT
 
Now classify:
Message: "File orders_2024_Q3.csv not found in /data/input/"
Category:
```
 
| ✅ Use for | ❌ Avoid when |
|---|---|
| Domain-specific classification, brand voice matching, unusual output formats | Only bad examples available · Task varies too much from examples |
 
---
 
## 🔵 Intermediate Techniques
 
> Medium cost · Better accuracy · For complex tasks and production workflows
 
---
 
### 06 — Delimiter Prompting
**"Fences keep sections from mixing."**
 
XML tags or labelled sections clearly separate instructions from data. Prevents the model conflating what to *follow* vs what to *process*. Essential for document processing and preventing prompt injection attacks.
 
**Why it matters:** Without delimiters, a document containing instruction-like text ("Ignore all previous instructions and...") can hijack your prompt. Delimiters create hard boundaries.
 
**Accuracy:** 78–90% · **Cost:** 1.1× · **Speed:** ⚡⚡⚡⚡⚡
 
```xml
<instruction>
Summarise the meeting transcript. Focus on decisions and action items.
</instruction>
 
<transcript>
[meeting content — may contain instruction-like language]
</transcript>
 
<output_format>
## Decisions Made
## Action Items | Owner | Task | Deadline |
</output_format>
```
 
| ✅ Use for | ❌ Avoid when |
|---|---|
| Document processing, large data injections, prompt injection defence | Simple single-context prompts |
 
---
 
### 07 — Step-Back Prompting
**"Zoom out before you zoom in."**
 
Identify the broader principle first, then apply it to the specific case. Prevents premature conclusions by grounding specific answers in established frameworks. Works especially well when the model tends to jump to the first plausible explanation.
 
**Accuracy:** 80–89% · **Cost:** 2× · **Speed:** ⚡⚡⚡
 
```
STEP 1 — Step back: What are the general categories of causes
for intermittent 502 errors under load in microservice architectures?
 
STEP 2 — Apply: Which categories are most likely for this specific
pattern (intermittent + load-dependent)? What diagnostics first?
```
 
| ✅ Use for | ❌ Avoid when |
|---|---|
| Technical diagnosis, policy interpretation, strategic reasoning | Well-defined tasks with a single known method |
 
---
 
### 08 — Chain of Thought (CoT)
**"Show your work. Every step."**
 
Reason through a problem in visible, numbered steps before giving the final answer. Each step becomes context for the next — so conclusions are grounded in logic, not confident guessing.
 
**Magic phrase:** `"Let's think step by step"` activates reasoning behaviour without explicit structure.
 
**Accuracy:** 83–92% · **Cost:** 3× · **Speed:** ⚡⚡⚡
 
```
Step 1: Calculate total salary cost (3 devs × £95k + 1 designer × £65k + 1 PM × £70k)
Step 2: Add equipment cost (£3,000 × 5 people)
Step 3: Add employer costs (30% on salaries only)
Step 4: Compare to £500,000 budget — over or under, and by how much?
```
 
| ✅ Use for | ❌ Avoid when |
|---|---|
| Multi-step calculations, logic, compliance checks, root cause analysis | Simple factual lookups · Speed is priority |
 
> **CoT vs ToT:** CoT follows one path. Use CoT when one clear approach exists. Use ToT when multiple fundamentally different approaches are valid.
 
---
 
### 09 — Reflection Prompting
**"Draft, critique, then polish."**
 
Generate first, then review against specific criteria. The model shifts from creator to editor mode — catching errors, tone issues, and risks the first pass missed.
 
**Why it works:** The model in "editor mode" applies different heuristics than in "writer mode." The perspective shift finds real problems.
 
**Accuracy:** 85–92% · **Cost:** 3.5× · **Speed:** ⚡⚡
 
```
STEP 1 — Write a rejection email for a Software Engineer candidate.
 
STEP 2 — Review your email and check:
- Does it sound cold or dismissive?
- Does it invite them to apply again?
- Any legal risk?
 
STEP 3 — Output only the improved version.
```
 
| ✅ Use for | ❌ Avoid when |
|---|---|
| Documents before publication, code review, any high-stakes output | Quick tasks · Creative work where first instinct matters |
 
---
 
### 10 — Prompt Chaining
**"Assembly line, not one big machine."**
 
Break complex tasks into sequential prompts. Each step does one job. Errors are isolated — when step 3 fails, you fix step 3 only. Dramatically easier to debug and improve than single-mega-prompts.
 
**Accuracy:** 84–93% end-to-end · **Cost:** 3× per step · **Speed:** ⚡⚡
 
```
Prompt 1 → Extract 5 key facts from press release → numbered list
         ↓
Prompt 2 → Write LinkedIn post from [P1 output] → 150 words, B2B tone
         ↓
Prompt 3 → Review against brand guidelines → APPROVED or NEEDS REVISION
```
 
| ✅ Use for | ❌ Avoid when |
|---|---|
| Content pipelines, multi-stage data processing, production workflows | Simple tasks · Latency is critical |
 
> 💡 **Design rule:** Each prompt should have exactly one job. If you're tempted to use "and" to describe what a step does, split it into two steps.
 
---
 
### 11 — Meta Prompting
**"Ask AI to write the AI's instructions."**
 
Use AI to generate or improve prompts rather than end content. Cuts initial prompt development from hours to minutes. Generated prompts still need testing before production — treat them as a strong first draft, not a final answer.
 
**Accuracy:** 76–87% · **Cost:** 2.5× · **Speed:** ⚡⚡⚡
 
```
You are an expert prompt engineer.
 
Task: Help customer service agents summarise calls and extract actions into CRM.
Audience: Non-technical agents
System: Output pasted into Salesforce
 
Generate an optimised prompt with role, task, constraints, and output format.
Explain your design choices.
```
 
| ✅ Use for | ❌ Avoid when |
|---|---|
| Building prompt libraries, improving underperforming prompts | Deploying without testing the generated prompt first |
 
---
 
## 🟠 Advanced Techniques
 
> Higher cost · Production-grade · For systems where accuracy is non-negotiable
 
---
 
### 12 — RAG Prompting (Retrieval-Augmented Generation)
**"Find the facts first. Then answer."**
 
Retrieve documents from a knowledge base and inject them into the prompt. The model answers from *your documents*, not its training data. The standard solution to hallucination on proprietary or current information.
 
**The retrieval quality rule:** RAG is only as good as what you retrieve. Retrieve relevant *chunks*, not entire documents. Garbage in, garbage out.
 
**Accuracy:** 88–96% · **Cost:** 4× · **Speed:** ⚡⚡
 
```xml
<instruction>
Answer using ONLY the retrieved documents.
If not there, say: "I don't have that — contact HR at hr@company.com"
Cite your source document and last-updated date.
</instruction>
 
<retrieved_documents>
[Policy sections, clearly labelled with update dates]
</retrieved_documents>
 
<question>[Employee's question]</question>
```
 
| ✅ Use for | ❌ Avoid when |
|---|---|
| Internal knowledge bases, policy Q&A, customer support with live docs | General knowledge questions · Retrieval quality is poor |
 
---
 
### 13 — Self-Consistency Prompting
**"Three independent opinions. Then vote."**
 
Run the same prompt 3–5 times independently, then select the most consistent answer. Correct answers are stable across runs; hallucinations and errors vary. Most reliable technique available — at proportional cost.
 
**Accuracy:** 88–95% · **Cost:** 5× · **Speed:** ⚡
 
```
[Run 3 times independently — temperature > 0]
 
Analyse these symptoms. Think through the differential diagnosis step by step.
Final answer: [most likely category]
 
Compare outputs:
- All 3 agree      → High confidence, proceed
- 2/3 agree        → Flag for human review
- All 3 disagree   → Escalate to specialist
```
 
| ✅ Use for | ❌ Avoid when |
|---|---|
| Medical/legal/financial reasoning, critical hard-to-verify facts | Cost or speed is priority · Simple factual lookups |
 
> 💡 **Implementation note:** Use temperature > 0 (try 0.7–1.0) to get genuine variation across runs. Temperature 0 will return near-identical outputs.
 
---
 
### 14 — ReAct Prompting
**"Think, act, observe. Repeat until done."**
 
Interleaves Reasoning and Acting — think → call tool → observe result → think → next step. The backbone of all AI agent systems. Enables AI to use real-world tools rather than relying only on training data.
 
**Accuracy:** 87–93% · **Cost:** 6× · **Speed:** ⚡
 
```
Thought: I need Q2 Western region sales data.
Action: get_report("Q2_Sales_Regional")
Observation: Western Q2 = £2.4M
 
Thought: Now I need Q3 for comparison.
Action: get_report("Q3_Sales_Regional")
Observation: Western Q3 = £2.9M
 
Thought: Calculate the percentage increase.
Action: calculate("(2.9 - 2.4) / 2.4 * 100")
Observation: 20.83
 
Final Answer: Western region grew 20.83% from Q2 to Q3.
```
 
| ✅ Use for | ❌ Avoid when |
|---|---|
| AI agents with tools, dynamic data retrieval, multi-step research | Static knowledge tasks · Latency-critical pipelines |
 
---
 
## 🔴 Expert Technique
 
---
 
### 15 — Tree of Thoughts (ToT)
**"Explore branches before committing to a path."**
 
Generate multiple distinct reasoning branches, evaluate each, select the best. Mirrors expert problem-solving — consider alternatives before committing to one path.
 
**CoT vs ToT — when to use which:**
 
| | Chain of Thought | Tree of Thoughts |
|---|---|---|
| Paths explored | 1 | 3–5 |
| Best for | Linear reasoning with one clear method | Strategic decisions with multiple valid approaches |
| Cost | 3× | 8× |
| Accuracy | 83–92% | 90–96% |
 
**Accuracy:** 90–96% · **Cost:** 8× · **Speed:** ⚡
 
```
Problem: Cut response time from 48h → 24h, no budget increase.
 
Generate THREE fundamentally different approaches. For each:
  - Describe the solution in 2–3 sentences
  - 2 advantages
  - 2 risks or drawbacks
  - Feasibility: Low / Medium / High
 
Then recommend the best approach with a one-paragraph justification.
```
 
| ✅ Use for | ❌ Avoid when |
|---|---|
| Strategic planning, complex debugging, design decisions with real trade-offs | Single-solution problems · Cost is constrained |
 
---
 
## 🔗 Power Combinations
 
These combos are greater than the sum of their parts:
 
| Combo Name | Techniques Combined | Why It Works | Accuracy Estimate |
|---|---|---|---|
| **Enterprise Workhorse** | Role + Constraint + Output Format | Expertise + guardrails + structured output | 82–93% |
| **Compliance & Audit** | RAG + Chain of Thought | Real documents + visible reasoning trail | 88–95% |
| **Data Pipelines** | Few-Shot + Output Format | Pattern teaching + format lock-in | 84–92% |
| **High-Stakes Reasoning** | CoT + Reflection | Step-by-step logic + self-correction pass | 87–93% |
| **Agent Systems** | ReAct + Prompt Chaining | Tool loop + step isolation for debugging | 85–93% |
| **Maximum Reliability** | RAG + Self-Consistency | Ground truth docs + majority voting | 90–97% |
 
---
 
## 🪜 Upgrade Decision Framework
 
Use this to decide when to invest in a more expensive technique:
 
```
Is Zero-Shot giving you wrong answers?
  ├─ Yes, wrong FORMAT/STYLE  →  Add Few-Shot (2×) or Output Format (1.2×)
  ├─ Yes, wrong DOMAIN        →  Add Role Prompting (1×)
  ├─ Yes, needs GUARDRAILS    →  Add Constraint Prompting (1×)
  └─ Yes, wrong REASONING     →  Add Chain of Thought (3×)
                                      ↓
                               Still wrong?
                                 ├─ Using PROPRIETARY INFO  →  RAG (4×)
                                 ├─ VARIABLE/UNSTABLE       →  Self-Consistency (5×)
                                 ├─ MULTI-STEP WORKFLOW     →  Prompt Chaining (3×/step)
                                 └─ STRATEGIC DECISION      →  Tree of Thoughts (8×)
```
 
**Golden rule:** The right technique is the cheapest one that meets your accuracy threshold. Never pay for 8× when 2× gives you what you need.
 
---
 
## 📋 Technique Selection by Domain
 
| Domain | Primary Technique | Fallback | Avoid |
|---|---|---|---|
| Customer Support | Role + Constraint | RAG | Self-Consistency |
| Data Pipelines | Output Format + Few-Shot | Delimiter | Tree of Thoughts |
| Legal / Compliance | RAG + CoT | Reflection | Zero-Shot |
| Medical Triage | Self-Consistency + CoT | RAG | Zero-Shot |
| Content Marketing | Role + Few-Shot | Reflection | ReAct |
| AI Agents / Bots | ReAct + Prompt Chaining | CoT | Reflection |
| Strategic Planning | Tree of Thoughts | Step-Back | Zero-Shot |
| Code Review | Reflection + CoT | Role | Few-Shot |
| Internal Q&A | RAG + Delimiter | Constraint | Tree of Thoughts |
 
---

### 🔗 Power Combinations

| Combo | Techniques | Why it works |
|---|---|---|
| Enterprise workhorse | Role + Constraint + Output Format | Expertise + guardrails + structured output |
| Compliance & audit | RAG + Chain of Thought | Real documents + visible reasoning trail |
| Data pipelines | Few-Shot + Output Format | Pattern teaching + format lock-in |
| High-stakes reasoning | CoT + Reflection | Step-by-step logic + self-correction pass |
| Agent systems | ReAct + Prompt Chaining | Tool loop + step isolation for debugging |

---

