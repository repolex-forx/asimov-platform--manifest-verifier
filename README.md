# Repolex Knowledge Graph of asimov-platform/manifest-verifier

RDF knowledge graph data for [asimov-platform/manifest-verifier](https://github.com/asimov-platform/manifest-verifier), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [lexq](https://github.com/repolex-ai/lexq) query tool using [uv](https://docs.astral.sh/uv/getting-started/installation/).

If you have uv installed, just copy/paste this into your terminal:

```bash
uv tool install git+https://github.com/repolex-ai/lexq
```

This installs lexq onto your system, in your user context. Verify the install:

```bash
lexq --help
```

**lexq is designed to be used primarily by LLMs in a terminal.** Start up your favorite LLM and ask it to use the lexq tool. It's that easy!

To load this repo's data:

```bash
lexq download asimov-platform/manifest-verifier
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   ├── d99d86878c2ecbd8c40fbc57e35b4477590b8287
│   │   │   └── chunk-001.nq.gz
│   │   ├── d99d86878c2ecbd8c40fbc57e35b4477590b8287.nq.gz
│   │   └── f96b0752150029af9d1b51e6c77d89940fec0803.nq.gz
│   ├── lsp
│   │   ├── d99d86878c2ecbd8c40fbc57e35b4477590b8287.nq.gz
│   │   └── f96b0752150029af9d1b51e6c77d89940fec0803.nq.gz
│   └── repolex
│       ├── d99d86878c2ecbd8c40fbc57e35b4477590b8287
│       │   └── chunk-001.nq.gz
│       ├── d99d86878c2ecbd8c40fbc57e35b4477590b8287.nq.gz
│       └── f96b0752150029af9d1b51e6c77d89940fec0803.nq.gz
├── blob
│   ├── 0e190b0515727c4dff4ccc023bb0fa43836c4840.nq.gz
│   ├── 14b829ae4a8bd0e5c9d793f9e190c09c1a9ea245.nq.gz
│   ├── 15ff50da1665da30e9dee1a6c59b03647846d27c.nq.gz
│   ├── 17e052080cd791a92fcce2bb7d57f833715819eb.nq.gz
│   ├── 1cede6cec57fb16d825ff6035f7237642352a1c3.nq.gz
│   ├── 2091312cedc106b30f5850b70cdd9f48265ec54e.nq.gz
│   ├── 42f314f04b51b036b226dfe6d620d2328278a0a9.nq.gz
│   ├── 582b00a043cae5926c595ee141e837eaad2c43a9.nq.gz
│   ├── 5aa9cbd720935c575879bf683105d771e0f0abc8.nq.gz
│   ├── 5b632085e2fcbea91c470241dad895fa76fdef62.nq.gz
│   ├── 6cfeefa5b5cd77e1949b3079e041f06db63a16fb.nq.gz
│   ├── 74ef8e7d637334a9cdce291802b0fad7592c4986.nq.gz
│   ├── 7ecf123a670f5e0ed7eb8563a597a21bdfd17c7f.nq.gz
│   ├── 8266925e6f1f136e53d1b655577057e05f7de429.nq.gz
│   ├── ac490563452b120b56f59e992fbfe4a63cea233e.nq.gz
│   ├── b3cee64ac92097b6c14ee058ce5d2dbab49e9943.nq.gz
│   ├── be0adfaadd0517aafe70202896440ca7827d0dac.nq.gz
│   ├── c40ed1026bd29641c95d0817221859f92edd712a.nq.gz
│   ├── cadc6eee85cacc264bb69b8283412ac862ed92c4.nq.gz
│   ├── cc34d84b0cf1967900d28162bf86ba92197e3bf2.nq.gz
│   ├── d3217bf5f4415ce684628ec18292d6bfc51c3ea7.nq.gz
│   ├── e0bf4a69de6fc26239cee77d54201cd4971f6bcb.nq.gz
│   ├── f790038dcc2d887d65c9aa6ed4f230d5f7090fe3.nq.gz
│   ├── fd5fa1e1071379441f535cf94ada6890753f1f54.nq.gz
│   ├── fedaa2b1d2a80a9dc199386a1f248ca92f4cf54c.nq.gz
│   └── ffe21ded32ae96b8b03696b8911dd0e49a3c237e.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   ├── d99d86878c2ecbd8c40fbc57e35b4477590b8287.nq.gz
│   └── f96b0752150029af9d1b51e6c77d89940fec0803.nq.gz
├── filetree
│   ├── d99d86878c2ecbd8c40fbc57e35b4477590b8287.nq.gz
│   └── f96b0752150029af9d1b51e6c77d89940fec0803.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 41 files
```

| Directory | What it contains |
|-----------|-----------------|
| `blob/` | Per-file AST graphs, content-addressed by git blob SHA. Each file in the source repo gets its own graph. |
| `aggregate/ast/` | Combined AST graph per parsed commit. Merges all blob graphs for a snapshot of the entire codebase at that point. |
| `aggregate/lsp/` | Language Server Protocol enrichment: resolved symbols, definitions, references, and type information. |
| `aggregate/dataflow/` | Interprocedural data flow edges between functions and modules. |
| `aggregate/repolex/` | Combined graph (AST + LSP + dataflow) per commit. |
| `commit/` | Git commit metadata (author, date, message, parent links). |
| `branch/` | Branch metadata. |
| `tag/` | Tag metadata. |
| `filetree/` | File tree snapshots per commit (which files existed and their blob SHAs). |

## Source repository

[asimov-platform/manifest-verifier](https://github.com/asimov-platform/manifest-verifier)

---
*Parsed on 2026-04-15 by [repolex](https://repolex.ai)*
