# POC using ollama, chatbot-ollama and different models

## Sample request

```
curl http://localhost:11434/api/generate -d '{
"model": "codellama",
"prompt":"Which programming languajes do you know?",
"stream": false
}'
```
