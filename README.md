# Steadyline releases

Downloads for Steadyline, a Windows call assistant that captions calls on the PC.

## Install

Download `Steadyline-win-Setup.exe` from the [latest release](../../releases/latest) and run it.
It installs for your Windows account and needs no administrator rights.

- The installer isn't code-signed yet, so Windows may show "Windows protected your PC" the first
  time: choose **More info**, then **Run anyway**.
- Steadyline needs a license key for your PC. The first start shows your PC's machine code, which
  the key is made for.
- Updates come through the app: the start screen offers **Update and restart** when a newer
  version is out.

The other files of an app release are the same app as a zip and the files the updater reads.

## GPU speech models

Steadyline runs speech recognition on an NVIDIA GPU with these models. The app fetches them itself
when it needs them; there's nothing to download by hand. Each model is one release, named after
its folder:

| Release | Chunk size | Files |
|---|---|---|
| `sherpa-onnx-nemotron-speech-streaming-en-0.6b-80ms-fp16-2026-11-14` | 80 ms | encoder (fp16), decoder, joiner, tokens |
| `sherpa-onnx-nemotron-speech-streaming-en-0.6b-160ms-fp16-2026-11-14` | 160 ms | encoder (fp16), decoder, joiner, tokens |

They are a derivative of NVIDIA's
[nemotron-speech-streaming-en-0.6b](https://huggingface.co/nvidia/nemotron-speech-streaming-en-0.6b),
exported to ONNX with a fixed chunk size and the encoder converted to 16-bit floating point. The
app checks every file against its SHA-256 before using it.

## Model license

The speech models are licensed by NVIDIA Corporation under the NVIDIA Open Model License. See [Notice.txt](Notice.txt)
and the agreement in [NVIDIA-Open-Model-License.pdf](NVIDIA-Open-Model-License.pdf); each release
carries both files too.
