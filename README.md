# Repolex Knowledge Graph of tortoise/aiosqlite

RDF knowledge graph data for [tortoise/aiosqlite](https://github.com/tortoise/aiosqlite), parsed by [repolex](https://repolex.ai).

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
rlex download tortoise/aiosqlite
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── ed1861fe6f8baebcd83dd90653fa486f1e0cf44d
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── ed1861fe6f8baebcd83dd90653fa486f1e0cf44d
│           └── chunk-001.nq.gz
├── blob
│   ├── 14b776d9ea10a0afc6e4b9275509d0818c451abf.nq.gz
│   ├── 16fd54dabf314a0bedf3ab782a1bf05e358a592c.nq.gz
│   ├── 1bf3d737f356acbe76535678a0c46384f90cfcfc.nq.gz
│   ├── 241ad2fcbd3c4aa2ee96edf54f358bfad2d9e054.nq.gz
│   ├── 2a343d0f96040d5165e8d88db1c0771020209586.nq.gz
│   ├── 406e511e2d211efb5e1cf5bb10f3e20f6a913a01.nq.gz
│   ├── 50354f923f7defedc53781c1e03fa0355523d655.nq.gz
│   ├── 5cc32a20eb75d8eab3e2c85fd261e5283588aa32.nq.gz
│   ├── 60db6a10cd77c05a1c9f8447e2c6f261a892162b.nq.gz
│   ├── 64ad321dfff2eb592df2776b35a1cf9131f44f1c.nq.gz
│   ├── 69ef9cc6605fcdb02b61b8a7b03bba169a864393.nq.gz
│   ├── 755e0cfb08a700c48b8a312d811e01aa514e4989.nq.gz
│   ├── 7fe1d4c784c371abd2161c81f9f0c26b93acbc13.nq.gz
│   ├── 8190c8c1ce6bd37395d20174e64dcc673933492e.nq.gz
│   ├── a32938f602dfce1fb23f288fb3ae593200b512cf.nq.gz
│   ├── d5b8cae284f4d0c88e5f730307c706a6210afa7e.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── fb5833364e9650910981aa35e24c84363b0074d8.nq.gz
│   ├── fbb796ede7f7d36fb72dca80d873780b904d0d25.nq.gz
│   └── fbe41ad0428d792498d1d6aa1ed55238a5548f74.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── ed1861fe6f8baebcd83dd90653fa486f1e0cf44d.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 26 files
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

[tortoise/aiosqlite](https://github.com/tortoise/aiosqlite)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
