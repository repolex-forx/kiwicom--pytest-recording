# Repolex Knowledge Graph of kiwicom/pytest-recording

RDF knowledge graph data for [kiwicom/pytest-recording](https://github.com/kiwicom/pytest-recording), parsed by [repolex](https://repolex.ai).

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
rlex download kiwicom/pytest-recording
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 243e582d5502ebaac90ada5c903fe6f26f7dbbbc
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 243e582d5502ebaac90ada5c903fe6f26f7dbbbc
│           └── chunk-001.nq.gz
├── blob
│   ├── 0012b836da239a6005ebff1057208a61c17e17b0.nq.gz
│   ├── 001b9d8403edcc9dc8bc9008fab3ce764a2a9850.nq.gz
│   ├── 13b920d5a77ef3154ccfa2a08223d1c72d1f48bc.nq.gz
│   ├── 1f6e21f184dca1462c54190e5681adf821c6af9b.nq.gz
│   ├── 234073c856fc3c14ef709a3265933826428beb05.nq.gz
│   ├── 29ae719de53535ba0095c2d1758c6a470e843bdb.nq.gz
│   ├── 307fddee6cba5d27bd4661cdf8b8e5e415454004.nq.gz
│   ├── 39a2b6e9a55b8aaa96d0ee0e1c8f956c5c662e75.nq.gz
│   ├── 414e5f28dc8ace60e457229e58a28c1f695befe3.nq.gz
│   ├── 42ec63f6c9f2c35be764c44381c0548aa1b4edd9.nq.gz
│   ├── 471dbaac8221ea684de8b61bd7fd99bd3f4b8946.nq.gz
│   ├── 4d0633ff6da3f9f36ecf44dd4519aec087feba47.nq.gz
│   ├── 524ca96807df052f8dc9018b50439a84ec8ae3f1.nq.gz
│   ├── 548be9b5c5a60bf4ba8e48acecede4c44c14392e.nq.gz
│   ├── 561fd5538896e8d01bb0c5de7acdf961dee4dfae.nq.gz
│   ├── 5e951079b7cc2307e5e268218f4e2bb7bf699045.nq.gz
│   ├── 65918f4972db468682f21b572651ecaf860f3175.nq.gz
│   ├── 725e2bf61a6ca8591ff1aecbbd3d7868c900e54d.nq.gz
│   ├── 763f8371340e523e52ac8a80fc32287015526e82.nq.gz
│   ├── 8eca63cf5689e6eb90212ae48f84fa5751a8a51a.nq.gz
│   ├── 9312f9c6852406b00fb06e957c7bec5df66d6ee8.nq.gz
│   ├── 9a4c915fdf61299a6f393efdfb4344fbb833074b.nq.gz
│   ├── b2a41c6b0ad6d0f2718ea5f9de0e1ed7136cf9f7.nq.gz
│   ├── b67109f95fa3882203e2ac52c05b7cbc3ee90e4f.nq.gz
│   ├── c44fb2d809e3e628869303f96d5d8be3a558bd8d.nq.gz
│   ├── c796a2a64a67214528b81147853b0f44f62a94ec.nq.gz
│   ├── dfd289fa8fb7efc523477afbafe7d2482cefaba5.nq.gz
│   ├── e4a4e7c2c6bc1fa5f7a3fe5d5c55ba031f426508.nq.gz
│   ├── e520cd5538bee1d9e378261f0bd357d46abd7b53.nq.gz
│   ├── e5fe64afa6648529b0fac5fc4606b7a947ffe3b1.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e899beaa7f2a3c09f96a4cfd30c64c0bab09f13e.nq.gz
│   ├── ed07ccb6a228406ee0910ef6aa3e08fbc6e7974d.nq.gz
│   ├── edfb6985302981eb81027cb912d32b2262fa34fc.nq.gz
│   ├── f3549f8a1df72502d984e573cf3ea98d3b1aaa72.nq.gz
│   ├── f7590f0d7d05ed3b36291fedc29007cba044a3c1.nq.gz
│   └── fa2680495307ffbea4f02443ea7d109f2ecb6efa.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 243e582d5502ebaac90ada5c903fe6f26f7dbbbc.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 45 files
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

[kiwicom/pytest-recording](https://github.com/kiwicom/pytest-recording)

---
*Parsed on 2026-10-18 by [repolex](https://repolex.ai)*
