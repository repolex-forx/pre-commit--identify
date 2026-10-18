# Repolex Knowledge Graph of pre-commit/identify

RDF knowledge graph data for [pre-commit/identify](https://github.com/pre-commit/identify), parsed by [repolex](https://repolex.ai).

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
rlex download pre-commit/identify
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 28ae3106d2979b86ce674940d44c07e1dbed1a89
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 28ae3106d2979b86ce674940d44c07e1dbed1a89
│           └── chunk-001.nq.gz
├── blob
│   ├── 0279ba8e404de57dec05dede61650db6dadda9a1.nq.gz
│   ├── 093ce8902c0bb1872d724f196ce0d4c65f7d4510.nq.gz
│   ├── 0c5a37eb0adeb312718e533d0a4fbcbea6880056.nq.gz
│   ├── 0c954cf0c347ee9a74c13f27379faa8b24ae5c54.nq.gz
│   ├── 0e96bcaafc4e479f239e6c75a11c6969ac87c6d6.nq.gz
│   ├── 0ecc5db911dadf39c600843c4646aa2b5c3a0ed7.nq.gz
│   ├── 13a006a1c75d60b189afb4195b2a1895e0295de8.nq.gz
│   ├── 3d93aefb2da505dba9c0114404cfaaeee5ad0d3f.nq.gz
│   ├── 4a13a7e2a3d3fc7bbff2ae18956fcdcf80fad8ba.nq.gz
│   ├── 98c77bd6abde74c53c058bd5bfa9bec248d005b9.nq.gz
│   ├── a15a8d1a4edb8c68a20a8a1488529cd69b42f385.nq.gz
│   ├── a82f353c215f58bea346c8d325789a1bd19faca5.nq.gz
│   ├── ba21e2e4a91ffd59e81e621af730f9d9b3b997d4.nq.gz
│   ├── c98afe271a796c1903bf4ecc9ac255b183d1dde4.nq.gz
│   ├── d1898d740482ed6fa70fa1ecde625f1d79dec0a3.nq.gz
│   ├── d7fb3cd9e8526784efa40023ea0cb6ffab28d2ec.nq.gz
│   ├── e0b563328c42cc8ebe7ae3a948140ae25a4422cf.nq.gz
│   ├── e3c45e369338e3a2eb1ed011e48db4bdc4643094.nq.gz
│   └── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 28ae3106d2979b86ce674940d44c07e1dbed1a89.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 27 files
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

[pre-commit/identify](https://github.com/pre-commit/identify)

---
*Parsed on 2026-10-18 by [repolex](https://repolex.ai)*
