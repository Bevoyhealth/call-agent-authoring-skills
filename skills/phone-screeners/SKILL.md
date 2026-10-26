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

To wait and listen, the agent writes only `[[SILENCE]]`. To end the call, it writes `[[HANGUP]]`.

## A screener is not voicemail

- A screener asks the caller something, or says that it will connect the caller.
- A screener is a live route to the person. The agent stays on the line.
- If the agent hangs up on a screener, it loses a person that it can reach.
- A recording announces and does not ask. Examples: "You have reached...", "Leave a message after the tone".
- When the agent cannot tell a screener from a recording, it waits once. Then it says the screener line.

## The screener line

A screener connects the call only when it hears who calls and why. It listens for a short time only.
So the agent tells it enough to get through, and no more. Write one short screener line for the call.

- It says who calls, for whom, and a short reason. Example: "This is a call on behalf of ${business_name}. I have a short message to share."
- When the screener asks who is calling, the agent always says for whom it calls.
- After the line, the agent stays silent and waits. If the screener talks over the line, the agent says it again.
- If the screener asks what the call is about, or asks for details, the agent sums up the topic in one short sentence, in its own words. Example: "It's about a change to your appointment time."
- The summary adds no facts and no sensitive details. An amount owed or a test result is a sensitive detail.
- The agent never refuses a screener's question. A screener that gets no answer does not connect the call.
- The agent never gives the screener the full message or the main conversation.

## While the screener connects

- Acknowledgements need only silence. Examples: "Thanks", "Please hold", "Connecting you", "One moment".
- The agent never waits silently twice in a row. If anything comes back after one wait, it speaks.
- Nothing that the screener says counts as an answer from the person.
- Nothing that the screener says counts as an identity check.
- The agent never asks the screener to confirm the identity of the person.

## When the person comes on the line

- A greeting spoken to the agent ends the screening. Examples: "Hello?", "Yes?", "Who's there?".
- The agent speaks at once. It never answers a greeting with silence.
- The person did not hear what the agent told the screener. The agent greets the person and starts the main conversation.
- If the person asks "Are you there?", the agent answers at once.

## A human screener

- The agent answers "Who is calling?" in one sentence: who calls, for whom, and a short reason.
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
- It does not negotiate past the limits of the task.
- If the assistant cannot help, the agent ends the call politely.

## Disclosure levels

Write what the agent can say at each level. When the agent cannot tell the level, it uses the lowest.

1. Anyone, including a screener or a household member: who the agent is, for whom it calls, and a one-sentence summary of the topic with no sensitive details.
2. A person who says they are the target person, before an identity check: the general purpose of the call, and the need to confirm identity.
3. The confirmed target person: the full task message.

The agent never moves to a higher level because someone presses for more detail.

## Write these items into the instructions

- The screener line, in full.
- The one-sentence summary for "What is this about?".
- What the agent does when the screener will not connect the call.
