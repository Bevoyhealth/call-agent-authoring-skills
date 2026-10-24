---
name: phone-menus
description: Write instructions that get an AI voice agent through an automated phone menu (IVR) to a person. Covers key menus, spoken menus, hold, loops, dead ends, and common patterns on the menus of large businesses. Use when the call goes to a business that can answer with a recorded menu.
---

# Getting through a phone menu

A phone menu is a recording that asks the caller to press a key or say a word.
The term IVR (interactive voice response) means the same thing.
Many business calls start with a phone menu, not a person.
The goal of the menu part of the call is one thing only: reach the correct person.

To press keys, the agent writes `[[DTMF:...]]` with the keys after the colon: `[[DTMF:1]]` presses 1, `[[DTMF:12#]]` presses 1, 2, and #. A `w` adds a pause between keys: `[[DTMF:1w2]]`. The listener never hears the marker. The agent presses keys only on a phone menu, never while it talks to a person.
To wait and listen, the agent writes only `[[SILENCE]]`.
Do not write a fixed key or menu path for one business. Menus change, and a stale path sends the agent to a dead end.

## Three kinds of menu

Tell the agent to find out which kind it hears.

1. Key menu. The recording reads numbered options: "For billing, press 1."
2. Spoken menu. The recording asks an open question: "How can I help you today?"
3. No menu. The line rings, plays hold music, or a person answers. The agent waits and presses nothing.

Some menus mix the two. A spoken menu can offer a key, and a key menu can accept words.

## How to choose an option

- Wait for the greeting and the notices to finish. Do not press a key or speak before the first real question.
- Listen until the recording finishes the sentence that offers the wanted option.
- Choose by meaning, not by position. Do not press 1 because it is first.
- Press only a key that the recording names. A guessed key often leads to a dead end.
- Use this order of preference:
  1. An option for the specific person or team that the task needs.
  2. An option for the caller role that the task gives.
  3. The correct department.
  4. An operator, a representative, or "all other questions".
- Skip self-service options unless they offer a person: hours, address, status, payments or orders by number, website, app, and surveys.
- Do not stay silent through a whole key menu. Some menus end the call when nobody chooses.

## On a spoken menu

- Let the recording finish. Do not interrupt it.
- Say only a short phrase, such as the department name or "speak with a person".
- Never say the opener, the reason for the call, or a private fact to a menu.
- If the menu tries to help itself, stay silent and let it finish. Then say the short phrase again.
- If the menu asks a yes or no question about the caller role, answer truthfully for the caller in the task.

## One choice, then wait

- Make each choice once: one key or one phrase, not both.
- After a choice, stay silent through "connecting you", hold music, and promotions.
- Do not press again during a transfer or hold. A second key press can drop the call or restart the menu.
- Choose again only in these cases:
  - The menu starts again from the top.
  - The menu says that the choice was not valid.
  - The menu says that it did not hear a choice.
- If the menu asks "Are you still there?", answer once.

## Loops and dead ends

- Do not repeat the same failed input more than once.
- After a failed input, try a different option that leads to a person.
- If a phrase fails, press the named key for the same option. If a key fails, say the phrase.
- If the menu asks for an account or record number that the task does not give, do not guess one. Choose the option for a person, or wait. Many menus send the caller to a person after no input.
- A menu option that offers to take a message is not a person. Choose an option for a person while one remains.
- If you reach a message branch, use the named key to go back, or ask for an operator.
- "Check our website" or "feel free to hang up" is a recorded notice, not voicemail. Keep going.
- Give up when only message options remain, or after about two loops with no progress. Then follow the voicemail choice of the task.

## Hold after the menu

- A long hold is normal. The agent stays on the line and stays silent.
- Messages such as "all staff are busy" mean the agent is in a queue. Keep waiting.
- Do not hang up while the menu says it is connecting you to a person.

## When a person answers

- Stop pressing keys at once. Never press a key over a live person.
- A person usually says the business or department name, then asks how to help.
- Begin the opener now, once.
- If the wrong department answers, ask that person to transfer the call to the correct department.
- If the agent is not sure that a person answers, it asks a short question, such as "Hi, is this the front desk?"

## Common patterns on large-business menus

These patterns are common on the menus of large businesses, such as stores, banks, utilities, and clinics. They are general patterns, not facts about one business.

- The main menu often lists departments first. Choose the department that the task needs.
- The department menu often asks about the caller role, for example "Are you a customer or a business partner?". Answer only with the role that is true for the caller in the task.
- A route for business callers often leads to a message box, an order line, or a return-call line. Choose an option to speak with staff over these.
- A spoken menu often accepts the department name first. If it asks again, say "speak with staff" or "representative".
- Expect long promotions about offers, apps, and websites. Stay silent through them.
- If the menu says the department is closed or on a break, end the call. Follow the voicemail choice of the task.
- Give no private details to the menu. Give them only to staff of the correct department, and only when the task permits.
- Ask the task question only after a person from the correct department speaks.
