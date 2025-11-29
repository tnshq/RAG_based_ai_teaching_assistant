
# RAG-based AI Teaching Assistant

This project is an AI-powered teaching assistant that leverages Retrieval-Augmented Generation (RAG) to answer user questions about a web development course. It processes video/audio content, generates embeddings, and uses a local LLM to provide context-aware answers, including references to specific videos and timestamps.

## Features
- Converts video files to audio (mp3)
- Transcribes audio and generates JSON subtitle chunks
- Creates and stores embeddings for each chunk
- Accepts user questions and finds the most relevant content
- Uses a local LLM (via Ollama API) to generate human-like answers
- Guides users to the exact video and timestamp for their query

## Project Structure
```
mp3_to_json.py           # Converts mp3 audio to JSON subtitle chunks
preprocess_json.py       # Preprocesses JSONs and creates embeddings
process_incoming.py      # Main script for user Q&A
video_to_mp3.py          # Converts video files to mp3 audio
audios/                  # Directory for audio files
jsons/                   # Directory for JSON subtitle files
videos/                  # Directory for video files
```

## Requirements
- Python 3.8+
- Anaconda (recommended)
- Required Python packages: see code for `requests`, `pandas`, `numpy`, `scikit-learn`, `joblib`
- Ollama (for local LLM and embedding API)

## Setup
1. Clone this repository.
2. Create and activate a conda environment:
	```sh
	conda create -n rag python=3.9
	conda activate rag
	```
3. Install required packages:
	```sh
	pip install requests pandas numpy scikit-learn joblib
	```
4. Install and run Ollama (see https://ollama.com/ for instructions).
5. Place your video files in the `videos/` directory.

## Usage
1. Convert videos to mp3:
	```sh
	python video_to_mp3.py
	```
2. Convert mp3 to JSON subtitle chunks:
	```sh
	python mp3_to_json.py
	```
3. Preprocess JSONs and create embeddings:
	```sh
	python preprocess_json.py
	```
4. Start the Q&A assistant:
	```sh
	python process_incoming.py
	```
5. Enter your question when prompted. The assistant will answer and guide you to the relevant video and timestamp.

## Notes
- `.gitignore` is set up to exclude large media files and macOS metadata.
- Make sure Ollama is running and the required models are available.

## License
MIT License


