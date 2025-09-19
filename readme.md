# Docker Model Runner, Docker MCP Toolkit, and Promptfoo

This repo contains a few examples of how to use Docker Model Runner, Docker MCP Toolkit, and Promptfoo together to 
compare models, evaluate MCP servers, and even perform LLM red-teaming from the comfort of your own dev machine.


## Prerequisites

1. Enable Docker MCP Toolkit in Docker Desktop per https://docs.docker.com/ai/mcp-catalog-and-toolkit/get-started/#enable-docker-mcp-toolkit.
2. Enable Docker Model Runner in Docker Desktop or Docker Engine per https://docs.docker.com/ai/model-runner/#enable-docker-model-runner.
3. Use the Docker Model Runner CLI to pull the following models
```bash
docker model pull ai/gemma3:4B-Q4_K_M
docker model pull ai/smollm3:Q4_K_M
docker model pull ai/mxbai-embed-large:335M-F16
```
4. Install Promptfoo

```bash
npm install -g promptfoo
```

## Run the model comparison evaluation

```bash
export ANTHROPIC_API_KEY=<your_api_key_here>
promptfoo eval -c promptfooconfig.comparison.yaml
promptoo view
```

## Run the MCP Direct example

```bash
promptfoo eval -c promptfooconfig.mcp-direct.yaml
```

## Run the MCP Red-Team Example

```bash
export ANTHROPIC_API_KEY=<your_api_key_here>
promptfoo redteam run -c promptfooconfig.mcp-repo-summarizer.yaml
```