# Repolex Knowledge Graph of sdispater/lampwick

RDF knowledge graph data for [sdispater/lampwick](https://github.com/sdispater/lampwick), parsed by [repolex](https://repolex.ai).

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
rlex download sdispater/lampwick
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── af8e85390a3e0e3a6c3429d9e526d3bce10d3757
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── af8e85390a3e0e3a6c3429d9e526d3bce10d3757
│           └── chunk-001.nq.gz
├── blob
│   ├── 0c738421d6a41dc32ab049a68f3d3f781a67b3d2.nq.gz
│   ├── 333f7411ea7c5a7d1c449b1e6c778d69fe1ce809.nq.gz
│   ├── 3c5fe4698a4df1aabacb7abe04f83ea1ae15a8c8.nq.gz
│   ├── 3f0aed7fa14a255a93863e9a9ab9bfbf57c1aeca.nq.gz
│   ├── 4cbfa391382deb446bf477a53b24744a4e3ed2cc.nq.gz
│   ├── 633f866158ac742cf754a2c43edcb07e3a094f3c.nq.gz
│   ├── 7a8479f7c7741738da4915d9137bf6cd118ae55b.nq.gz
│   ├── 7cb9ea84d67ddd66e4389d21e64c61eed6d1f091.nq.gz
│   ├── 82b875aeed6ec7b8cde5d4a3975b34a7776e69d1.nq.gz
│   ├── 9a14d115075c823ec8eb0d9fb6353c1dac181db7.nq.gz
│   ├── a4667261c40786c2bc1106618ec1f4b92c236935.nq.gz
│   ├── a8888ec749499d3af81bf4cc6b618e88d4cdce7e.nq.gz
│   ├── d2c2a963644324cc9b046ae7ba9688cf5f61d7cb.nq.gz
│   └── d3ad332e56d30633b64af0af6da01854f5b61f2f.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── af8e85390a3e0e3a6c3429d9e526d3bce10d3757.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 20 files
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

[sdispater/lampwick](https://github.com/sdispater/lampwick)

---
*Parsed on 2026-10-28 by [repolex](https://repolex.ai)*
