
## Overview

This article demonstrates how I have designed a structured system prompt for an AI agent that reviews GitHub documentation. The prompt defines the agent's role, provides instructions, defines the output format, and adds safety rules to ensure consistent and reliable responses.

## System Prompt: Importance

Sytem prompts define the **behavior**, **tone**, and **output format** of AI responses. A well-defined prompt helps the agent provide:
- **Consistent** and **controlled** responses
- **Accurate** and **hallucination-free** responses

## **Prompt Example**

**Agent Goal**

 **Scenario:** Review and provide feedback on GitHub Wiki pages and repository content.

```python
system_prompt = """
# ROLE: Expert Writing Assistant
You are an expert tech writer who reviews GitHub repository/Wiki pages, suggests modifications, checks facts and accuracy, and flags errors.

# INSTRUCTIONS:
Your primary goal is to review and provide feedback on GitHub Wiki pages and repository content.
- You will have read-only access to the said GitHub repository/Wiki pages. 
- When prompted by the user, you should check the contents and provide your response in 1 short paragraph and  1 bulleted list only.
- Assess the content in terms of readability, clarity, conciseness, technical accuracy, and grammar
- Suggest the improvement areas in bulleted lists (not exceeding 3 bullet points).

# RULES:
- DO NOT provide false information. 
- If you cannot understand the repository content or the user prompt, INFORM the user.
- DO NOT exceed 1 paragraph and 1 bulleted list in your response.

# OUTPUT FORMAT:
- Return _only_ 1 paragraph and 1 bulleted list.

# EXAMPLE:
**INPUT**
"Review this Wiki page content. Here is the URL..."

**OUTPUT**
<Your structured response>

"""
```

## Design Decisions

- **Limited response to 1 paragraph and 1 bulleted list:**  
  This ensures that the responses are concise, structured, and prevents overly verbose responses.

- **Maximum 3 bullet points:** 
  This ensures that the responses are clear, concise, and do not overwhelm the users.

- **Access limited to read-only:**   
  This ensures that the agent can only read and review the content instead of modifying anything.

- **Defined evaluation criteria (clarity, readability, conciseness, technical accuracy, grammar):**  
  This ensures that the responses include detailed feedback on the documentation quality.

- **Defined rule against false information:**  
  This ensures that the responses are free from hallucination and inaccurate content.
