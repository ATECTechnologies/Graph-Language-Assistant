# CodeMind

**A code-intelligence model that reads code as a map of relationships — and writes, fixes, explains and checks it.**

CodeMind understands software the way an engineer does: not as a long string of characters, but as **what calls what, what feeds what and what runs before what**. It turns code (and requests in human language) into graphs, understands them with specialised networks, writes an answer, and **checks its own answer** before giving it — and when it is not sure, it says so.

It is self-hosted: you run it on your own machine or server, at the precision and on as many GPUs as you choose.

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

Three versions are available. Each is a separate model with its **own documentation** and its **own license**.

| | **CodeMind 1.0** | **CodeMind 2.0** | **CodeMind 3.0** |
|---|---|---|---|
| Size | ≈ 3.3 B parameters | ≈ 6.1 B parameters | ≈ 17.9 B parameters |
| Answers with | Code | Code and text | Code and text |
| Human languages | Requests read as instructions; answers in code | About 20 | 24 |
| Trained on | One 80 GB-class GPU | One 180 GB-class GPU | Two 180 GB-class GPUs |
| Writing context | Up to 32,768 positions | Up to 180,000 positions | Up to 180,000 tokens |
| Runs with | The CodeMind 1.0 server (served by the developer) | `codemindai` library | `codemindai` library |
| Documentation | [Technical overview](docs/CodeMind_1.0_Technical_Overview.md) | [Technical overview](docs/CodeMind_2.0_Technical_Overview.md) | [Technical overview](docs/CodeMind_3.0_Technical_Overview.md) |
| License | [CodeMind 1.0 License](licenses/LICENSE-CodeMind-1.0.md) | [CodeMind 2.0 License](licenses/LICENSE-CodeMind-2.0.md) | [CodeMind 3.0 License](licenses/LICENSE-CodeMind-3.0.md) |

### What each version brought

**1.0 — the foundation**
- Code becomes a typed graph; two networks understand it (one for the code, one for the change to make).
- A structural code writer, a layered validator, and learning from its own validated answers.
- A standard, code-free model folder, served privately through an OpenAI-compatible API.

**2.0 — language and exactness**
- A third network for **human language**, so requests in many languages are understood directly.
- A separate **text writer** for prose answers, next to the code writer.
- An **exact math and physics engine** inside the learning loop.
- Expert routing (12 experts), policy-driven **safety**, and the **`codemindai`** library for anyone to run the model.

**3.0 — one writer, deeper graphs**
- About **3× larger**, trained on ≈ 620 GB across two GPUs as one model.
- **One writer for code and text** with one open vocabulary — any name, number, script or language can be written — that reads the request word by word and consults a memory of what the networks understood.
- **Deeper graph reading:** relationships flow in both directions, every node knows where it sits, every layer sees the whole graph.
- Learns to understand code **without a hand-written parser** for the language.
- **One reward** teaches writing, expert choice and confidence together; the model also practises **repairing its own mistakes**.

Read each version's technical overview for the full picture of that version.

---

## Quick start (2.0 and 3.0)

```bash
pip install torch --index-url https://download.pytorch.org/whl/cu128   # the build for your system
pip install "codemindai[server]"
```

```python
import codemindai

model = codemindai.load("./Model_CodeMind")         # the model folder you downloaded
print(model.chat("Explain what a race condition is."))
print(model.code("Write a function that merges two sorted lists", language="python"))
```

Serve it as an OpenAI-compatible API:

```bash
codemindai init
codemindai serve --host 0.0.0.0
```

Requirements: Windows 10/11 or Linux, Python 3.11–3.13, PyTorch 2.4+, an NVIDIA GPU (CPU works for testing). Precision: FP32, BF16, FP16, FP8 or FP4.

---

## License at a glance

| | 1.0 | 2.0 | 3.0 |
|---|---|---|---|
| Use commercially to run your own website, app or API service | ✅ | ✅ | ✅ |
| Charge users for that service | ✅ | ✅ | ✅ |
| Modify / fine-tune the model | ✅ | ✅ | ✅ |
| Share it or your modified version free, as open source, under the same license | ✅ | ✅ | ✅ |
| **Sell** the model or a modified version, in any form | ❌ | ❌ | ❌ |
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

The model weights are distributed separately from this repository. Training source code and data are not part of the public release.

---

*CodeMind — © FWKTechnologies.*
