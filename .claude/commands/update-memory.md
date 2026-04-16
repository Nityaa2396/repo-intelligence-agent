# Update Memory Command

## Command: /update-memory

When this command is triggered, it should perform the following actions:

### 1. Analyze Current Conversation Context
- Review the last 10 conversations for key information
- Identify new decisions, learnings, and project changes
- Extract relevant context that should persist

### 2. Update memory.md Content

#### Keep (Essential Information)
- Key decisions made during the conversation period
- Current project structure and architecture
- Tools and technologies being used and their rationale
- Active goals and objectives
- Important learnings and insights
- Project vision and long-term objectives

#### Remove (Outdated Information)
- Completed setup steps that are no longer relevant
- Resolved issues that have been fixed
- Redundant or duplicate notes
- Temporary workarounds that are no longer needed
- Outdated goals that have been achieved or superseded

### 3. Content Organization
- **Current Project Context:** Update with latest project status
- **Key Decisions:** Add new decisions, keep important historical ones
- **Tools and Technologies:** Update with newly adopted tools, remove discontinued ones
- **Current Goals:** Refresh with active objectives, remove completed ones
- **Learnings and Insights:** Add new insights, consolidate similar learnings

### 4. Maintenance Tasks
- Update the "Last updated" timestamp
- Ensure the memory file remains concise (aim for < 500 lines)
- Verify all links and references are still valid
- Check for any broken formatting or incomplete sections

### 5. Confirmation Output
After updating, provide confirmation of:
- What new information was added
- What outdated information was removed
- Current memory file status (line count, sections updated)
- Any recommendations for future updates

### 6. Automation Triggers
- Command should be triggered manually with `/update-memory`
- Should also trigger automatically every 10 conversations
- Can be triggered early if significant project changes occur

### 7. Best Practices
- Always preserve critical project context
- Use clear, concise language
- Maintain chronological order where relevant
- Include dates for all new entries
- Cross-reference related decisions and learnings