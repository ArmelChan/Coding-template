[繁體中文（香港）](quick-start.zh-HK.md) | English

# Quick Start: AI Prompt Generator

This tool helps you turn rough ideas into clear, reusable instructions for AI. Describe the task, add the information the AI should use, and choose how you want the answer formatted. Then copy the generated prompt into an AI chat tool and try it out.

> **Creating a prompt is not the same as running it.**
> This tool only writes the instructions. You get an answer only when you give them to an AI model, for example in a chat tool. Filling in the form doesn't produce any AI analysis.

## What does this tool do?

Many people start with a one-line request:

> "Summarise our sales."

The AI then has to guess which stores, which numbers, what to compare and how long to write. If information is missing, it may simply make something up.

With this tool, you add what the AI needs:

| You add | Example |
|---|---|
| The information to use | This week's and last week's sales for each store |
| Rules | Use only these figures. If a number is missing, say so. |
| The answer format | Three bullet points |

Now the AI knows much more clearly what to deliver. That makes a good answer more likely, not certain, so always check it yourself.

## Your first prompt in four steps

Open the tool's web page (the `index.html` file in this project) in your browser.

### 1. Choose `Prompting 101`

At the top of **Generator Inputs**, click **`Prompting 101 · 10-part`**. Its labelled boxes show clearly how a good prompt is built, so it's the best place to start. The original **`V2 Super Instruction`** mode is still there; ignore it for now.

### 2. Fill in the task, the information and the format

You don't need all ten sections. For the example below, fill in only these boxes:

- **`1 Task Context`**: who the AI is helping, and with what
- **`4 Detailed Task Description & Rules`**: the rules, one per line
- **`7 Immediate Task / Request`**: what to do this time
- **`Input Data (this request)`**: this request's information (just below box 7)
- **`9 Output Formatting`**: what the answer should look like

### 3. Pick `Analytical` or `Generative`

In **`Task Nature`**:

- **`Analytical`**: uses only the information you provide, and points out anything missing.
- **`Generative`**: may suggest ideas or make inferences, but must list its assumptions.

The sales example needs facts, not guesses, so choose **`Analytical`**.

### 4. Generate, copy, and try it in an AI chat tool

Click **`Generate Prompt`**. The **`Prompt`** tab under **Generated Prompt** shows two parts:

- **`SYSTEM PROMPT`**: the overall rules (the AI's role and what it must always follow)
- **`USER MESSAGE`**: what to do this time (the request, the data and the format)

**`Copy`** copies both parts with their headings. If your chat tool has one message box, paste everything in the same order, keep both heading lines, and send.

```text
===== SYSTEM PROMPT =====
(overall rules...)

===== USER MESSAGE =====
(what to do this time...)
```

The AI reads it all as one message. That's fine for testing, but it isn't the same as the separate `system` setting a program uses. If **Copy** doesn't work, select the text and copy it yourself.

## A copy-ready example

All figures are made up. Copy each block into the matching box.

**`Prompt Name`**

```text
Weekly sales summary
```

**`Task Nature`**: `Analytical`

**`1 Task Context`**

```text
You are helping a shop manager write a short weekly sales summary for two stores.
```

**`4 Detailed Task Description & Rules`**

```text
Only use the figures provided.
Only make comparisons that the data supports.
If a figure is missing, say that it is missing. Do not estimate the change.
Do not guess why sales went up or down.
```

**`7 Immediate Task / Request`**

```text
Write this week's sales summary for Store A and Store B.
```

**`Input Data (this request)`**

```text
Store A: 120 units sold this week; 100 units last week
Store B: 80 units sold this week; last week not provided
```

**`9 Output Formatting`**

```text
Three bullet points, one sentence each. Show any change as units and as a percentage.
```

**What a good answer looks like** (the exact wording will vary):

```text
- Store A sold 120 units this week, up 20 units (20%) from 100 last week.
- Store B sold 80 units this week; last week's figure was not provided, so no weekly change can be given.
- This week, Store A sold 40 more units than Store B (120 vs 80).
```

Check that Store A is up exactly 20 units (20%), and that Store B has no estimated change and no made-up reason. If not, make the rules clearer and try again.

## What can I try next?

- **Add files (`Attach Images / Files`)**: Add a table, document or picture for the AI to refer to (JPG, PNG, GIF, WebP, PDF, or text files such as .txt or .csv), below box 7. In a chat tool, attach images and PDFs yourself, and never upload customers' personal data or confidential files.
- **Compare two versions (`Evaluation Lab`)**: To see which of two summary instructions works better, scroll down to **Evaluation Lab** (Prompting 101 mode), click **`Save current form as version`**, edit the instructions, save again, and add the same sales data with **`Add case`**. Under **`3 · Run`**, choose **`Manual · claude.ai (no key)`**, then **`Build worksheet`**, to copy each prompt into claude.ai and paste the answers back; use the same model for both so any difference comes from the prompt.
- **Connect to a program (`API JSON` / `cURL`)**: To plug the prompt into code or an automated workflow, use the **`API JSON`** or **`cURL`** tab. A chat tool needs no Claude API key; you need one only to send requests to the Claude API, such as running the exported request or **`Run evaluation`** with the **`API key`** option.

> The Claude API features have so far been tested only against simulated responses, not the real Claude API. If you use them, start with one small example.
