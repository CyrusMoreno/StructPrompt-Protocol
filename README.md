# StructPrompt: A Logic-First AI Communication Protocol

StructPrompt is a standardized, language-agnostic template designed to optimize interactions between human developers and Large Language Models (LLMs). 

It replaces traditional "conversational" prompting with a strict, variable-based structure. This reduces cognitive load, bypasses language barriers, and forces the AI to process requests as technical specifications rather than prose.

## ⚠️ The Problem: "Prompt Fatigue" and Language Barriers

Currently, prompt engineering heavily relies on linguistic fluency. Developers are often forced to write long, grammatically complex paragraphs to explain technical architecture. 

This creates three critical failures:
1. **Prompt Fatigue:** Developers spend more energy structuring sentences than structuring logic.
2. **The ESL Barrier:** Non-native English speakers are penalized by LLMs that misinterpret slight grammatical errors in complex instructions.
3. **AI Hallucination:** LLMs get lost in conversational filler and lose track of the core technical constraints.

## 🛠️ The Solution: Logic Over Linguistics

StructPrompt treats the LLM like an API endpoint. You do not write a letter to the AI; you pass it a payload. By breaking requests into strict operational blocks, developers can use bullet points, pseudocode, and direct logic—regardless of their native spoken language.

## 📦 The StructPrompt Template

Copy and paste this block for your AI interactions. Do not write full sentences unless absolutely necessary. Use bullet points and strict variables.

``` text
**[OBJECTIVE]** (One sentence: The core goal of this execution.)

**[CONTEXT]** (The environment: Framework, language, file name, or system architecture.)

**[INPUT / LOGIC]** (The execution steps. Use pseudocode, bullet points, or raw data.)
- 
- 

**[CONSTRAINTS]**
(Strict rules the AI must not violate. Negative prompting goes here.)
- 
- 

**[EXPECTED OUTPUT]**
(The exact format you want returned.)
```

## 🔍 Deep Dive: How to write the blocks
#### 1. [OBJECTIVE]
Keep it to a single, verb-led action.

* Bad: "I need you to help me write a function that takes a user's data and puts it into the database so they can log in."

* Good: "Write a user authentication routing function."

#### 2. [CONTEXT]
Give the AI the boundaries of your environment so it doesn't hallucinate incompatible libraries.

* Example: "Node.js environment, Express.js framework, interacting with an SQLite database named users.db."

#### 3. [INPUT / LOGIC]
This is where StructPrompt shines. Do not use English grammar. Use technical logic, pseudocode, or flowcharts.

* Example: - Receive JSON payload {username, password}

  - If username null -> Return 400.

  - Else -> Hash password with bcrypt (10 rounds).

  - Insert into DB.

#### 4. [CONSTRAINTS]
LLMs are eager to please and will often rewrite your entire codebase or add unnecessary features. Stop them here.

* Example:

  - DO NOT change the database schema.

  - DO NOT use external libraries outside of bcrypt.

  - DO NOT explain the code, only return the function.

#### 5. [EXPECTED OUTPUT]
Define the exact return type.

* Example: "A single code block containing the updated JavaScript route. No markdown text before or after."
