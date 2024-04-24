# POC using ollama, chatbot-ollama and different models

## Starting the ollama server and chatbot-ollama
```bash
docker-compose up -d
```

## Pulling fundational models
```bash
# Get a shell into ollama container
docker exec -it ollama-poc-ollama-1 bash
# List models
ollama list
# Pull or update models
ollama pull llama3
```

## Running chatbot-ollama in browser
[localhost:3000](http://localhost:3000)

## Query ollama server
```bash
curl http://localhost:11434/api/generate -d '{
"model": "codellama",
"prompt":"Which programming languajes do you know?",
"stream": false
}'
```
