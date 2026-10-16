# Repolex Knowledge Graph of glue-viz/jupyter-output-monitor

RDF knowledge graph data for [glue-viz/jupyter-output-monitor](https://github.com/glue-viz/jupyter-output-monitor), parsed by [repolex](https://repolex.ai).

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
rlex download glue-viz/jupyter-output-monitor
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 069b71b2b94174fe953e6171d52f055611b98efb
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 069b71b2b94174fe953e6171d52f055611b98efb
│           └── chunk-001.nq.gz
├── blob
│   ├── 1df8de57f8d586f14fabc2f013f17e17b90927ef.nq.gz
│   ├── 38971cc6232c89c6c0f09d8e279f28efa5e8fddf.nq.gz
│   ├── 426c3452e54d7bc1bce5352987a2a70faac2cfcb.nq.gz
│   ├── 45988c98d3f9f02879cc0d857c0e03191bfddc76.nq.gz
│   ├── 4881aeabfd4d97da0b23bd97c4bad92e7908225e.nq.gz
│   ├── 5137fcf8fab609887a7b67eb1ebd49ec337b1f2d.nq.gz
│   ├── 5d9160808864ce25014cbd460016d4a235327d8e.nq.gz
│   ├── 67e5fbe83d106aaa09b82d13d51f987ceaf9b7dd.nq.gz
│   ├── 6b0c235992bd42858029a97cf48d4950a1438b9a.nq.gz
│   ├── 70f25b0c8d8aa2bc409e65ec67110fb922f56a3e.nq.gz
│   ├── 92c3bc0c2673f531c691f2ffd3efaa50eda1e6ae.nq.gz
│   ├── bc2888a953621efdb51dc1a5822f8d9c97c238f2.nq.gz
│   ├── c1e1d702a6a45fce1dc1d4a72e1920e58025fa1f.nq.gz
│   ├── d0fcea43e35c1c1ab8868a88b8233564dc167274.nq.gz
│   ├── d587fb02aa237bf977ee882772371710c68ea7e9.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── ec9ffd611eec1e1fa3b4a765d0c798249bea2cb7.nq.gz
│   └── f17fa68cc3bf0ba2e9042f211c152806beac2fa5.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 069b71b2b94174fe953e6171d52f055611b98efb.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 26 files
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

[glue-viz/jupyter-output-monitor](https://github.com/glue-viz/jupyter-output-monitor)

---
*Parsed on 2026-10-16 by [repolex](https://repolex.ai)*
