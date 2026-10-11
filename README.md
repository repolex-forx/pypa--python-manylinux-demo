# Repolex Knowledge Graph of pypa/python-manylinux-demo

RDF knowledge graph data for [pypa/python-manylinux-demo](https://github.com/pypa/python-manylinux-demo), parsed by [repolex](https://repolex.ai).

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
rlex download pypa/python-manylinux-demo
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 8247a02cc646048f32786e3b708be494ec730296
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 8247a02cc646048f32786e3b708be494ec730296
│           └── chunk-001.nq.gz
├── blob
│   ├── 1dbc687de014ee027b4e6c0d7f2a37ee7636137e.nq.gz
│   ├── 3bbbc1ee92562e6a2eebfc6a366f4309d06c7d54.nq.gz
│   ├── 4e66afb22d873ff0e853885b2037ffe99de3b4fc.nq.gz
│   ├── 51e4a733d2ec06da544b905651a738cd33eab79a.nq.gz
│   ├── 9b179a3bafb5e1d49e1a34585738b0f357ad8655.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── f13f15ed536a9118a2086f0c47465172a69bff36.nq.gz
│   ├── f1e0f37977b34790631b8b326ea94d48f2c07f3e.nq.gz
│   ├── f3c7e8e6ffb905f7de8b597eb22213a7dc20bfb3.nq.gz
│   └── f751a7591ba48ef31ab7e43826e1cdf9ba5bf34c.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 8247a02cc646048f32786e3b708be494ec730296.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 18 files
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

[pypa/python-manylinux-demo](https://github.com/pypa/python-manylinux-demo)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
