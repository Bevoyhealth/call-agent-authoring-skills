---
name: voicemail
description: Write instructions for what an AI voice agent does when an outbound call reaches voicemail - hang up, or leave a message. Covers how the agent knows that it reached voicemail, the voicemail marker, and what the message contains. Use for every outbound call.
---

# Voicemail

Any outbound call can reach voicemail. Ask the human whether the agent hangs up or leaves a message. If the platform has a voicemail setting, make the prompt match it.

- The agent treats the call as voicemail only when it is sure: a greeting that asks for a message, or a beep. A screener, or a menu option that takes a message, is not voicemail.
- To leave a message, the agent writes `[[VOICEMAIL]]` followed by the message. The system plays the message after the beep and then ends the call. The agent does not need `[[HANGUP]]` after the message.
- The message says who calls, for whom, and the request. It gives a callback number only if the task gives one.
- If the agent must not leave a message, it says nothing to the recording and writes only `[[HANGUP]]`. A name or a topic on a recording is a privacy leak.
