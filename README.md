# CodeMind

**A code-intelligence model that reads code as a map of relationships — and writes, fixes, explains and checks it.**

CodeMind understands software the way an engineer does: not as a long string of characters, but as **what calls what, what feeds what and what runs before what**. It turns code (and requests in human language) into graphs, understands them with specialised networks, writes an answer, and **checks its own answer** before giving it — and when it is not sure, it says so.

> **CodeMind is proprietary — it is not open source.** Every version is owned by **FWKTechnologies** and is used under its own CodeMind license, not under an open-source license (it is not MIT, Apache, GPL, Creative Commons or similar). Being able to download a version free of charge does **not** make it open source: the license still forbids selling it and requires credit to the developer.

CodeMind **2.0** and **3.0** can be downloaded: you download the model and run it yourself, on your own machine or server, with the `codemindai-api` library, at the precision and on as many GPUs as you choose. CodeMind **1.0** is not released — see [Availability](#availability).

---

## What it does

- **Writes code** in any programming language from a request in plain language.
- **Fixes and edits** existing code, including very large files.
- **Explains** code and answers technical questions.
- **Checks code** — syntax, structure, hidden "fake" solutions, safety — with a built-in validator.
- **Computes exact numbers** — arithmetic, units, physics formulas — with a built-in calculator instead of guessing.
- **Says when it is unsure**, why, and what information would help.

---

## Versions

There are three versions. Each is a separate model with its **own documentation** and its **own license**.

| | **CodeMind 1.0** | **CodeMind 2.0** | **CodeMind 3.0** |
|---|---|---|---|
| Availability | **Not released** — no download, no distribution | **Downloadable** — run it yourself under its license | **Downloadable** — run it yourself under its license |
| License type | Proprietary **access** license | Proprietary **model** license | Proprietary **model** license |
| Size | ≈ 3.3 B parameters | ≈ 6.1 B parameters | ≈ 17.9 B parameters |
| Answers with | Code | Code and text | Code and text |
| Human languages | Requests read as instructions; answers in code | About 20 | 24 |
| Trained on | One 80 GB-class GPU | One 180 GB-class GPU | Two 180 GB-class GPUs |
| Writing context | Up to 32,768 positions | Up to 180,000 positions | Up to 180,000 tokens |
| Runs with | Only the developer's own CodeMind 1.0 server — **not** the `codemindai-api` library | `codemindai-api` library | `codemindai-api` library |
| Documentation | [Technical overview](docs/CodeMind_1.0_Technical_Overview.md) | [Technical overview](docs/CodeMind_2.0_Technical_Overview.md) | [Technical overview](docs/CodeMind_3.0_Technical_Overview.md) |
| License | [CodeMind 1.0 License](licenses/LICENSE-CodeMind-1.0.md) | [CodeMind 2.0 License](licenses/LICENSE-CodeMind-2.0.md) | [CodeMind 3.0 License](licenses/LICENSE-CodeMind-3.0.md) |

### What each version brought

**1.0 — the foundation**
- Code becomes a typed graph; two networks understand it (one for the code, one for the change to make).
- A structural code writer, a layered validator, and learning from its own validated answers.
- A standard, code-free model folder, run only by the developer on its own server (never released).

**2.0 — language and exactness**
- A third network for **human language**, so requests in many languages are understood directly.
- A separate **text writer** for prose answers, next to the code writer.
- An **exact math and physics engine** inside the learning loop.
- Expert routing (12 experts), policy-driven **safety**, and the **`codemindai-api`** library for anyone to run the model.

**3.0 — one writer, deeper graphs**
- About **3× larger**, trained on ≈ 620 GB across two GPUs as one model.
- **One writer for code and text** with one open vocabulary — any name, number, script or language can be written — that reads the request word by word and consults a memory of what the networks understood.
- **Deeper graph reading:** relationships flow in both directions, every node knows where it sits, every layer sees the whole graph.
- Learns to understand code **without a hand-written parser** for the language.
- **One reward** teaches writing, expert choice and confidence together; the model also practises **repairing its own mistakes**.

Read each version's technical overview for the full picture of that version.

---

## Availability

| | CodeMind 1.0 | CodeMind 2.0 | CodeMind 3.0 |
|---|---|---|---|
| Model files available to download | ❌ No | ✅ Yes | ✅ Yes |
| Runs with the `codemindai-api` library | ❌ No | ✅ Yes | ✅ Yes |
| Run it on your own machine or server | ❌ No | ✅ Yes | ✅ Yes |
| How you can use it | Only through access granted by FWKTechnologies (e.g. an API key to its server) | Your own copy | Your own copy |

**About CodeMind 1.0.** CodeMind 1.0 is **not released and not distributed** in any form. Its weights stay with FWKTechnologies, and the `codemindai-api` library cannot load it. Its technical overview is published **for information only** — it explains how 1.0 works, but it does not make the model available. Any file, package or website offering "CodeMind 1.0" for download is not authorized.

If you want to run a CodeMind model yourself, use **2.0** or **3.0**.

---

## Quick start

`codemindai-api` runs **CodeMind 2.0 and 3.0** (it detects the version from the model folder). It does not run 1.0.

```bash
pip install torch --index-url https://download.pytorch.org/whl/cu128   # the build for your system
pip install "codemindai-api[server]"
```

```python
import codemindai_api

model = codemindai_api.load("./Model_CodeMind")         # the model folder you downloaded
print(model.chat("Explain what a race condition is."))
print(model.code("Write a function that merges two sorted lists", language="python"))
```

Serve it as an OpenAI-compatible API:

```bash
codemindai-api init
codemindai-api serve --host 0.0.0.0
```

Requirements for `codemindai-api`: Windows 10/11 or Linux, Python 3.11–3.13, PyTorch 2.4+, an NVIDIA GPU (CPU works for testing). Precision: FP32, BF16, FP16, FP8 or FP4.

---

## License at a glance

All three licenses are **proprietary licenses written by FWKTechnologies**. None of them is an open-source license. CodeMind is **licensed, not sold**: you receive permission to use it, never ownership of it.

- **1.0 — access license.** You never receive the model. If FWKTechnologies gives you access (for example an API key to its server), you may use 1.0 inside your own website, app or API service, including commercially. You may not copy, modify, share, sell or resell it, or your access.
- **2.0 and 3.0 — model licenses.** You receive a copy and run it yourself. You may use it commercially in your own services and modify it. You may give copies to others only **free of charge and only under the same CodeMind license** — never under an open-source or any other license — and you may **never sell** it.

| | 1.0 | 2.0 | 3.0 |
|---|---|---|---|
| Download the model / get a copy | ❌ Never | ✅ | ✅ |
| Use commercially in your own website, app or API service | ✅ Only through access granted by FWKTechnologies | ✅ | ✅ |
| Charge users for that service | ✅ | ✅ | ✅ |
| Modify / fine-tune the model | ❌ | ✅ | ✅ |
| Give copies (original or modified) to others free of charge, only under the same CodeMind license | ❌ | ✅ | ✅ |
| Call it, or your modified version, "open source" or put it under another license | ❌ | ❌ | ❌ |
| **Sell** the model or a modified version, in any form | ❌ | ❌ | ❌ |
| Resell, share or transfer access / API keys | ❌ | — | — |
| Train another model on its outputs to imitate it | ❌ (without written permission) | Counts as a modified version | Counts as a modified version |
| Credit the main developer | Always required | Always required | Always required |
| Safety and responsibility duties for public services | — | Required | Required, plus transparency and security duties |

Credit line to use:

> **Built with CodeMind &lt;version&gt; by FWKTechnologies** — https://github.com/FWKTechnologies/CodeMind-Code-Intelligence

This table is a summary. **Each version's license file is what governs** — see [`LICENSE`](LICENSE) and the [`licenses/`](licenses/) folder.

---

## Repository

```
README.md                         this page
LICENSE                           which license applies to which version
licenses/
  LICENSE-CodeMind-1.0.md
  LICENSE-CodeMind-2.0.md
  LICENSE-CodeMind-3.0.md
docs/
  CodeMind_1.0_Technical_Overview.md
  CodeMind_2.0_Technical_Overview.md
  CodeMind_3.0_Technical_Overview.md
```

The model weights of **2.0 and 3.0** are distributed separately from this repository. **1.0 weights are not distributed at all.** Training source code and data are not part of the public release for any version.

---

*CodeMind — © FWKTechnologies.*
