## Local AI on hardware people actually own

I bought a Radeon because it was the better card for the money. Then I tried to
run a local model on it, and discovered what that really costs.

If you have an AMD card you already know the shape of it: the guide stops working
at step four, the wheel does not exist for your ROCm version, and the most recent
answer on the forum is from two years ago and says "should work now". Nothing is
broken exactly - it just never quite finishes.

So I build the half that is missing. Installers that get to the end. Model
management that does not quietly store the same twelve gigabytes twice.
Measurements that describe *your* machine instead of someone else's leaderboard.

Everything here was tested on the machine it was written for, and I tell you
which machine that is.

### Projects

| Project | What it does |
|---|---|
| **[ollama-amd-plug-and-play](https://github.com/miradorventus/ollama-amd-plug-and-play)** | Ollama + Open WebUI on AMD, with ROCm set up for you. Ubuntu / Mint. |
| **[comfyui-amd-plug-and-play](https://github.com/miradorventus/comfyui-amd-plug-and-play)** | ComfyUI on AMD, AllTalk and Wan2.2 workflows ready to run. Ubuntu / Mint. |
| **[EZmodL](https://github.com/miradorventus/EZmodL)** | GGUF model manager for llama-swap: search HuggingFace, classify quantizations against your real VRAM budget, symlink Ollama blobs instead of duplicating gigabytes. |
| **[ClaudeCode-RulesAfterCompact-Windows-AutoHook](https://github.com/miradorventus/ClaudeCode-RulesAfterCompact-Windows-AutoHook)** | Puts your Claude Code rules back in context after compaction, and fixes the silent UTF-8 corruption that breaks the reminder on Windows. |

### How I work

**Measure, then try to prove yourself wrong.** I have produced a result that was
clean, monotonic and entirely false, and believed it for a while. A broken
measurement setup does not throw an error - it hands you numbers that agree with
each other, look reasonable, and are not true. Most of my benchmarking time now
goes into attacking my own results before trusting them.

**Read the repository, not the search results.** I have written tools that
already existed, in better versions, by people who had thought about it longer.
That is a specific kind of expensive. Now I go and read the thing first, and
assemble what works before writing anything new.

**Say which machine.** Radeon RX 9070 XT (16 GB), Windows 11 and Linux Mint.
"Works on my machine" is only useful information if you say whose machine, so
numbers that belong to this one are labelled, and so are the mechanisms that
travel to yours.

### Currently

Trying to find out what a local reasoning model can honestly be trusted with on
a 16 GB consumer card - where the usable context actually ends, whether thinking
should be on or off, how many tools you can hand an agent before it starts going
in circles. Not to publish a score. To end up with settings I can point at and
say: this is why.
