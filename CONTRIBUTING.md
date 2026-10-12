# Contributing

This is a one-file demo built in an evening, so the bar is low: if something breaks or the bouncer says something daft, open an issue and say what you said and what came back.

## Where things live

Everything is in `bouncer.html`: the page, the microphone capture and the connection to AssemblyAI's Voice Agent API.

## Running it

```bash
python3 -m http.server 3000
```

Then open `http://localhost:3000/bouncer.html` and paste your own AssemblyAI key. Never commit a key.
