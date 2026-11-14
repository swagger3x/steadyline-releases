# Steadyline releases

Downloads for Steadyline, a Windows call assistant that captions calls on the PC. The app fetches
these files itself when it needs them; there's nothing here to install by hand.

## GPU speech models

Steadyline runs speech recognition on an NVIDIA GPU with these models. Each model is one release,
named after its folder:

| Release | Chunk size | Files |
|---|---|---|
| `sherpa-onnx-nemotron-speech-streaming-en-0.6b-80ms-fp16-2026-11-14` | 80 ms | encoder (fp16), decoder, joiner, tokens |
| `sherpa-onnx-nemotron-speech-streaming-en-0.6b-160ms-fp16-2026-11-14` | 160 ms | encoder (fp16), decoder, joiner, tokens |

They are a derivative of NVIDIA's
[nemotron-speech-streaming-en-0.6b](https://huggingface.co/nvidia/nemotron-speech-streaming-en-0.6b),
exported to ONNX with a fixed chunk size and the encoder converted to 16-bit floating point. The
app checks every file against its SHA-256 before using it.

## License

Licensed by NVIDIA Corporation under the NVIDIA Open Model License. See [Notice.txt](Notice.txt)
and the agreement in [NVIDIA-Open-Model-License.pdf](NVIDIA-Open-Model-License.pdf); each release
carries both files too.
