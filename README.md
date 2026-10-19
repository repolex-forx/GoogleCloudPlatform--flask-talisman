# Repolex Knowledge Graph of GoogleCloudPlatform/flask-talisman

RDF knowledge graph data for [GoogleCloudPlatform/flask-talisman](https://github.com/GoogleCloudPlatform/flask-talisman), parsed by [repolex](https://repolex.ai).

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
rlex download GoogleCloudPlatform/flask-talisman
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 0040966bed66634db3d0f0b627b9bc6b541238d5
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 0040966bed66634db3d0f0b627b9bc6b541238d5
│           └── chunk-001.nq.gz
├── blob
│   ├── 0a60e37ad588526c8e5a07d9dc98b2bf87ad4373.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 2c5c028cdb64dba7f0aa3588e16c1c73298c0608.nq.gz
│   ├── 2d55d13d67e1d4310a5c2982fd287d46d0c2c741.nq.gz
│   ├── 31b5b2b1d915019b57cf22f1929dbeb9c5c4c20f.nq.gz
│   ├── 34e28804ec425ded280f71de22db4855bba10780.nq.gz
│   ├── 6736efd943c8d138a3ed74be795227c9d0fcfedc.nq.gz
│   ├── 8698c2ff2e5dca83110866149cf231568a22d163.nq.gz
│   ├── 8c75fc494ed8706e63ed44520a38cb3bd4109e2f.nq.gz
│   ├── 9228356ecdad6165ce84b8d2f0025e098173a0ed.nq.gz
│   ├── ab866a94be3d770835539e7cefa786d62c3994d7.nq.gz
│   ├── ccb0af964472e70303df4fa2cc8d025aa75c7b48.nq.gz
│   ├── d5e3ca17a1891584022370c7838a4ac798d0b548.nq.gz
│   ├── d91027c8c196be256d03193afc91c4e38d4fee91.nq.gz
│   ├── de742cee4ff1f7d9a75631f1465246f84eb979c8.nq.gz
│   └── fcc22df6fb16e63ed8568b065be1d8bd6f5b9842.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 0040966bed66634db3d0f0b627b9bc6b541238d5.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 24 files
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

[GoogleCloudPlatform/flask-talisman](https://github.com/GoogleCloudPlatform/flask-talisman)

---
*Parsed on 2026-10-19 by [repolex](https://repolex.ai)*
