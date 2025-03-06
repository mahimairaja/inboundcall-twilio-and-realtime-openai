# Twilio + OpenAI Realtime Voice Assistant

A real-time voice assistant that uses Twilio for handling inbound calls and OpenAI's Realtime API for natural conversation. The assistant can understand speech, respond naturally, and even tells jokes!

## Features

- Real-time voice conversations using Twilio Media Streams
- Natural language processing with OpenAI's Realtime API
- Interruption handling for more natural conversations
- Automatic speech detection and turn-taking
- Fun personality with jokes and facts

## Requirements

- Python 3.8+
- Twilio Account
- OpenAI API Key
- ngrok or similar for exposing local server

## Environment Setup

1. Clone the repository
2. Create a `.env` file with:
```
OPENAI_API_KEY=your_openai_api_key
PORT=5050  # or your preferred port
```

## Installation

```bash
pip install -r requirements.txt
```

## Running the Application

1. Start the server:
```bash
python main.py
```

2. Expose your local server using ngrok:
```bash
ngrok http 5050
```

3. Configure your Twilio number:
   - Go to Twilio Console
   - Set the voice webhook URL to your ngrok URL + `/incoming-call`
   - Method: POST

## How It Works

1. When someone calls your Twilio number, the call is connected to the server
2. Audio is streamed in real-time to OpenAI's API
3. The AI processes the speech and generates responses
4. Responses are streamed back to the caller
5. The conversation continues naturally with support for interruptions

## Project Structure

- `main.py`: Main application code
- `requirements.txt`: Project dependencies
- `.env`: Environment variables (not in repo)

## Troubleshooting

- Make sure your OpenAI API key is valid and has access to the Realtime API
- Verify your Twilio webhook URL is correctly set
- Check the server logs for detailed error messages

## License

MIT License
