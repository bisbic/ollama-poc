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
