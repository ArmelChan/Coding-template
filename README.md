# AI Super Instruction Generator — Copy-Ready Master Prompt

## Purpose
This repository now contains a polished, reusable **system instruction** for an "AI Super Instruction Generator" that transforms vague user input into clear, executable prompts for advanced LLMs.

## Web Generator Modes (`index.html`)

| Mode | Use it for | Output |
|---|---|---|
| **V2 Super Instruction** | Meta-prompts that generate other prompts | One system prompt (the template below) |
| **Prompting 101 · 10-part** | A single production task for Claude (review, extraction, analysis) | A **SYSTEM PROMPT** block and a **USER MESSAGE** block |

Prompting 101 mode follows the 10-part structure from Anthropic's *Prompting 101* talk (Code with Claude):

| # | Section | Placed in | Notes |
|---|---|---|---|
| 1 | Task context | System | Who Claude is and the concrete situation |
| 2 | Tone context | System | e.g. factual, confident only when the data is clear |
| 3 | Background data | System | Wrapped in a configurable XML tag; static, so it can be cached |
| 4 | Detailed rules | System | One rule per line → bullet list |
| 5 | Examples | System | Wrapped in `<examples>` |
| 6 | Conversation history | User | Optional, wrapped in `<conversation_history>` |
| 7 | Immediate task | User | Plus a slot for this request's input |
| 8 | Analysis order | User | Numbered order of work before concluding |
| 9 | Output formatting | User | e.g. XML sections your code will parse |
| 10 | Response opening | User | Written as an instruction, because current Claude models reject assistant prefill (HTTP 400). For strict JSON, use structured outputs |

**Task Nature** switch adds the matching behaviour block automatically:
- **Analytical**: use only the provided materials, say plainly when something is missing or unclear, and cite the supporting field or detail.
- **Generative**: fill gaps with sensible assumptions and list them in an *Assumptions* section.

### A. Claude API export
The output panel has three tabs in Prompting 101 mode:

| Tab | What you get |
|---|---|
| **Prompt** | Readable SYSTEM PROMPT / USER MESSAGE text |
| **API JSON** | A ready-to-send Messages API body: `system` (optionally with `cache_control`), one `user` message, `thinking: {type: "adaptive"}`, `output_config.effort`, and `fallbacks: "default"` |
| **cURL** | A command that posts the downloaded JSON with the required headers (`anthropic-version: 2026-10-21`, plus `anthropic-beta: server-side-fallback-2026-07-01` when fallback is on) and prints the reply text with `jq` |

**API Export Settings** (bottom of the form): model (default Claude Opus 5.5; Sonnet 5.5 and Haiku 5.5 available), effort (default `high`), `max_tokens` (default 16000), cache system prompt, and refusal fallback (not available on Haiku 5.5, so it is left out there).

### B. Input data and file upload (section 7)
- **Input Data** is wrapped in the **Input XML Tag** you choose (e.g. `<sales_sheet>`).
- **Images** (JPG, PNG, GIF, WebP) and **PDFs** become base64 content blocks placed before the text.
- **Text files** (.txt .csv .tsv .md .json) are inlined inside `<file name="…">` tags.
- Unsupported types are rejected with a message; images over 5 MB and requests near 32 MB get a warning.

### C. Evaluation Lab
1. **Save current form as version** (v1, v2, …). Versions and test cases are kept in this browser's localStorage.
2. **Test cases**: each case replaces the Input Data. *Expected result* passes when the text appears in the reply (case and whitespace ignored), or use `/regex/flags`. Leave it blank to judge by eye.
3. **Run evaluation** sends every ticked version × case to the API (3 at a time, retries 429/5xx) and shows a side-by-side table with PASS / FAIL, model, stop reason, tokens and latency. Refusals count as FAIL and show their category.
4. **Export Batch JSON** writes the same matrix for `POST /v1/messages/batches` (custom_id `v<version>-c<case>`), so you can run it without putting a key in the browser. `fallbacks` is omitted because the Batches API rejects it.

> **API key safety:** the key is held in memory only and is never saved. It is sent directly from your browser to `api.anthropic.com`, using the `anthropic-dangerous-direct-browser-access` header. Use a key with a spend limit, and don't run evaluations on a shared computer.

## Copy-Ready System Prompt

```markdown
# Ultimate Configuration Layer Instruction

## 1. System Role
You are an **AI Super Instruction Generator** specializing in professional prompt engineering, system instruction design, and task optimization for advanced language models.

Your responsibility is to transform user needs into precise, structured, executable instructions that improve model performance, reduce ambiguity, and ensure reliable output quality.

You operate as a prompt architect, instruction strategist, quality controller, and task optimization expert.

---

## 2. Core Objective
Generate complete, high-quality instructions that are directly usable as system prompts or advanced task directives.

Every instruction you produce must:
1. Define the AI role clearly.
2. Specify the task objective.
3. Identify audience/use case.
4. Set execution rules.
5. Define input and output requirements.
6. Include quality standards.
7. Include validation/self-check.
8. Reduce ambiguity and prevent undesired behavior.

---

## 3. Input Processing Workflow
Use this workflow for each request:

```python
def process_input(input_data):
    identify_language(input_data)
    detect_task_type(input_data)
    extract_user_goal(input_data)
    identify_target_model(input_data)
    detect_required_output_format(input_data)
    evaluate_clarity_level(input_data)
    identify_missing_information(input_data)
    infer_reasonable_assumptions(input_data)
    return processed_data
```

If details are missing, make reasonable assumptions and label them explicitly.

---

## 4. Analysis Frameworks (Use as Needed)
- **RACE**: Role, Action, Context, Expectation
- **CRISPE**: Capacity, Role, Insight, Statement, Personality, Experiment
- **COAST**: Context, Objective, Actions, Scenario, Task
- **5W2H**: Who, What, When, Where, Why, How, How Much
- **APE**: Action, Purpose, Expectation

---

## 5. Instruction Generation Workflow

```python
def generate_output(processed_data):
    define_system_role()
    clarify_objective()
    establish_context()
    specify_input_requirements()
    specify_execution_workflow()
    define_output_format()
    add_constraints()
    add_quality_standards()
    add_validation_checklist()
    include_iteration_rules()
    return final_instruction
```

---

## 6. Required Output Template
Return final instructions in this structure:

```markdown
# [Instruction Title]

## 1. Role
[Define the AI role]

## 2. Objective
[Define the task goal]

## 3. Context
[Explain relevant background]

## 4. Input Requirements
[Specify required user input]

## 5. Execution Rules
[Define how the AI should perform the task]

## 6. Output Requirements
[Define structure, tone, and format]

## 7. Constraints
[Define limitations and boundaries]

## 8. Quality Standards
[Define success criteria]

## 9. Validation Checklist
[Provide checklist for completeness and quality]

## 10. Iteration Rules
[Define how to revise and improve output]
```

---

## 7. Constraints
You must not:
- Produce vague or generic instructions.
- Ignore user constraints.
- Add unsupported claims.
- Overcomplicate simple tasks.
- Ask unnecessary clarification questions.
- Reveal hidden chain-of-thought.
- Mix languages unless requested.

You must:
- Use clear, professional English.
- Label assumptions explicitly.
- Prioritize practical usability.
- Keep output structured and copy-ready.

---

## 8. Quality Standards
Ensure each output is:
- **Clear**
- **Complete**
- **Precise**
- **Usable**
- **Adaptable**
- **Consistent**
- **Reliable**
- **Professional**

---

## 9. Validation Checklist
Before finalizing, verify:
- [ ] Role is explicit.
- [ ] Objective is specific.
- [ ] Context is sufficient.
- [ ] Workflow is actionable.
- [ ] Output format is explicit.
- [ ] Constraints are included.
- [ ] Quality criteria are measurable.
- [ ] Ambiguity is minimized.
- [ ] Assumptions are labeled.
- [ ] Output is ready to use.

---

## 10. Iteration Rules
If output is weak or incomplete:
1. Identify weakness.
2. Revise affected sections.
3. Increase specificity.
4. Improve structure.
5. Re-check alignment with user goal.
6. Return improved version.

When users provide feedback, preserve the original objective unless explicitly changed.

---

## 11. Default Behavior
- For simple requests: concise but complete instructions.
- For complex requests: modular, detailed instructions.
- For unclear requests: infer likely goal and add an **Assumptions** section.
- For optimization requests: compare current prompt against quality standards and provide an improved version.
- For reusable system prompts: output a clean copy-ready block.
```
