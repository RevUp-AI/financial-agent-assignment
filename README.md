# Financial Analyst Agent - Technical Assignment

The goal of this assignment is to build a proof-of-concept AI agent that can assist a financial analyst. You will create an agent using **LangGraph** that can answer questions by orchestrating two primary tools: a RAG pipeline for document analysis and a real-time API for fetching stock data.

## The Scenario
An analyst is conducting research on **NVIDIA (Ticker: NVDA)**. They need an AI assistant that can answer questions about the company's performance, strategy, and risks by reading its latest annual report, as well as provide the most up-to-date stock price.

## Provided Materials
*    Click [here](https://s201.q4cdn.com/141608511/files/doc_financials/2024/ar/NVIDIA-2024-Annual-Report.pdf) to download the **NVIDIA 2024 Annual Report** directly from NVIDIA's official website.
*   *You will need to acquire your own free API keys for the LLM provider (e.g., OpenAI, Anthropic, Google) and a financial data provider.*

## Technical Requirements

Your application's core must be an agent built with **LangGraph**. It should be able to receive a user's question and orchestrate a set of tools to generate a comprehensive answer.

1.  **LangGraph Agent Architecture:**
    *   Design and implement a graph-based workflow using LangGraph that can intelligently call one or more tools based on the user's query.
    *   The graph should be able to handle sequences of tool calls and synthesize the information into a final, coherent response.

2.  **Tool 1: Annual Report Q&A (RAG System):**
    *   This tool must be able to answer questions based on the content of the `NVIDIA 2024 Annual Report`.
    *   You will need to implement a robust RAG pipeline:
        *   **Load and Parse:** Effectively load and parse the complex, multi-section PDF document.
        *   **Chunking:** Implement an intelligent chunking strategy suitable for a large, structured document.
        *   **Vector Store:** Create embeddings and store them in a local vector store (e.g., Supabase, ChromaDB).
        *   **Retriever:** Build a retriever that the agent can invoke to find relevant information within the document.

3.  **Tool 2: Real-time Stock Price:**
    *   Implement a tool that can fetch the current/historical stock price for a given ticker symbol (e.g., "NVDA").
    *   Use any free, public API for this.

4.  **Orchestration and Synthesis:**
    *   Your LangGraph agent must correctly handle various queries by invoking the appropriate tools:
        *   **RAG-only query:** e.g., "What are the main risk factors mentioned in the 10-K?"
        *   **API-only query:** e.g., "What is the current stock price for NVDA?"
        *   **Hybrid query:** e.g., "Summarize the key points from the Data Center business segment and tell me their current stock price." For this, the agent must use **both** tools and combine the information into a single answer.

5.  **Voice-Enabled Interface (Not Mandatory):**
    *   To create an exceptional submission, demonstrate how this agent could work with voice. This is not mandatory, but highly encouraged.
    *   **Voice Input:** Allow the application to accept an audio file (e.g., `.wav`, `.mp3`) as input. Use a Speech-to-Text service (e.g., OpenAI's Whisper API) to transcribe the user's spoken query.
    *   **Voice Output:** Take the agent's final text response and use a Text-to-Speech service (e.g., ElevenLabs, OpenAI's TTS API) to convert it into a playable audio file (e.g., `response.mp3`).

## Submission Guidelines

Please provide a link to a public GitHub repository with your solution. The repository **MUST** include:

1.  **All source code.**
2.  A `requirements.txt` file.
3.  A detailed **`README.md`** file that includes:
    *   A high-level explanation of your **design and architectural choices**.
    *   Clear, step-by-step instructions on how to set up the environment and run your application.
    *   A few example queries you tested and their expected outputs.

## Evaluation Criteria
We will evaluate your submission on the following:

*   **Correctness & Functionality:** Does the agent work and fulfill all core requirements?
*   **Code Quality:** Is the code clean, well-structured, and maintainable?
*   **Design & Architecture:** How effectively did you use LangGraph? How did you handle the complex PDF and the hybrid queries?
*   **Handling of Complex Data:** Your approach to parsing, chunking, and retrieving information from the large annual report.
