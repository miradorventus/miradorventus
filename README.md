## Local AI on hardware people actually own

Most local-AI tooling assumes an NVIDIA card and a tolerance for debugging your
own driver stack. I build the missing half: installers that work on **consumer
AMD GPUs**, model management that does not waste your disk, and measurements
that tell you what your machine can really do instead of what a benchmark
leaderboard says.

Everything published here was tested on the machine it was written for, and I
say which machine that is.

### Projects

| Project | What it does |
|---|---|
| **[ollama-amd-plug-and-play](https://github.com/miradorventus/ollama-amd-plug-and-play)** | Ollama + Open WebUI on AMD, with ROCm set up for you. Ubuntu / Mint. |
| **[comfyui-amd-plug-and-play](https://github.com/miradorventus/comfyui-amd-plug-and-play)** | ComfyUI on AMD, AllTalk and Wan2.2 workflows ready to run. Ubuntu / Mint. |
| **[EZmodL](https://github.com/miradorventus/EZmodL)** | GGUF model manager for llama-swap: search HuggingFace, classify quantizations against your real VRAM budget, symlink Ollama blobs instead of duplicating gigabytes. |
| **[ClaudeCode-RulesAfterCompact-Windows-AutoHook](https://github.com/miradorventus/ClaudeCode-RulesAfterCompact-Windows-AutoHook)** | Puts your Claude Code rules back in context after compaction, and fixes the silent UTF-8 corruption that breaks the reminder on Windows. |

### How I work

**Measure, don't assume.** A broken measurement setup does not raise an error.
It produces numbers that are consistent, plausible and wrong - and a clean curve
is not evidence that you measured the thing you meant to measure. Most of my
benchmarking time goes into proving a result is real before believing it.

**Check what exists before building it.** Reading the repository beats reading
the search results, every single time. Assembling tools that already work beats
rewriting them.

**Name the hardware.** Radeon RX 9070 XT (16 GB), Windows 11 and Linux Mint.
Numbers from that machine are labelled as such; mechanisms that generalize are
labelled as such too.
### Currently

Working out what a local reasoning model can actually be trusted with on a
16 GB consumer card - the usable context ceiling, whether reasoning should be
enabled, how many tools an agent can be given before it starts looping - and
turning those measurements into concrete settings rather than opinions.
