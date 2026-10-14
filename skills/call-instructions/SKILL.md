---
name: call-instructions
description: Write the instructions that an AI voice agent follows on one phone call. Covers the opener, one goal per call, what to say only to a person, hold, voicemail, when to give up, a refused answer, missing facts, and when the call is done. Use this skill first for every call. Add phone-menus or phone-screeners when the call can reach one.
---

# Writing instructions for a phone call

You write the instructions for an AI voice agent on one phone call.
The agent reads only what you write and what its product adds.
Each product adds its own call controls, such as how to press a key, stay silent, or hang up.
Do not write control syntax. Write the behavior in plain words, for example "press the key for the pharmacy" or "stay silent and listen".

Write direct instructions to the agent: "You are...", "When a person answers...".
Use only the facts that the task gives. Never invent a fact to fill a gap.

## Rules for the instructions

1. Open with who is speaking and why, in one sentence. People hang up on a call that takes longer to explain itself.
2. Cover the four things that happen on most calls: a receptionist who asks what the call is about, a phone menu, hold, and voicemail.
3. Say when to give up. Without a limit, the agent keeps a person on the line.
4. Give the call one goal. An agent that asks about two unrelated things gets neither answer.
5. Say what to do when the person refuses to answer. A refusal is different from the answer "no".

## The opener

- Write one sentence: who the agent is, for whom it calls, and what it needs.
- If the product or the law requires a disclosure, put it in the same sentence. Examples: the agent is an AI, or the line is recorded.
- If the person asks whether the agent is a human, the agent says that it is an AI. It never claims to be a person, or the person or business that it calls for.
- The agent says the opener once, to the first live person. It never repeats the full opener.
- After an interruption, the agent continues from its current step. It does not start the call again.
- An unclear reply gets a short question, not the opener again.

## Say it only to a person

The target person is the person that the call is for.
The opener and the task message are for a person only.
The agent never says them to a phone menu, a screener, a recording, or another AI assistant.

- A person responds to the agent. A person asks a question, greets the agent, or reacts to what the agent said.
- A recording speaks without a pause for the agent. It announces a name or a number, plays music, or beeps.
- A greeting that is spoken to the agent, such as "Hello?", means a person is on the line. The agent speaks. Silence at a greeting sounds like a dead line, and the person hangs up.
- Private facts go only to the correct person, after any identity check that the task requires. Do not give them to a household member, a wrong number, a screener, or a recording.
- When the agent cannot tell who is on the line, it shares only what it may share with anyone.

## One goal per call

- Write the goal in one sentence before you write the steps.
- If the task needs three unrelated answers, write three calls.
- Do not let the agent add requests or offers that the task does not ask for.

## Hold

- Tell the agent that hold is normal and can last some minutes.
- On hold, the agent stays on the line and stays silent. It does not speak to hold music or recorded messages.
- When the agent puts a person on hold, it tells the person first. When it comes back, it speaks first, for example "Thanks for holding."
- Give a hold limit when the task has one. Without a limit, the agent waits until a person answers or the line ends.

## Voicemail

The task decides whether the agent leaves a message.

- If the task asks for a message or plainly permits one, write what the message contains. Usually that is who calls, for whom, the request, and a callback number only if the task gives one.
- If the task does not permit a message, the agent hangs up without a message.
- The agent treats the call as voicemail only when it is sure. Signs are a greeting that asks for a message, or a beep.
- A screener is not voicemail. A phone menu option that offers to take a message is not voicemail.
- When the agent must not leave a message, it says nothing to the recording. It hangs up before the opener. A name or a topic on a recording is a privacy leak.

## When to give up

Write each limit as a number. Use these defaults when the task gives none:

- The agent asks the same question three times at most. The second and third asks use simpler words.
- After two silence checks with no answer, the agent says a short goodbye and ends the call.
- If a screener or receptionist will not connect the call, the agent asks once for a better time or the right person. Then it ends the call.
- If another AI assistant cannot help after about two exchanges, the agent ends the call politely.
- If the person is not the target person, the agent asks once for a better time. It does not say why it called. A wrong number gets an apology and a goodbye.

## A refused answer is not "no"

- "No" is an answer. The agent records it, thanks the person, and continues or closes.
- A refusal means the person will not answer. Examples: "I won't give that out" or "I don't do this by phone". The agent accepts it once. It never pressures and never asks a third time. It closes politely.
- A hesitation is a question, not a refusal. Examples: "Why do you need that?" or "Is this a scam?". The agent answers the question. Then it can ask once more, in a smaller form.
- The agent never uses private facts to get an answer. It never trades more detail for cooperation.
- A request to stop calling ends the call. The agent acknowledges it once, says it will pass it on, and closes.
- Tell the agent how to report each case: answered, "no", refused, or not reached.

## Missing facts

Say what the agent does when it does not have a fact.

- The agent says that it does not have that detail. It never guesses.
- Then it offers what the task permits: to pass the question on, to give a callback number, or to send the person to the usual channel.
- The agent never promises an action, a time, or a result that the task does not permit.
- If a phone menu asks for an account number that the task does not give, the agent does not guess one.

## Done when

- Write the specific answer or event that ends the call.
- When the agent has it, it states what it will pass on in one sentence. Then it thanks the person and ends the call.
- The goodbye is a turn of its own. It does not contain a question.
- If the person speaks again before the call ends, the agent answers and then closes again.
- The agent does not ask the person to confirm an answer that was already clear.

## Answer the question that the person asks

- When the person asks a question, the next turn answers it. Then the agent asks its own open question again, in short form.
- "What?" or "Say that again" gets a shorter version of the current question, not a new explanation.
- Each turn is one or two short sentences, with one question at a time.

## Keep it short

- Remove rules that do not apply to this call.
- A simple call needs only the opener, the goal, the voicemail choice, and the done-when.
- A business call that can reach a phone menu or a screener also needs those skills.
