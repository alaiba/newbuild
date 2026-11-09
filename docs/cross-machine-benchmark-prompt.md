# Local LLM benchmark prompt

I want to compare local LLM inference on this computer with another machine. Run the following benchmark and report the results. Ask before downloading a model that is not already installed.

1. Identify the operating system, processor, GPU, installed and available system memory, and GPU memory where applicable. Report the Ollama version and exact model ID/digest and quantization.
2. Use Ollama and the local model `qwen3:8b`. If it is missing, report its approximate download size and ask before downloading it. Do not use a cloud model. Record whether the model is running on the CPU, GPU, or both, using `ollama ps` while it is loaded.
3. Use the same prompt for every run: `Write a detailed explanation of how rainbows form, using at least 800 words.` Set context to 4096 tokens, temperature to 0, seed to 42, and the output limit to 1024 tokens. Keep thinking behavior consistent with the model default and report it if known. Use the Ollama API with `stream: false` and `keep_alive: "10m"`.
4. Run one warm-up followed by three measured runs, sequentially. Calculate generation tokens per second as `eval_count / (eval_duration / 1e9)`. Also report prompt token count, prompt processing time and rate when available, generated token count, generation time, total elapsed time, load time, and finish reason for each measured run. If prompt tokens are cached, report that and don't treat the warm cached rate as a cold prompt processing measurement. Record model placement, context, and memory use when observable. Capture any errors rather than reporting zeros.
5. Present a table of the three runs and the average and median generation rate. List the full settings, model ID, Ollama version, and whether GPU offloading was confirmed. Clearly state that a short input does not test long-context performance. Don't claim the machines have been compared until results from both are available.

Avoid running other heavy tasks at the same time. Use the same Ollama version and model digest on both machines if possible; if they differ, identify that limitation. Do not change persistent system settings.
