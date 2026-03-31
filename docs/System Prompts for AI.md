## **Introduction**

This page is dedicated to creating **system** prompts that are _well structured_ and _follow_ all the protocols to generate accurate responses from the AI models. Through these prompts, I aim to solve the hands-on excercises recommended by [Cornelis de Jager](https://github.com/Corneldj) in the context engineering tutorial.

## **Task 1 Deconstruct an AI Failure**

**Premise**

A chatbot failed when I asked about the summary of "The Abduction" by Robin Cook. It confused the characters and referred to some other characters from an unrelated book. It also couldn't differentiate between "primary" and "secondary" humans.

**Deconstruct the context (As the AI)**

**User query:** The primary goal was to generate a summary of the book and get a clear demarcation between primary and secondary humans, with each character divided between 'primary' and 'secondary'.

**Possible system AI prompt**: You are a helpful assistant who assists users with a wide range of book-related queries. Keep your responses short and polite. If you do not know the answer to any user query, provide a generic response.

**Missing knowledge:** The chatbot lacked knowedge of the said book and books in general as most the 'bookish' queries weren't answered clearly or correctly. Access to the available resources across the internet or access to the actual book/summary document might have helped resolve the confusion.

## **Revised System Prompt:**

```
You are a helpful and friendly AI assistant who assists users with a wide range of book-related queries. If the user asks about any specific work, check the list of novels document or check the internet to find the requested information. If the data to answer a question is not available in the context, you must state that you do not have that specific information. Do not provide false or misleading information.
```

**Example of retrieved knowledge:** list_of_novels_by_robin_cook.pdf

```json
        {
          "retrieved_knowledge": [
            {
              "source": "list_of_novels_by_robin_cook.pdf",
              "book_name": "Abduction",
              }
            ]
          }
```

## **Design a High-Density Prompt**

**Scenario:** You need to build an AI assistant that classifies customer support emails into one of three categories: [Billing], [Technical Support], or [General Inquiry].

```python
system_prompt = """
# ROLE: Customer Support Email Bot
You are a helpful AI assistant that catergorizes customer support emails into three categories- [Billing], [Technical Support], and [General Enquiry].

# INSTRUCTIONS:
Your primary goal is to classify the emails into the three categories for proper routing to the respective teams.
**[Billing]**: Use this for queries or emails related to invoice, pricing, and billing.
**[Technical Support]**: Use this for queries or concerns related to app support or any technical difficulties faced by users.
**[General Inquiry]**: Use this for queries or concerns related to the general topics.

# RULES:
- NEVER invent a new category.
- Always check the user emails before categorizing.

# OUTPUT FORMAT:
- Return _only_ one of the three category tags and nothing else.
"""
```
