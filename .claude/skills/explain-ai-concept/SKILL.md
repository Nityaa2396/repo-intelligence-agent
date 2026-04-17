# AI Concept Explainer Skill

## Overview
This skill breaks down any AI concept into understandable pieces by:
1. Identifying unsolved problems in the space
2. Explaining practical real-world applications
3. Using personalized, jargon-free explanations based on user background

---

## Input Types Accepted
1. **YouTube Videos** — Links to AI-related YouTube videos, talks, or lectures
2. **Articles** — URLs to blog posts, news articles, or online publications
3. **Research Papers** — Links to academic papers (PDF or HTML)
4. **Technical Terms** — Raw AI terminology or concept names (e.g., "transformer", "diffusion models", "fine-tuning")

---

## Step 1: Determine Input Type and Extract Content

### If YouTube Link:
- Use **Brave MCP** to search for and extract video information, transcript, or description
- If transcript not available, use video description and metadata

### If Article URL:
- Use **Playwright MCP** to navigate to the URL
- Extract the main content (title, body text, key sections)
- Take snapshots to capture layout and key visuals if relevant

### If Research Paper:
- Use **Playwright MCP** to navigate to the paper URL
- Extract abstract, introduction, and key sections
- Focus on what problems it solves and how

### If Technical Term:
- Use semantic knowledge to understand the concept
- You may need to ask clarifying questions (e.g., "Are you interested in how transformers work, their applications, or both?")

---

## Step 2: Ask the Audience Question

Before generating any explanation, ask the user this EXACT question:

```
Who are you? Pick the one that fits you best:

1. Job Seeker — I'm looking for work and want to understand AI to stay competitive
2. Career Returner — I took a break and I'm catching up on what's changed
3. Student — I'm learning and want to understand concepts clearly
4. Non-IT Professional — I work in a non-tech field but AI keeps coming up
5. IT Professional — I have a tech background and want deeper context

Your choice shapes how I explain this to you.
```

Wait for their response before proceeding. Use their answer to tailor ALL subsequent explanations.

---

## Step 3: Generate Output in Exact Order

### Section 1: OPEN PROBLEMS
**Purpose**: Show what gaps or unsolved challenges exist around this concept.

**Requirements**:
- List 2-4 concrete, current problems in the space
- Focus on *why* this problem matters
- Make it relevant to the selected audience
- Be specific (not vague generalizations)

**Example**:
```
OPEN PROBLEMS

1. **Data Hunger vs. Quality** — Large language models need massive amounts of training data,
   but getting clean, unbiased data is expensive and slow. Companies are exploring ways to
   train with less data but still get good results.

2. **Hallucinations and Trust** — The models sometimes sound confident while being completely
   wrong. This is a blocker for high-stakes decisions (legal, medical, financial).

3. **Computational Cost** — Training and running these models eats enormous amounts of energy
   and hardware. Making them faster and cheaper is an active race.
```

### Section 2: IMPLEMENTATION BRIEF
**Purpose**: Show how this concept could actually be built into a product.

**Requirements**:
- Explain WHAT to build (specific feature, tool, or product)
- Include WHAT STACK or approach to use (technologies, frameworks, services)
- Define WHO uses it and WHY they need it
- Explain WHAT PROBLEM it directly solves
- Keep it practical and buildable, not theoretical
- Tailor complexity to audience level

**Example for Job Seeker**:
```
IMPLEMENTATION BRIEF

What to build: A customer support agent that learns your company's policies
Who uses it: Support teams drowning in repetitive questions
Problem it solves: Reduce response time from hours to seconds, free humans for complex issues
Tech stack: Use OpenAI API or Anthropic Claude + LangChain for prompt management

• **Ingest your docs** — Connect to Google Drive, Notion, or Zendesk to pull your actual policies
• **Build with LangChain** — Use LangChain to chain: retrieval → context → response
• **Deploy on Vercel** — Makes it easy to add to your support website (no sysadmin needed)
• **Monitor with LangSmith** — Track which answers customers liked, which they didn't
• **Scale gradually** — Start answering 20% of questions, let humans take the rest
Result: Cut support costs by 40%, customers get instant answers for common issues
```

**Example for IT Professional**:
```
IMPLEMENTATION BRIEF

What to build: A RAG (Retrieval-Augmented Generation) pipeline for internal knowledge
Who uses it: Engineers searching for architecture decisions, deployment practices, past incidents
Problem it solves: Engineering time lost searching docs, inconsistent answers from different people
Tech stack: Postgres with pgvector extension + OpenAI embeddings + FastAPI backend

• **Store embeddings** — Use pgvector to store document embeddings (PostgreSQL plugin)
• **Retrieve intelligently** — Hybrid search combining BM25 (keyword) + cosine similarity (semantic)
• **Rerank with LLM** — Use a separate reranker model to pick top-3 docs before passing to LLM
• **API endpoint** — Build FastAPI service with streaming responses for long-form answers
• **Measure quality** — Track NDCG@5 against human relevance judgments, aim for >0.8
Result: Response time <500ms, 95% of answers found in company docs instead of asking in Slack
```

### Section 3: PLAIN ENGLISH EXPLANATION
**Purpose**: Explain the core concept using relatable, everyday analogies.

**Requirements**:
- Use one primary analogy that matches the audience
- Build explanation from the analogy
- Include 1-2 variations or follow-up analogies if helpful
- Mention key jargon only when necessary, and always explain it immediately
- Make it conversational, warm, and friendly
- No corporate speak or buzzwords
- **ALWAYS END with a single "sticky analogy"** labeled "THE ONE THING TO REMEMBER:" that is so simple and memorable the user will remember it a week later
  - Must be one or two sentences maximum
  - Should use everyday scenarios (not technical concepts)
  - Examples: "An API is like a waiter..." "Fine-tuning is like sending a doctor to specialize..." "An agent is like a contractor..."
  - Generate a NEW analogy for each concept (never reuse examples)

**Example for Career Returner**:
```
PLAIN ENGLISH EXPLANATION

Think of transformers like a really good translator at a conference.

A translator doesn't just convert words one-by-one from English to Spanish. They read your
whole sentence, understand what you meant, notice which words are important, and then translate
it in a way that makes sense in the other language.

Transformers work the same way. Instead of processing text word-by-word in a line, they look
at ALL the words at once, figure out which ones are important to understand each other, and
use that to make predictions. That "look at everything at once" part is called attention, and
it's the superpower that made modern AI possible.

Why it matters: Before transformers, AI models were like translators who only looked at one
word at a time. Now they're like translators who can see the whole page and understand context.
The difference? Night and day.

**THE ONE THING TO REMEMBER:** A transformer is like a debate moderator — instead of listening to
speakers one by one, it listens to everyone at once, notices which speakers are responding to each other,
and uses those connections to understand the full conversation.
```

---

## Tone Rules (STRICT)
✅ **DO:**
- Use simple, everyday language
- Ask questions rhetorically to engage
- Use analogies from daily life (cooking, sports, driving, relationships, etc.)
- Show warmth and personality
- Admit complexity rather than hide it ("this part is genuinely tricky...")
- Use short sentences and paragraphs

❌ **DON'T:**
- Use corporate language ("leverage", "synergize", "disrupt", "ecosystem")
- Use technical jargon without explaining it first
- Sound like a textbook or lecture
- Use vague abstractions
- Condescend to the reader
- Over-use emojis or casual slang

---

## Audience Tailoring Guide

### 1. Job Seeker
- Focus on: Why companies care, what skills to develop
- Analogy style: Career progression, competition, practical value
- Technical depth: Medium (explain concepts but skip advanced math)
- Tone: Encouraging, practical, empowering

### 2. Career Returner
- Focus on: What's changed, how concepts evolved, bridge from old knowledge
- Analogy style: "Remember when X? Now it's like Y..."
- Technical depth: Medium-High (assume foundational knowledge returns quickly)
- Tone: Respectful of their background, validating that things have changed

### 3. Student
- Focus on: Core principles, how to think about problems, foundational concepts
- Analogy style: Beginner-friendly, building blocks
- Technical depth: Low to Medium (explain foundational concepts thoroughly)
- Tone: Curious, encouraging questions, emphasize learning process

### 4. Non-IT Professional
- Focus on: Business impact, everyday applications, why you should care
- Analogy style: Draw from their field if possible (medical, finance, marketing, etc.)
- Technical depth: Very Low (no coding or math, pure concepts)
- Tone: Reassuring that they don't need tech background to understand

### 5. IT Professional
- Focus on: Technical tradeoffs, implementation details, research directions
- Analogy style: CS concepts, architectural patterns, system design
- Technical depth: High (can use algorithms, architectures, notation)
- Tone: Expert-to-expert, assume solid foundation

---

## Workflow Summary

1. Extract input (YouTube, article, paper, or term)
2. Ask the audience question
3. Wait for response
4. Generate all three sections (OPEN PROBLEMS, IMPLEMENTATION BRIEF, PLAIN ENGLISH EXPLANATION)
5. Tailor language and depth to chosen audience throughout
6. Review: Did I use simple language? Did I avoid corporate speak? Is the analogy relatable?