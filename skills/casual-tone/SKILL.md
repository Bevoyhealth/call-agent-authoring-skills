---
name: casual-tone
description: Write short, conversational instructions for an AI voice agent with a casual tone. Covers spoken sentences, contractions, plain words, and optional vocal tics. Use only when the task asks for a casual tone. Leave it out for a professional or formal tone.
---

# Casual tone

Use this skill when the task asks for a casual, conversational agent.
Do not use it for a professional or formal tone.
A friendly tone alone does not mean casual.

## Start with short speech

Teach the agent to speak as a person speaks in a conversation.
Casual tone starts with the words and sentences, before any vocal tic.

- Use short, spoken sentences with one idea per sentence.
- Use contractions, such as "that's", "I'll", and "don't".
- Use plain words, such as "yes", "sure", and "thanks".
- Answer the person's question directly before the next question.
- Ask one question at a time.
- Give the person time to answer.
- Do not read a list aloud. Give the next useful point when the person needs it.
- Do not turn each reply into a speech, a summary, or a formal written answer.
- Keep the facts and the task clear. Casual words do not permit a guess or an unsupported promise.

For example, replace "That is correct" with "That's right".
Replace "I will now proceed to check that information" with "I'll check that".

## Add vocal tics as words

A vocal tic is a short spoken word that expresses a pause, agreement, or a reaction.
It is an addition to short speech, not a substitute for it.
Write the tic as ordinary text that the voice says aloud.
Do not write a stage direction such as "[hesitates]" to request "umm".

Examples of plain-word tics:

- "umm" or "ummm" for a brief hesitation.
- "hmm" for thought or uncertainty.
- "uhuh" for agreement or acknowledgment.
- "oh", "huh", or "ah" for a reaction.
- "okay so" before the next point.

For example, "uhuh, that's right" sounds more casual than "that is correct".
Another example is "ummm, I've never heard that one before."
Use a tic when it fits the answer.
Do not force a tic into every reply or repeat the same tic throughout the call.
Do not add a tic to fixed text that the agent must say word for word.

## Combine a cue and a tic only when supported

An emotion cue tells a voice how to say the words that follow it.
Use a cue only when the selected voice and the service that runs the call support it.
Follow that service's cue syntax.
For a voice that accepts single-bracket cues, an example is "[surprised] huh, that's unexpected".
The cue expresses surprise; "huh" is the spoken tic.
Some services require a different cue syntax before they send the text to the voice.
For a voice or service without cue support, leave the cue out: "huh, that's unexpected".
Do not treat a plain-word tic as a cue.

## For a professional or formal tone

Leave out the casual speech rules, vocal tics, and casual reaction examples from this skill.
Use the tone that the task requests.
