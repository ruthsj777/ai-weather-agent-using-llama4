🌦️ AI Weather Agent (Hugging Face + Llama-4-Scout)

This project demonstrates how to build a simple AI Agent using
Meta Llama-4-Scout-17B-16E-Instruct via Hugging Face’s InferenceClient.

It follows the classic agent loop:

Thought → Action (JSON) → Observation → Final Answer


The model decides an action, your Python code executes it, and the model uses the result to answer the question.

Features

Uses Hugging Face Inference API

Runs Llama-4-Scout for agent reasoning

Custom system prompt controlling agent behaviour

JSON tool-calling structure

Uses stop=["Observation:"] to avoid hallucinated outputs

Executes a real Python tool: get_weather()

Demonstrates how AI agents decide, act, and use tools


Agent Workflow Explained

User asks a question
Example: “What’s the weather in London?”

Model thinks
Generates “Thought:” describing what action to take.

Model outputs action JSON
Example:

{
  "action": "get_weather",
  "action_input": {"location": "London"}
}


Your Python code executes the tool
Runs get_weather("London").

Insert the tool result as "Observation:"
The agent receives the real data.

Model produces final answer
Using the observation, it completes the reasoning loop.

 Technologies Used

Python

Hugging Face huggingface_hub

Meta Llama-4-Scout

JSON tool-calling

Agent-style prompt engineering

📂 Project Structure
📁 ai-weather-agent
 ├── agent_weather_demo.ipynb     # Main notebook with the full code
 ├── README.md                    # Project documentation
 └── requirements.txt (optional)  # Package list


 Requirements

Install Hugging Face Hub:

pip install huggingface_hub


You also need a Hugging Face Read Token:

Create one here: https://hf.co/settings/tokens

Name it HF_TOKEN

Add to environment variables or Colab secrets

You must also request access to:

meta-llama/Llama-4-Scout-17B-16E-Instruct

Approval usually takes under 1 hour.

▶ How to Run

Clone this repo

Install requirements

Set your HF_TOKEN

Open the notebook

Run all cells

The agent will answer weather questions like:

“Weather in London?”

“Weather in Mumbai?”

“Weather in New York?”

You can modify the input to check any location.

Learning Purpose

This project is a simple, educational example of:

How an AI agent works behind the scenes

How tool-calling is implemented

How to prevent hallucinations

How model reasoning steps are controlled

How to integrate Python functions with an LLM

Perfect for beginners learning AI agents.

Future Improvements

Add real weather API instead of dummy function

Add multiple tools (calculator, search, news)

Create a general multi-tool AI agent

Add a UI (Streamlit)

Author

Created as part of learning AI Agents and Hugging Face model integration.
