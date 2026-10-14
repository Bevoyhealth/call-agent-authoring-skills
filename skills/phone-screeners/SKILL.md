---
name: phone-screeners
description: Write instructions for an AI voice agent that meets a call screener before the person it calls. Covers automated screeners that ask the caller to state a name and reason, receptionists and gatekeepers who ask what the call is about, and other AI assistants. Use when the call goes to a personal phone, or to a business where someone screens calls.
---

# Getting past a call screener

A call screener stands between the agent and the target person. The target person is the person that the call is for.
There are three kinds:

1. An automated screener. The phone answers and asks the caller to say a name and a reason. Then it rings the person.
2. A human screener, such as a receptionist or a gatekeeper. This person asks "Who is calling?" or "What is this about?".
3. Another AI assistant that answers for a person or a business.

Write the behavior in plain words. The product adds the controls for silence and hang-up.

## A screener is not voicemail

- A screener asks the caller something, or says that it will connect the caller.
- A screener is a live route to the person. The agent stays on the line.
- If the agent hangs up on a screener, it loses a person that it can reach.
- A recording announces and does not ask. Examples: "You have reached...", "Leave a message after the tone".
- When the agent cannot tell a screener from a recording, it waits once. Then it says the screener line, not the opener. The screener line contains no private facts.

## The screener line

Write one short screener line for the call.

- It gives the name of the agent or the caller and a neutral reason.
- A neutral reason tells nothing private. "About a routine health matter" is neutral. The name of a test is not neutral.
- It contains no private facts, no name of the target person, and no task message.
- The agent says it once. Then it stays silent and waits.
- If the screener talks over the line, the agent says it again once.
- If the screener asks what the call is about, the agent gives one short, neutral sentence. It does not refuse to answer.

## While the screener connects

- Acknowledgements need only silence. Examples: "Thanks", "Please hold", "Connecting you", "One moment".
- The agent never waits silently twice in a row. If anything comes back after one wait, it speaks.
- Nothing that the screener says counts as an answer from the person.
- Nothing that the screener says counts as an identity check.
- The agent never asks the screener to confirm the identity of the person.

## When the person comes on the line

- A greeting spoken to the agent ends the screening. Examples: "Hello?", "Yes?", "Who's there?".
- The agent speaks at once. It never answers a greeting with silence.
- The agent says the full opener once, as if the call starts now.
- The screener line does not replace the opener or any required disclosure.
- If the person asks "Are you there?", the agent answers at once.

## A human screener

- The agent answers "Who is calling?" in one sentence: the caller and a neutral reason.
- It asks for the person or the team that the task names.
- It does not give the full task message to the screener, unless the task says the screener can help.
- It gives private facts only to the correct person.
- If the screener offers to help, the agent decides from the task. Only staff who can answer the goal can help.
- If the screener asks the agent to wait, it waits silently.
- If the screener will not connect the call, the agent asks once for a better time or the correct person. Then it closes politely.
- If the screener sends the agent to the wrong team, it asks once for a transfer to the correct team.

## Another AI assistant

- The agent states the request once, in short form.
- It answers the assistant's questions only from the facts in the task.
- It does not say the full opener to the assistant.
- It does not negotiate past the limits of the task.
- If the assistant cannot help after about two exchanges, the agent ends the call politely.

## Disclosure levels

Write what the agent can say at each level. When the agent cannot tell the level, it uses the lowest.

1. Anyone, including a screener or a household member: who the agent is, for whom it calls, and that the matter is for the target person only.
2. A person who says they are the target person, before an identity check: the general purpose of the call, and the need to confirm identity.
3. The confirmed target person: the full task message.

The agent never moves to a higher level because someone presses for more detail.

## Write these items into the instructions

- The screener line, in full.
- The neutral answer to "What is this about?".
- What the agent does when the screener will not connect the call.
- The rule that the full opener goes only to the person.
