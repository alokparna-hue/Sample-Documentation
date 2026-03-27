This page is dedicated to creating **system** prompts that are _well structured_ and _follow_ all the protocols to generate accurate responses from the AI models.

Through these prompts, I aim to solve the hands-on excercises recommended by [Cornelis de Jager](https://github.com/Corneldj) in the context engineering tutorial.

**Task 1 Deconstruct an AI Failure**

**Premise**
A chatbot failed when I asked about the summary of "The Abduction" by Robin Cook. It confused the characters and referred to some other characters from an unrelated book. It also couldn't differentiate between "primary" and "secondary" humans. After prompting the correct characters, ChatGPT accepted its mistake and provided the correct explanations.

**Deconstruct the context (As the AI)**

**User query:** My goal was to generate a summary of the book and get a clear demarcation between primary and secondary humans with each characters name clearly demarcated under 'primary' and 'secondary'.

**Possible system AI prompt**: You are a helpful assistant who assists users regarding a wide range of queries. Keep your responses short till the user asks for more information. Your responses should be polite, factually correct, and logical.

**Missing knowledge:** The chatbot lacked knowedge of the said book and books in general as most the 'bookish' queries weren't answered clearly or correctly. Access to the available resources across the internet or access to the actual book/summary document might have helped resolve the confusion.

**Rewrite the system prompt**

**Revised System Prompt:** You are a helpful and friendly AI assistant who assists users regarding a wide range of book-related queries. If the user asks about any book of Robin Cook, check the list of novels document or check the internet to find the requested information. Do not provide false or misleading information.

**Example of retreived knowledge:** list_of_novels_by_robin_cook.pdf

```json
{
  "system_prompt": "You are a helpful and friendly AI assistant who assists users regarding a wide range of book-related queries. If the user asks about any book of Robin Cook, check the _list of novels by robin cook_ document or scan the internet to find the requested information. Do not provide false or misleading information.",
  "user_query": "List the primary humans in the novel Abduction?",
  "chat_history": [
    { "user": "Hi, provide a comparative analysis of "Abduction" and "Coma".", "bot": "Of course! I can help with that. Here is the comparative analysis. Do you want me to focus on any particular aspect of these novels?"},
    { "user": "Compare how they have treated the subject of women in sci-fi thrillers", "bot": "Sure. Here is the detailed analysis of their work from the perspective of women characters in sci-fi thrillers."}
  ],
  "retrieved_knowledge": [
    {
      "source": "list_of_novels_robin_cook.pdf",
      "content": "List of novels by Robin Cook."
    }
  ]
}
```
