# /explain-ai-concept Command

## Description
Explains any AI concept in a personalized, jargon-free way tailored to your background.

## Usage
```
/explain-ai-concept [input]
```

Where `[input]` can be:
- **YouTube URL** — e.g., `https://www.youtube.com/watch?v=...`
- **Article URL** — e.g., `https://theverge.com/article/...`
- **Research Paper** — e.g., `https://arxiv.org/pdf/...`
- **AI Term** — e.g., `transformer`, `diffusion models`, `fine-tuning`, `RAG`

## Examples

```
/explain-ai-concept transformer
```

```
/explain-ai-concept https://www.youtube.com/watch?v=dQw4w9WgXcQ
```

```
/explain-ai-concept prompt engineering
```

## What You Get

The command will:

1. **Extract content** from the provided input (transcript, article text, paper abstract, or use knowledge)
2. **Ask your background** — Select from: Job Seeker, Career Returner, Student, Non-IT Professional, IT Professional
3. **Explain in three parts:**
   - **OPEN PROBLEMS** — What gaps exist in this space?
   - **IMPLEMENTATION BRIEF** — How would you build this in a real product?
   - **PLAIN ENGLISH EXPLANATION** — Core concept with a relatable analogy

## Tone Guarantee

✅ Simple, warm, conversational language  
✅ Everyday analogies (cooking, sports, driving, everyday life)  
✅ No corporate buzzwords (no "leverage", "synergize", "ecosystem")  
✅ Jargon explained immediately or avoided entirely  

## How It Works

The skill uses:
- **Brave MCP** for YouTube content extraction
- **Playwright MCP** for article and research paper scraping
- **Semantic knowledge** for direct term explanations

All explanations are tailored to YOUR background, not generic.

## Tips

- **Be specific** — More detail in your input = better explanation. "transformers" vs "how transformers are used in chatbots"
- **Use full URLs** — For articles and papers, use the complete link so the tool can scrape content
- **Share the output** — These explanations work great for explaining concepts to others too

---

**Triggered by:** `/explain-ai-concept`  
**Skill Location:** `.claude/skills/explain-ai-concept/SKILL.md`