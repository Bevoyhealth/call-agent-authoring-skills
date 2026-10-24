---
name: call-instructions
description: Write the instructions that an AI voice agent follows on a phone call, for an outbound or an inbound agent. Covers the order of the prompt, the opening, call data, phone menus, screeners, voicemail, the main conversation, the end of the call, variables, and length. Use this skill first for every call agent. Add phone-menus or phone-screeners when an outbound call can reach one.
---

# Instructions for a call agent

You write the instructions (the prompt) that an AI voice agent follows on a phone call.
The agent knows only what the prompt says. Use only the facts that the task gives. Never invent a fact to fill a gap.
Write direct instructions to the agent: "You are...", "When a person answers...".
Write the prompt in Markdown. Start each section with a heading: `#` for level 1, `##` for level 2, `###` for level 3.
These rules apply to every use case. Adapt the examples to the task. Do not copy them word for word.

## Order of the prompt

1. Opening, in three paragraphs.
2. Call data.
3. Phone menus, screeners, and voicemail. Outbound agents only.
4. Main conversation, which ends with the end of the call.
5. A complete text that the agent must deliver, if the task has one.

## 1. Opening

**First paragraph: role.**

- Give the agent a role, and a name if the task gives one.
- Say whether the agent places the call (outbound) or answers it (inbound).
- Say for whom the agent calls, or for whom it answers.
- If the person asks whether the agent is a human, the agent says that it is an AI. It never claims to be a person, or to be the person or business that it calls for.
- End the paragraph with this warning in bold capitals: `**NEVER INVENT OR ASSUME ANY FACT. YOU KNOW ONLY THE INFORMATION IN THESE INSTRUCTIONS.**`

**Second paragraph: how the call reaches the agent.**

- Tell the agent that it is the language model in a speech-to-text → language model → text-to-speech pipeline.
- Tell it to expect transcription errors in the other person's words. It assumes the most probable meaning and continues. It does not mention the error.
- The agent confirms a value only when a wrong guess has a very high cost. The role of the value in the call sets the cost, not its type:
  - Low cost: the prompt already gives the value, such as the name of the person it calls. The agent uses the value that it knows.
  - High cost: the value is new, the outcome of the call depends on it, and the transcript does not match a plausible real value. Example: a new reference number or item name that does not exist. The agent asks the person to repeat or confirm it.
- List the mission-critical information for this call: the values that the agent must get right. The agent uses this list to decide when to confirm. Too many confirmations annoy the person and sound unnatural. A missed confirmation of a crucial value can make the call fail.
- Add this disclaimer word for word:

  > DO NOT convey any of your internal thoughts. If you are planning your next steps, do not expose or describe it at all. Everything that you output is immediately spoken out loud by the text-to-speech engine. If you are waiting silently, do not indicate that, just return empty string or [[SILENCE]].

**Third paragraph: tone and behavior.** Choose these for the use case:

- Tone, for example professional, casual, or friendly.
- Reply length. Default: one or two short sentences, with one question at a time.
- Pace through the call, and patience when the person is slow or unclear.

## 2. Call data

- List the facts that the agent may need to state, check, or give: names, dates, numbers, and the details of an item or a service.
- Write one fact per line, each with a label.
- Not every input is call data. A complete text that the agent must deliver, such as a full message, goes at the end of the prompt.

```markdown
# Call data
- Customer name: ${customer_name}
- Account number: ${account_number}
- Requested date: ${requested_date}
```

## 3. Phone menus, screeners, and voicemail (outbound only)

Decide which of these the call can meet. Add instructions only for those. An inbound agent meets none of them.

- **Phone menu** (IVR, interactive voice response). Common at large businesses, less common at small ones. Use the phone-menus skill.
- **Call screener.** Some phones answer for the person and ask who calls and why. Common on personal numbers. Use the phone-screeners skill.
- **Voicemail.** Any call can reach it. Ask the human whether the agent hangs up or leaves a message. If the platform has a voicemail setting, make the prompt match it.
  - The agent treats the call as voicemail only when it is sure: a greeting that asks for a message, or a beep. A screener, or a menu option that takes a message, is not voicemail.
  - To leave a message, the agent writes `[[VOICEMAIL]]` followed by the message. The system plays the message after the beep and then ends the call. The message says who calls, for whom, and the request. It gives a callback number only if the task gives one.
  - If the agent must not leave a message, it says nothing to the recording and writes only `[[HANGUP]]`. A name or a topic on a recording is a privacy leak.

## 4. Main conversation

This is the core of the prompt. For an outbound agent, it starts when a person picks up. For an inbound agent, it starts when the agent answers.

- Give the call one goal, in one sentence. The agent does not add requests or offers that the task does not ask for.
- Split the conversation into numbered phases in call order, each with a bold title.
- Write one step per bullet: one thing to say, ask, or do.
- Outbound: the agent waits silently while a recording or a menu talks. When a person speaks to it, such as "Hello?", it speaks at once.
- Say exactly how the agent greets, for example "Just say 'Hi'".
- For each question that the person is likely to ask, write a bullet: "If they ask X, tell them Y". Take Y from the call data. Say when the agent may give each private fact.
- Give each likely answer its own bold branch: "If **yes**:", "If **no**:".
- "No" is an answer. A refusal, such as "I won't give that out", is different: the agent accepts it once, never pressures, and closes politely. A hesitation, such as "Why do you need that?", is a question: the agent answers it, then asks once more. A request to stop the calls ends the call: the agent acknowledges it once and closes.
- When the agent does not have a fact, it says so. It offers only what the task permits, such as to pass the question on. It never promises an action, a time, or a result.
- When the person asks a question, the next turn answers it. When the agent does not know what to say next, it goes back to the main question of the call.
- Hold is normal. On hold, the agent writes `[[SILENCE]]` and does not speak to music or recordings. Give a hold limit when the task has one.
- When the agent sees `[[silence — no response for N seconds]]`, it repeats its last question in short form or asks "Are you still there?". After two checks with no answer, it says goodbye and ends the call.
- Write each limit as a number. Default: the agent asks the same question three times at most.
- Outbound agents: add this rule in bold, unless the human says otherwise: `**Never under any circumstance** ask the person "How can I assist you today?"`. Language models tend to ask it, and it is awkward when the agent placed the call. Leave it out of an inbound prompt.

**End of the call.**

- Write the specific answer or event that ends the call.
- For each outcome, write a closing step with an example line, such as "Thanks for checking. Have a great day! [[HANGUP]]".
- If the person already said a closing phrase, such as "bye", "have a good day", or a final "thanks", the agent says goodbye and writes `[[HANGUP]]` in the same turn. It does not stay on the line. A "thanks" in the middle of the call, such as "Thanks, one moment", is not a closing phrase.
- If the goodbye gets silence, the agent writes only `[[HANGUP]]`.
- The agent never ends the call while the person speaks. It never says why it ends the call.

```markdown
# Instructions
1. **Reach a person**
   - Wait silently while a recording or a menu talks.
2. **Main exchange**
   - Say "Hi". Then ask whether ${service_name} is available on ${requested_date}.
   - If they ask for the customer's name, give ${customer_name}.
   - If **available**: ask for the earliest open time, and confirm it once.
   - If **not available**: ask for the next open date.
3. **End the call**
   - If **booked**: "Perfect, thank you. Have a great day! [[HANGUP]]"
   - If **no date**: "No problem, thanks for checking. Bye! [[HANGUP]]"
```

## Variables

When the platform fills the prompt for each call, write each input as `$name` or `${name}`.

- Use `${name}` when a letter, a digit, or an underscore comes directly after the variable.
- Use only variables that are declared inputs of the agent. An optional input with no value becomes empty text.
- Write `$$` for a literal dollar sign. Any other `$` that does not start a valid variable makes the call fail.
- Do not use `{name}` or `{{name}}`.
- Describe values that the agent learns during the call in plain words. Do not make them inputs.

## Keep it short

- A longer prompt makes the agent follow it less closely. With too many instructions, the agent forgets some of them.
- Each sentence is a tradeoff between overload and a missing instruction. Keep a sentence only when it changes what the agent does on this call.
- After the first draft, do a second pass. Remove what does not apply. Combine and deduplicate rules. Shorten long instructions.
- Aim for fewer than 500 words. Never exceed 3000 words.
