# GLA — Graph-Language Assistant

**An AI model that reads code as a map of relationships — and writes, fixes, explains and checks it.**
Made by **ATEC** (Advancement Through Engineering & Creation).

> **GLA is proprietary — it is not open source.** Every version is owned by **ATEC** and is used under its own GLA
> license, not under an open-source license (it is not MIT, Apache, GPL, Creative Commons or similar). Being able to
> download a version free of charge does **not** make it open source: the license still forbids selling it and
> requires credit to ATEC.

---

## The names

| Name | What it means |
|---|---|
| **ATEC** | **Advancement Through Engineering & Creation** — the company that develops and owns GLA |
| **GLA** | The AI and its models: GLA 1.0, GLA 2.0, GLA 3.0 |
| **Graph-Language Assistant** | GLA written out in full, and the name of the **architecture** all GLA models are built on |
| **`gla-api`** | The official Python library that runs and serves GLA 2.0 and 3.0 (version 1.2.1 or newer for the GLA 3.0 release) — https://pypi.org/project/gla-api/ |

GLA was previously called **CodeMind**, and its library was published as `codemindai-api`; `gla-api` replaces it.
Older files and folders with those names (for example `Model_CodeMind/`, `codemindai_api_data/`) are the same models
and data, and keep working with `gla-api`.

---

## What GLA does

GLA understands software the way an engineer does: not as a long string of characters, but as **what calls what,
what feeds what and what runs before what**. It turns code — and requests written in human language — into graphs,
understands them with specialised networks, writes an answer, and **checks its own answer** before giving it. When it
is not sure, it says so, says why, and asks what it needs to know.

- **Writes code** in any programming language from a request in plain language.
- **Fixes and edits** existing code, including very large files.
- **Explains** code and answers technical questions.
- **Checks code** — syntax, structure, hidden "fake" solutions, safety — with a built-in validator.
- **Computes exact numbers** — arithmetic, units, physics formulas — with a built-in calculator instead of guessing.
- **Is honest about uncertainty** — an answer it is not sure of is marked, with the reason.

---

## Versions

There are three versions. Each is a separate model with its **own documentation** and its **own license**.

| | **GLA 1.0** | **GLA 2.0** | **GLA 3.0** |
|---|---|---|---|
| Availability | **Not released** — no download, no distribution | **Downloadable** — run it yourself under its license | **Downloadable** — run it yourself under its license |
| License type | Proprietary **access** license | Proprietary **model** license | Proprietary **model** license |
| Size | ≈ 3.3 B parameters | ≈ 6.1 B parameters | ≈ 21.2 B parameters |
| Answers with | Code | Code and text | Code and text |
| Human languages | Requests read as instructions; answers in code | About 20 | 30 |
| Trained on | One 80 GB-class GPU | One 180 GB-class GPU | Three 180 GB-class GPUs (≈ 742 GB of data) |
| Writing context | Up to 32,768 positions | Up to 180,000 positions | Up to 180,000 tokens |
| Runs with | Only ATEC's own GLA 1.0 server — **not** `gla-api` | `gla-api` | `gla-api` 1.2.1 or newer |
| GPU memory for the weights | — | ≈ 12 GB BF16 · 6 GB FP8 · 4 GB FP4 | ≈ 42 GB BF16 · 21 GB FP8 · 13 GB FP4 |
| Documentation | [Technical overview](docs/GLA_1.0_Technical_Overview.md) | [Technical overview](docs/GLA_2.0_Technical_Overview.md) | [Technical overview](docs/GLA_3.0_Technical_Overview.md) |
| License | [GLA 1.0 License](licenses/LICENSE-GLA-1.0.md) | [GLA 2.0 License](licenses/LICENSE-GLA-2.0.md) | [GLA 3.0 License](licenses/LICENSE-GLA-3.0.md) |

### What each version brought

**GLA 1.0 — the foundation**
- Code becomes a typed graph; two networks understand it (one for the code, one for the change to make).
- A structural code writer, a layered validator, and learning from its own validated answers.
- A standard, code-free model folder, run only by ATEC on its own server (never released).

**GLA 2.0 — language and exactness**
- A third network for **human language**, so requests in many languages are understood directly.
- A separate **text writer** for prose answers, next to the code writer.
- An **exact math and physics engine** inside the learning loop.
- Expert routing (12 experts), policy-driven **safety**, and the **`gla-api`** library so anyone can run the
  model.

**GLA 3.0 — one writer, graphs that reach**
- About **3.5× larger** (≈ 21.2 B), trained on ≈ 742 GB in 30 human languages across three GPUs as one model.
- **One writer for code and text** with one open vocabulary — any name, number, script or language can be written —
  that reads the request word by word and consults a memory of what the networks understood.
- **Graphs that reach:** every file becomes one connected graph in every language, relationships flow in both
  directions, and every node can look up any part of its graph directly by content — information now crosses whole
  files instead of fading after a few steps.
- Learns to understand code **without a hand-written parser** for the language.
- **One reward** teaches writing, expert choice and confidence together; the model also practises **repairing its own
  mistakes**.

Each version's technical overview explains that version in full.

---

## Availability

| | GLA 1.0 | GLA 2.0 | GLA 3.0 |
|---|---|---|---|
| Model files available to download | ❌ No | ✅ Yes | ✅ Yes |
| Runs with the `gla-api` library | ❌ No | ✅ Yes | ✅ Yes |
| Run it on your own machine or server | ❌ No | ✅ Yes | ✅ Yes |
| How you can use it | Only through access granted by ATEC (for example an API key to its server) | Your own copy | Your own copy |

**About GLA 1.0.** GLA 1.0 is **not released and not distributed** in any form. Its weights stay with ATEC, and the
`gla-api` library cannot load it. Its technical overview is published **for information only** — it explains
how 1.0 works, but it does not make the model available. Any file, package or website offering "GLA 1.0" or
"CodeMind 1.0" for download is not authorized.

To run a GLA model yourself, use **GLA 2.0** or **GLA 3.0**.

---

## Install and run (GLA 2.0 and 3.0)

The official library is **`gla-api`**: **https://pypi.org/project/gla-api/**

```bash
pip install "gla-api>=1.2.2"
```

One command installs the model runtime **and** the API server. Requirements: Windows 10/11 or Linux, Python
3.11–3.13, an NVIDIA GPU (a CPU works for testing). For an NVIDIA GPU on Windows, install the CUDA build of PyTorch
first: `pip install torch --index-url https://download.pytorch.org/whl/cu128`.

**Serve the model to your website or app** (OpenAI-compatible API):

```bash
mkdir my-gla && cd my-gla
gla-api setup --owner my-website     # settings, a Model_GLA/ folder and your first API key (shown once)
# copy the downloaded model's files into Model_GLA/
gla-api start                        # API server in the background: http://127.0.0.1:8000/v1
gla-api status                       # running? model loaded?
gla-api chat "Explain what a race condition is."
```

**Or use it inside your own Python program:**

```python
import gla_api

model = gla_api.load("./Model_GLA")
print(model.chat("Explain what a race condition is."))
print(model.code("Write a function that merges two sorted lists", language="python"))

big = gla_api.load("./Model_GLA", devices="all")            # one copy per GPU
huge = gla_api.load("./Model_GLA", devices="all", split=3)  # GLA 3.0: each copy over 3 smaller GPUs
```

**Everyday commands**

| | |
|---|---|
| `gla-api start` · `stop` · `restart` · `status` · `logs` | run and watch the server in the background (`--split 3` spreads each GLA 3.0 copy over 3 GPUs) |
| `gla-api key create --owner NAME` · `key list` · `key rotate ID` · `key revoke ID` | API keys with per-key limits |
| `gla-api config show` · `config set port 9000` | settings of the folder |
| `gla-api doctor` | full check of the computer, GPUs and model files |
| `gla-api backup` · `check-update` | back up keys and settings; look for a newer library |

Every command, the Python API, the HTTP client and all settings are described on the
[library page](https://pypi.org/project/gla-api/) and in each version's technical overview.

Windows tip: if `pip` or `gla-api` is "not recognized", use `py -m pip install gla-api` and
`py -m gla_api <command>`.

---

## License at a glance

All three licenses are **proprietary licenses written by ATEC**. None of them is an open-source license. GLA is
**licensed, not sold**: you receive permission to use it, never ownership of it.

- **GLA 1.0 — access license.** You never receive the model. If ATEC gives you access (for example an API key to its
  server), you may use GLA 1.0 inside your own website, app or API service, including commercially. You may not copy,
  modify, share, sell or resell it, or your access.
- **GLA 2.0 and 3.0 — model licenses.** You receive a copy and run it yourself. You may use it commercially in your own
  services and modify it. You may give copies to others only **free of charge and only under the same GLA license** —
  never under an open-source or any other license — and you may **never sell** it.

| | 1.0 | 2.0 | 3.0 |
|---|---|---|---|
| Download the model / get a copy | ❌ Never | ✅ | ✅ |
| Use commercially in your own website, app or API service | ✅ Only through access granted by ATEC | ✅ | ✅ |
| Charge users for that service | ✅ | ✅ | ✅ |
| Modify / fine-tune the model | ❌ | ✅ | ✅ |
| Give copies (original or modified) to others free of charge, only under the same GLA license | ❌ | ✅ | ✅ |
| Call it, or your modified version, "open source" or put it under another license | ❌ | ❌ | ❌ |
| **Sell** the model or a modified version, in any form | ❌ | ❌ | ❌ |
| Resell, share or transfer access / API keys | ❌ | — | — |
| Train another model on its outputs to imitate it | ❌ (without written permission) | Counts as a modified version | Counts as a modified version |
| Use "GLA", "Graph-Language Assistant" or "ATEC" as your own product's name | ❌ | ❌ | ❌ |
| Credit ATEC | Always required | Always required | Always required |
| Safety and responsibility duties for public services | — | Required | Required, plus transparency and security duties |

Credit line to use:

> **Built with GLA &lt;version&gt; by ATEC** — https://github.com/ATECTechnologies/Graph-Language-Assistant

This table is a summary. **Each version's license file is what governs** — see [`LICENSE`](LICENSE) and the
[`licenses/`](licenses/) folder.

---

## Repository

```
README.md                          this page
LICENSE                            which license applies to which version
licenses/
  LICENSE-GLA-1.0.md
  LICENSE-GLA-2.0.md
  LICENSE-GLA-3.0.md
docs/
  GLA_1.0_Technical_Overview.md
  GLA_2.0_Technical_Overview.md
  GLA_3.0_Technical_Overview.md
```

The model weights of **GLA 2.0 and 3.0** are distributed separately from this repository. **GLA 1.0 weights are not
distributed at all.** Training source code and data are not part of the public release for any version.

---

*GLA — Graph-Language Assistant. © ATEC (Advancement Through Engineering & Creation).*
