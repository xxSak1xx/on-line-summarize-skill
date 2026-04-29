---
name: on-line-summarize
description: Skill for improving context management by summarizing the conversation immediately after it's finished.
version: 1.0.0
---

# on-line-summarize

This skill is designed to enhance context management with a lightweight approach. Instead of complicated and carefully-designed memory compression systems, it simply summarizes the conversation immediately after it's finished. It adopts a design similar with cache-memory hierarchy to avoid repetitive reading.

## Cautions

1. Make sure you understand the difference between **conversation** and **session**.

**conversation**: A conversation refers to the exchange of messages between the user and the agent within a **single** interaction.

> begins when the user initiates a message and ends when the agent provides a response.

**session**: A session refers to a longer period of interaction between the user and the agent, which may include multiple conversations.

> begins when the user starts interacting with the agent and ends when the user stops interacting for a certain period of time (e.g., 30 minutes of inactivity).

2. Language used in the summary should be **concise and clear while not ignoring important details**. It should be consistent with the language used in the first user message of the conversation. For example, if the first user message is in English, the summary should also be in English.\\

3. The next time the user interacts with the agent, the agent should first check if there is a summary of the previous conversation. If there is, it should read the summary instead of the entire conversation history. **The original context is only read when it's really necessary**.

## Trigger

The skill is used when:
- A conversation is finished
- The user explicitly requests a summary of the conversation.

## Template

Summarize each conversation in following form:
```markdown
**TIMESTAMP**:{CURRENT_TIMESTAMP}
**USER_INPUT**:{SUMMARY_OF_USER_INPUT} 
**AGENT_RESPONSE**: {SUMMARY_OF_AGENT_RESPONSE}
**KEY_DETAILS**: {KEY_DETAILS_OF_THE_CONVERSATION}
```




