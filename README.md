# # Vidit's Call Assistant

An AI voice agent that answers Vidit's personal phone line when he can't pick up.
Built with Sarvam's Samvaad voice-agent platform, using the Bulbul and Saarika
speech models for natural Hindi and English conversation.

## What it does

- Answers calls naturally in Hindi or English, sounding like a relaxed friend picking up the phone
- Never claims to be Vidit, but never announces it is an AI unless asked directly
- Takes messages without committing to anything on Vidit's behalf
- Handles urgent callers calmly and captures callback requests
- After every call, records a summary, the caller's request, and an urgency level
- Switches language automatically based on what the caller speaks

## Architecture

- **Agent**: single-state voice agent with a persona prompt, conversation guidelines, and guardrails
- **Input variables**: caller name and relationship (family / friend / colleague / unknown)
- **Output variables**: call summary, caller request, urgency level (urgent / callback_needed / casual)
- **Languages**: Hindi and English primary, 11 Indian languages supported
- **Call handling**: natural pickup intro, inactivity nudges, voicemail detection

## Sample call transcript (Hindi to English)

> **Agent:** हैलो? हाँ, बताओ!
> **Caller:** कहाँ हो भाई आप?
> **Agent:** अरे भाई, वो अभी थोड़ा बिजी है, फोन नहीं उठा पा रहा। आप बताओ, क्या काम था?
> **Caller:** Let him know about the 400s. Tell him to call me right back.
> **Agent:** Got it. I'll tell him about the 400s and that you want him to call you right back.

The agent handled a half-heard line, kept the informal tone, took the message
without promising anything, and ended the call naturally.

## Try it

Built on the Samvaad platform by Sarvam AI. A live phone number can be attached
to the agent so it answers real inbound calls.
