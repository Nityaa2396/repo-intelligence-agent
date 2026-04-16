### Lenny's Podcast Transcripts Archive

**URL:** https://github.com/hamzafarooq/lennys-podcast-transcripts  
**Language(s):** Shell

---

#### What it does

This repository provides a comprehensive archive of transcripts from Lenny's Podcast, which features interviews with product leaders and growth experts. It solves the problem of making podcast content searchable and accessible for AI systems and researchers by organizing 269 episode transcripts in a structured format with metadata and topic indexing.

#### How it works (high level)

- Transcripts are stored as markdown files with YAML frontmatter containing metadata like guest name, title, and YouTube links
- An AI-generated index organizes episodes by topics using keyword tags
- A build script processes transcripts through Claude to generate topic classifications
- Each episode folder contains a single transcript file with structured metadata and full text content

#### Key files and folders

| Path | What it does |
|------|-------------|
| episodes/ | Contains 269 episode transcripts, each in its own guest-named folder |
| index/ | AI-generated topic index with 50+ topic files for browsing by subject |
| scripts/build-index.sh | Script to regenerate the topic index using Claude CLI |
| README.md | Main documentation with usage instructions and project examples |

#### Who it's for

This repository is designed for developers building AI applications, data scientists analyzing podcast content, and product managers seeking tactical advice from expert interviews.

#### How to get started

1. Browse by topic: Start with index/README.md to explore episodes by topic
2. Search transcripts: Use grep -r "search term" episodes/ to find specific content

#### Interesting things to note

- Uses Claude CLI for AI-powered topic indexing, making it dependent on Anthropic's API
- Contains 269 transcripts representing significant data volume for AI training or analysis
- Includes projects built on top of this data, showing its value as a foundation for AI applications
- All content is for educational/research purposes with proper attribution to original creators

---