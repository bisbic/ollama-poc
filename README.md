# POC using ollama, chatbot-ollama and different models

## Starting the ollama server and chatbot-ollama
```bash
sudo docker compose up -d
```

## Pulling fundational models
[Search models here](https://ollama.com/library)
```bash
# Get a shell into ollama container
docker exec -it ollama-poc-ollama-1 bash
# List models
ollama list
# Pull or update models
ollama pull llama3.1:8b
ollama pull codellama:7b
```

## Running chatbot-ollama in browser
[localhost:3000](http://localhost:3000)

## Query ollama server
```bash
curl http://localhost:11434/api/generate -d '{
"model": "llama3.1:8b",
"prompt":"Which programming languajes do you know?",
"stream": false
}'
```

## Using codex cli with ollama models

1. (Install codex cli from here)[https://github.com/openai/codex-cli]
2. Set configuration file `~/.codex/config.json` to:
```json
{
  "model": "qwen2.5-coder:7b",
  "provider": "ollama",
  "providers": {
    "ollama": {
      "name": "Ollama",
      "baseURL": "http://localhost:11434/v1",
      "envKey": "OLLAMA_API_KEY"
    }
  },
  "history": {
    "maxSize": 1000,
    "saveHistory": true,
    "sensitivePatterns": []
  }
}
```
3. Run codex cli
```bash
codex --model qwen2.5-coder:7b --provider ollama
```
