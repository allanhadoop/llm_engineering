# llm_engineering

#Good Reference - Ed-Donner - https://github.com/ed-donner/llm_engineering

1. GPT
2. CLAUDE - Haiku, Sonnet and Opus
3. GEMINI
4. GROK

Frontier open source models- 
1. LLAMA
2. MIXTRAL
3. QWEN
4. GEMMA
5. PHI
6. DEEPSEEK
7. GPT-OSS from OpenAI



Foundation - ollama.com, various models available 
•	Download oollama.com and install on windows then run command like
o	Ollama, 
o	Ollama serve 
o	Ollama run gema3:270m     (We will run small version of Gemini with 2.7 million tokens) 

-- Install uv using winget under windows option -- https://docs.astral.sh/uv/getting-started/installation/#homebrew 
Commands - 
uv --version 
uv self update 
uv sync 

--Install Extensions - Python and Jupyter from microsoft 
--Get OpenAI API key and add a new file .env and update there 
-- Below is API code to get the response from OpenAI model - 
message = "Hello, GPT! This is my first ever message to you! Hi!"
messages = [{"role": "user", "content": message}]
openai = OpenAI()
response = openai.chat.completions.create(model="gpt-5-nano", messages=messages)
response.choices[0].message.content
data = fetch_website_contents("https://edwarddonner.com")
print(data)

---Prompts - 
System prompt - Tell tasks that model should perform
User prompt - conversation starter
messages = [
    {"role": "system", "content": "You are a helpful assistant"},
    {"role": "user", "content": "What is 2 + 2?"}
]
-----------------API Endpoint --------
import requests

headers = {"Authorization": f"Bearer {api_key}", "Content-Type": "application/json"}
payload = {
    "model": "gpt-5-nano",
    "messages": [
        {"role": "user", "content": "Tell me a fun fact"}]
}

response = requests.post(
    "https://api.openai.com/v1/chat/completions",
    headers=headers,
    json=payload
)
response.json()

---> We can package above endpoint using OpenAI - Python Clint Library -- For example from openai import OpenAI 
response = openai.chat.completion.create() 
response.choices[0].message.content


