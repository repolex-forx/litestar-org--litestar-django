# Repolex Knowledge Graph of litestar-org/litestar-django

RDF knowledge graph data for [litestar-org/litestar-django](https://github.com/litestar-org/litestar-django), parsed by [repolex](https://repolex.ai).

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
rlex download litestar-org/litestar-django
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── a66be68559f23a2ff5227ad18ded3e1aa5e29b9e
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── a66be68559f23a2ff5227ad18ded3e1aa5e29b9e
│           └── chunk-001.nq.gz
├── blob
│   ├── 05805d91d443d7a3ba1fe44ba77bdbee8ed716a3.nq.gz
│   ├── 24ee5b1be9961e38a503c8e764b7385dbb6ba124.nq.gz
│   ├── 2ea1c29ead80d50ab90af4e58adc08d7408fc1a0.nq.gz
│   ├── 3ab183228d5e144ca70ea23ce350973bfdc07dcc.nq.gz
│   ├── 412bf43361976cef7a95458d16fcf56d5f379dac.nq.gz
│   ├── 4ea871865914e860289092f1a6023676792654fd.nq.gz
│   ├── 51b15d0a6827446fe6abc8008046a084c92d6ae2.nq.gz
│   ├── 5bf68d82459f3edb0902c3fe706b749700097a43.nq.gz
│   ├── 6c4bc5022b770adbf441516d84799e601bf30921.nq.gz
│   ├── 70ec33a7ca18eb4c2dc46b1cb459eb6e80102d33.nq.gz
│   ├── 91fc427a57fecc150f5967d8fecb63ce5aa5c086.nq.gz
│   ├── 94aa28ac651fff88d6d8f9d53c94d848485d717a.nq.gz
│   ├── 98fd6401af5a57febf7be2e8e56912fe7640298c.nq.gz
│   ├── 9b1cf1159f9d6b893b2686b1fb64bd2f9e57e8d7.nq.gz
│   ├── c34df6a9bb69dfa2e147c4cf17e076a02a7a1cc8.nq.gz
│   ├── ccb593bdd3cc9894d2488f15ae2ff141da494f8a.nq.gz
│   ├── cf53fceabae6d89fe79eadfea439e3bd9de158c5.nq.gz
│   ├── d18f3eae13cc3aac7d138d85bc3cf21c276fd0c2.nq.gz
│   ├── d1bdd3cedbbe2a8b83a3cf866381aac15dd05bb5.nq.gz
│   ├── d3549b8d1b76ab31617d213a2b39835d85583383.nq.gz
│   ├── dd1e67a718827b6ec38f49ee942e6bcd92ee65c1.nq.gz
│   └── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── a66be68559f23a2ff5227ad18ded3e1aa5e29b9e.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 29 files
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

[litestar-org/litestar-django](https://github.com/litestar-org/litestar-django)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
