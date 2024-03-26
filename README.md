# Learning [Ollama](https://ollama.com)

Just one of the things I'm learning. https://github.com/hchiam/learning

Ollama makes it easy to run LLMs offline/locally/privately on your computer.

## Setup

1. ollama.com website download app to install ollama command
2. `ollama run llama2` automatically downloads llama2 model if needed, and lets you talk with the model offline directly in the terminal, with the ollama app running in the background
    - (otherwise to just use another terminal window to run ollama in the background: `ollama serve`)

## Extra notes

- in .bash_profile: `alias llm='ollama run llama2'`
- to read a local file: `ollama run llama2 "Summarize this file: $(cat scratchpad.md)"`
- or with the custom alias: `llm "Summarize this file: $(cat scratchpad.md)"`
- or run ollama with python code: https://github.com/hchiam/local-llms-analyse-finance/blob/main/categorize_expenses.ipynb
- but overall, it seems:
  - running llama2 on ollama has limited speed (unless your computer has GPUs that can Ollama can use for GPU acceleration)
  - running llama2 on ollama has limited prompt/input size, which would require chopping up the input

## Further resources

- https://youtu.be/WxYC9-hBM_g?feature=shared (around 18:08)
  - (aside: consider privategpt too:)
    - https://dev.to/docteurrs/installing-privategpt-on-wsl-with-gpu-support-1m2a
    - and https://docs.privategpt.dev/overview/welcome/introduction
- https://www.youtube.com/watch?v=h_GTxRFYETY
- https://ollama.com
- to customize with a Modelfile (temperature and system message/prompt): https://github.com/ollama/ollama?tab=readme-ov-file#customize-a-prompt
