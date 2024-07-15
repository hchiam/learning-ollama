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

## Example uses
- [use ollama to set up privateGPT](https://github.com/hchiam/learning-privateGPT)
- [use ollama to set up Gemma2 to run with local RAG using LangChain](https://www.youtube.com/watch?v=daZOrbMs61I) with [samwit's code to run](https://github.com/samwit/langchain-tutorials/tree/main/2024/gemma2_local_rag) (or [my fork of that repo](https://github.com/hchiam/langchain-tutorials-samwit/tree/main/2024/gemma2_local_rag)):
    - ```sh
      pip install langchain
      # langchain_community might need to installed with pip3 install langchain-community langchain-core
      ```
    - ```sh
      ollama run gemma2 # 5.4 GB when i tried
      ollama pull nomic-embed-text # 274 MB
      ollama list
      ```
    - ```sh
      python indexer.py
      ```
    - ```sh
      python ollama_gemma2_rag_debugging.py
      ```
      or
      ```sh
      python ollama_gemma2_rag_simple.py
      ```
