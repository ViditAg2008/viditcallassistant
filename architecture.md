# Architecture

## Platform
Built on Samvaad by Sarvam AI, a voice-agent platform for production phone calls.

## Stack
- Text to speech: Bulbul voice model (natural Hindi/English speech)
- Speech to text: Saarika speech model
- Agent: single-state voice agent, all conversation behavior authored in one instructions block
- Reasoning: conversational LLM with turn-by-turn generation

## Agent design
- Persona: relaxed young man answering a friend's phone, informal register in every language
- Variables in: user_name, caller_relationship (family / friend / colleague / unknown)
- Variables out: call_summary, caller_request, urgency_level (urgent / callback_needed / casual)
- Call goal: caller feels they had a natural conversation, and a record of who called,
  what they wanted and how urgent it was is captured after every call

## Languages
- Starts in Hindi, switches automatically to the caller's language (English tested,
  11 Indian languages supported: Hindi, Bengali, Gujarati, Kannada, Malayalam, Marathi,
  Odia, Punjabi, Tamil, Telugu, English)

## Call handling
- Interruptions allowed, so the caller can talk over the agent like a real person
- Inactivity nudge after 5 seconds of silence ("Hey, you still there?")
- Voicemail detection with a personal message
- Quiet office background sound for realism
- Max call length 15 minutes

## Deployment
The agent is deployed as an inbound phone line: attach a phone number and it answers
every call to that number. Tested via a live playground call with a real transcript
(see README).
