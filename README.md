<h2>Ollama examples</h2>

#### 0. LM Studio
[LM Studio](https://lmstudio.ai/) is a tool that you can use to experiment with local and open-source LLMs. It's standalone UI application where you can run these LLMs on your laptop, entirely off.
<br><br>


#### 1. Ollama + Open WebUI
[*Ollama*](https://github.com/ollama/ollama) - get up and running with large language models locally.

[*Open WebUI*](https://github.com/open-webui/open-webui) - ChatGPT-Style Web Interface for Ollama with a lot of features.

<h5>Setup:</h5>

  - run *Ollama + WebUI* by using `ollama/start.bat`
    >Docker containers can have access to the GPU. If you have it then use `start.gpu.bat`

  - open http://localhost:11434/ to make sure *Ollama* is available.

  - open http://localhost:3000/ and make sure *Open WebUI* is available

  - configure account & models to be used (try *tinyllama* model as an example)
    > use https://ollama.ai/library for models search

  - stop *Ollama + WebUId* by using `ollama/stop.bat`

#### 2. Ollama API
*Ollama* has an [Ollama API](https://github.com/ollama/ollama/blob/main/docs/api.md) so custom solutions can be implemented.

*Ollama API* wrappings:
- [*OllamaSharp*](https://github.com/awaescher/OllamaSharp) is an Ollama API bindings for .NET and has [Ollama API console](https://github.com/awaescher/OllamaSharp?tab=readme-ov-file#api-console) implementation

#### 3. How can I specify the context window size?

By default, Ollama uses a context window size of 2048 tokens.

- To change this when using `ollama run`, use `/set parameter`:

```
/set parameter num_ctx 4096
```

- When using the API, specify the `num_ctx` parameter:

```
curl http://localhost:11434/api/generate -d '{
  "model": "llama2",
  "prompt": "Why is the sky blue?",
  "options": {
    "num_ctx": 4096
  }
}'
```

#### 4. Ollama FAQ
[Ollama FAQ](https://github.com/ollama/ollama/blob/main/docs/faq.md) - 
  helpful guide regarding Ollama configuration.
