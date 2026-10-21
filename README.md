# Repolex Knowledge Graph of ibis-project/ibis-examples

RDF knowledge graph data for [ibis-project/ibis-examples](https://github.com/ibis-project/ibis-examples), parsed by [repolex](https://repolex.ai).

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
rlex download ibis-project/ibis-examples
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 0b4cbc3f74c7e2f617f1d107246e22cfb9227833
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 0b4cbc3f74c7e2f617f1d107246e22cfb9227833
│           └── chunk-001.nq.gz
├── blob
│   ├── 048ce046aabb97313644c709fb5ee2dbd91d7698.nq.gz
│   ├── 0c78790baeb1a591a8bef912924e7b30db2c93df.nq.gz
│   ├── 16e3705b92c25f40bfaeecd52353838b1ef7e47d.nq.gz
│   ├── 16e928d8c6ce5946b35818de65d58b3e40cef17f.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 293b283b42b35c0190f3ea797ad74dda2fe5d83a.nq.gz
│   ├── 2c010d2132a2acd4fa4d04b3eb9e5429c36ac9a3.nq.gz
│   ├── 2f4f91ca8fae36e4dcb9bb9274f3afbabaf1413c.nq.gz
│   ├── 39372d5927fafb3b06dfca1e5e80228a28d82c0f.nq.gz
│   ├── 4c88fa0a7d191ad61a6f76e2082d0325b09c0e40.nq.gz
│   ├── 4f3a0b38121b4cfcf8c21fd3f646274f044fef86.nq.gz
│   ├── 5428449433c427602a65fe92d5209231fb23b229.nq.gz
│   ├── 58092e2ba87bacb2833a0bdc23c19d7929044da7.nq.gz
│   ├── 73be78637e8ce940e6d53c652a988dd214db9212.nq.gz
│   ├── 75024a7c37017b4cd830060c5262d0730ec32971.nq.gz
│   ├── 8130a91c65e64529fa7ecc7cd33b961a597e209a.nq.gz
│   ├── 8174df76f416b328f7fe2746dc6de9c26ce59d74.nq.gz
│   ├── 88aba0a56ef8e67bc83de190ac1176a4d8647def.nq.gz
│   ├── a39a1f35ff376c4b66868db670481d5f4477e885.nq.gz
│   ├── b01b751839b021dc25c50a04d5c7c112033b21a7.nq.gz
│   ├── d01e7f9a1bc198fbd24134005bf658a8a0354f64.nq.gz
│   ├── d111c9641dad9024bed32459915ddd8322063fee.nq.gz
│   ├── e642e6caaad1ed7ffadcbfba1a10a6efd97130f0.nq.gz
│   ├── e80689858ad90e9fda85083cf3b688028849ccb5.nq.gz
│   └── e8e16f5f2d495a64413eac37d6c4f77335420b01.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 0b4cbc3f74c7e2f617f1d107246e22cfb9227833.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 33 files
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

[ibis-project/ibis-examples](https://github.com/ibis-project/ibis-examples)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
