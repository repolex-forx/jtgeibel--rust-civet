# Repolex Knowledge Graph of jtgeibel/rust-civet

RDF knowledge graph data for [jtgeibel/rust-civet](https://github.com/jtgeibel/rust-civet), parsed by [repolex](https://repolex.ai).

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
rlex download jtgeibel/rust-civet
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 68ca95e5a5c9f4c9cca8be9ae36edf27839b0db0
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 68ca95e5a5c9f4c9cca8be9ae36edf27839b0db0.nq.gz
│   └── repolex
│       └── 68ca95e5a5c9f4c9cca8be9ae36edf27839b0db0
│           └── chunk-001.nq.gz
├── blob
│   ├── 006fecc3e8aa608413684b3e3771df6dc5796c95.nq.gz
│   ├── 0827869afc4ff88a3aa9007a1d750f31db4ce0cd.nq.gz
│   ├── 1f7cf282765ffcb2099dbd7971251d492d5d60c2.nq.gz
│   ├── 2f4a06b8f3e55c2adf2a085b11b8ad9c2730a5fb.nq.gz
│   ├── 4e65fdc66d2c02ff849a4e4183117d6ba6ae8ae4.nq.gz
│   ├── 6b6d88b61f1c2f1e74e0d3e96d0f1ca69493b15a.nq.gz
│   ├── 9fed966372eb587ae93f0dea6dd4b5dd3cbb022e.nq.gz
│   ├── a93251b65da98b83862bc07ad0c89138639b58a5.nq.gz
│   ├── a9d37c560c6ab8d4afbf47eda643e8c42e857716.nq.gz
│   ├── b54f24e4afc3383d30dcfb3199294e3dfcb04981.nq.gz
│   ├── c8556d00d20bb856b1f017c6480e0d7eebdac333.nq.gz
│   ├── cb3817114093b0ee6f1f6b533b485d732ad910e8.nq.gz
│   ├── cf767cb7bc062e5d2b2ea0f9e3864d3d8055c5cf.nq.gz
│   └── d6c4f0149487a4800fd7c394ae4287b2ff0d586a.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 68ca95e5a5c9f4c9cca8be9ae36edf27839b0db0.nq.gz
├── filetree
│   └── 68ca95e5a5c9f4c9cca8be9ae36edf27839b0db0.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 22 files
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

[jtgeibel/rust-civet](https://github.com/jtgeibel/rust-civet)

---
*Parsed on 2026-11-21 by [repolex](https://repolex.ai)*
