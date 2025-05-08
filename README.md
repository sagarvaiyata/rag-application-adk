# RAG Travel Advisor Agent

A simple Retrieval-Augmented Generation (RAG) application built on Google’s Agents Developer Kit (ADK) framework.

## Prerequisites
- Python 3.8+
- Google Cloud SDK authenticated to your project
- Vertex AI & Places API enabled in your Google Cloud project

## Setup

1. **Clone the repository**  
   ```bash
   git clone https://github.com/sagarvaiyata/rag-application-adk.git
   cd rag-application-adk
   ```

2. **Install dependencies**  
   ```bash
   pip install -r requirements.txt
   ```

3. **Create a `.env` file**  
   Use the following as a template. Leave `RAG_CORPUS` blank initially; the application will populate it on first run.

   ```bash
   cat > .env <<EOF
   # Choose Model Backend: 0 -> ML Dev, 1 -> Vertex AI
   GOOGLE_GENAI_USE_VERTEXAI=1

   # ML Dev backend config (ignored if using Vertex AI)
   GOOGLE_API_KEY=YOUR_GOOGLE_API_KEY

   # Vertex AI backend config
   GOOGLE_CLOUD_PROJECT=ai-agents-459105
   GOOGLE_CLOUD_LOCATION=us-central1

   # RAG corpus resource (populated at runtime)
   RAG_CORPUS=
   EOF
   ```

4. **Initialize the corpus (first run)**  
   ```bash
   python prepare_corpus_and_data.py --init-corpus
   ```
   This will download your documents, upload them to GCS, create the RAG corpus, and update `RAG_CORPUS` in your `.env`.

## Usage

Start the agent with a scenario:
Open the Parent Directory of your Agent's Directory Location and Run:
```bash
adk web 
```
