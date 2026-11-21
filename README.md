# Repolex Knowledge Graph of zkat/supports-unicode

RDF knowledge graph data for [zkat/supports-unicode](https://github.com/zkat/supports-unicode), parsed by [repolex](https://repolex.ai).

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
rlex download zkat/supports-unicode
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── f886c823e6f4b5760171fbafcbe42ede41e26d6c
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── f886c823e6f4b5760171fbafcbe42ede41e26d6c.nq.gz
│   └── repolex
│       └── f886c823e6f4b5760171fbafcbe42ede41e26d6c
│           └── chunk-001.nq.gz
├── blob
│   ├── 164c7d366609da3e192acd8a25717ca0291e924a.nq.gz
│   ├── 1b83b43660bc201f6db5af13681a8013a89b63e2.nq.gz
│   ├── 48cbe2966fc00e82204a14c38b7365ab3af1c701.nq.gz
│   ├── 545f464b21a29953bbd564289a029dc157a10477.nq.gz
│   ├── 59e9d34efcff31280ca86aa2dac536046f33c8ff.nq.gz
│   ├── 7cea1b5394d9e54f3cfd30e5595084667fec8869.nq.gz
│   ├── 850f4631d329d487dfac871e08b9d9b6d9fe9594.nq.gz
│   ├── 86121202a8b946004d522124f7c2faa8001bcde3.nq.gz
│   ├── 96ef6c0b944e24fc22f51f18136cd62ffd5b0b8f.nq.gz
│   └── a04ed1d7db63ec6e0b7d067a07942ce0b89bb08c.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── f886c823e6f4b5760171fbafcbe42ede41e26d6c.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

14 directories, 19 files
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

[zkat/supports-unicode](https://github.com/zkat/supports-unicode)

---
*Parsed on 2026-11-21 by [repolex](https://repolex.ai)*
