# Repolex Knowledge Graph of explosion/fastapi-explosion-extras

RDF knowledge graph data for [explosion/fastapi-explosion-extras](https://github.com/explosion/fastapi-explosion-extras), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [rlex](https://github.com/repolex-ai/rlex) query tool:

```bash
cargo install --git https://github.com/repolex-ai/rlex
```

Verify the install:

```bash
rlex --help
```

**rlex is designed to be used primarily by LLMs in a terminal.** Start up your favorite AI assistant and ask it to use rlex. It handles the SPARQL — you just ask questions in plain English.

To load this repo's data:

```bash
rlex download explosion/fastapi-explosion-extras
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── b8cbf8c28400ab2b37b5d5bb437f00be9e012f7f
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── b8cbf8c28400ab2b37b5d5bb437f00be9e012f7f
│           └── chunk-001.nq.gz
├── blob
│   ├── 00cbcbf740da1cd780b8b825856965634f769173.nq.gz
│   ├── 03737f079a11ab10c5bd7b22ac6345d158656393.nq.gz
│   ├── 23b15047c1124fa8039cbd128af3c7d0fec5f2bc.nq.gz
│   ├── 287a00bea19e3ae824a800af9217ce1011999fda.nq.gz
│   ├── 31cf98034c8c4300851761a7bc5d1e5bed8ddb22.nq.gz
│   ├── 3f1751c5906e911d159c85213d09152ad0cb3696.nq.gz
│   ├── 5f7be3355b4c89986c67ef1a93550bdd5ad73eb6.nq.gz
│   ├── 63fbef0e7e625240e1477564f2e4a4ecc8cb888c.nq.gz
│   ├── 68c8918ca9953c92188b1d5a171cbce6ebab9ae0.nq.gz
│   ├── 6a3bc130a2c6ff297ca398bc05f4420dbe71ed8f.nq.gz
│   ├── 761f36382916f46887234f2ab532683f609c36a8.nq.gz
│   ├── 7669d49f8ab9f999f0b34aa378bb327de4393f2b.nq.gz
│   ├── 95592e584441b4519ed7f920c31c6041e86a1d49.nq.gz
│   ├── 974841b96c143ac1c58229465cfc25fc5c86ef34.nq.gz
│   ├── 9b9a93952b176250aa870878271e896ebfe0948a.nq.gz
│   ├── b617e1cc62321964f4742038d4b79e137ec3b187.nq.gz
│   ├── c06577311db9aaa1effcc9650b8e39a11799afd7.nq.gz
│   ├── c788aca8df76667ab2e73396037d370a2ea08ce6.nq.gz
│   └── de7b1e2bfdc6950bf6276e93c6df62fdd45865fc.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── b8cbf8c28400ab2b37b5d5bb437f00be9e012f7f.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 26 files
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
| `audit/` | Code architecture and graph audit reports per commit. |

## Source repository

[explosion/fastapi-explosion-extras](https://github.com/explosion/fastapi-explosion-extras)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
