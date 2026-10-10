# Berghain Bouncer 🎙️

A voice AI doorman for Berlin's most exclusive techno club. Plead your case
out loud — it interrogates you in English and German, cuts you off
mid-sentence, and stamps a live **JA / NEIN** verdict across the screen.
Almost everyone gets rejected.

Built in under an hour at the AssemblyAI London Voice AI Meetup (June 2026).

## How it works

One WebSocket to AssemblyAI's **Voice Agent API** handles everything:
speech-to-text, LLM, text-to-speech, turn detection and tool calling.
The browser client is a single vanilla HTML/JS file — AudioWorklet mic
capture at 24 kHz PCM16 in, streamed TTS audio out.

The verdict is a **tool call** (`decide_entry`) fired by the agent and
rendered as the on-screen stamp + running door tally, so the agent doesn't
just talk — it acts.

## Run it

1. Get an API key at [assemblyai.com](https://www.assemblyai.com/dashboard/api-keys)
2. Clone the repo and serve it locally:
   `git clone https://github.com/PKusch/berghain-bouncer && cd berghain-bouncer && python3 -m http.server 3000`
3. Open `http://localhost:3000/bouncer.html`, paste your key, **JOIN QUEUE**,
   allow the mic, and start pleading.

⚠️ The key is entered client-side for demo simplicity. In production you'd
mint short-lived tokens server-side and never expose the key in the browser.

## Credits

Built with AssemblyAI Voice Agent API + Claude as pair programmer.
Voice: `lukas` (German/English). Persona: the door decides.
