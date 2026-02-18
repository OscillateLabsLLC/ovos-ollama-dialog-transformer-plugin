# ovos-ollama-dialog-transformer-plugin

[![Status: Proof of Concept](https://img.shields.io/badge/status-proof%20of%20concept-orange)](https://github.com/OscillateLabsLLC/.github/blob/main/SUPPORT_STATUS.md)

Dialog transformer for OVOS, designed to return responses from [Ollama](https://ollama.com). By default it will make all your OVOS responses sarcastic.

The default model to use is `llama3.2`, which is a 3B parameter model and has a difficult time following instructions. You will probably need to adjust your prompt for best results. `phi4` has yielded good results in testing.

## Configuration

To enable the Ollama Dialog Transformer Plugin, add the following to your `mycroft.conf` (typically found at `~/.config/mycroft/mycroft.conf`):

```json
"dialog_transformers": {
    "ovos-ollama-dialog-transformer-plugin": {
        "prompt": "Please revise this text in 30 words or less as if it were spoken by a sarcastic AI. You are not an AI, you are revising text as if you were an AI. Don't mention anything about rewriting text, or your training, and don't use emoji. The dialog to rewrite is as follows:",
        "model": "llama3.2",
        "timeout": 10,
        "stream": false,
        "ollama_base_url": "http://localhost:11434"
    }
}
```

Note that these are all default values, so a minimal configuration would be:

```json
"dialog_transformers": {
    "ovos-ollama-dialog-transformer-plugin": {}
}
```
