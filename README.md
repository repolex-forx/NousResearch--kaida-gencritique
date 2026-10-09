# Repolex Knowledge Graph of NousResearch/kaida-gencritique

RDF knowledge graph data for [NousResearch/kaida-gencritique](https://github.com/NousResearch/kaida-gencritique), parsed by [repolex](https://repolex.ai).

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
rlex download NousResearch/kaida-gencritique
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 98d7e9b4e32172cfba350cef8fd465f681ff0003
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 98d7e9b4e32172cfba350cef8fd465f681ff0003
│           └── chunk-001.nq.gz
├── blob
│   ├── 0017ff3a13022052b4f81d72748da7616afe3870.nq.gz
│   ├── 0c9525098149bdec5a28da7d5473853c1507a6fa.nq.gz
│   ├── 1278fe7b55d09e3ec4cee09dca993e2815e7301e.nq.gz
│   ├── 179b3dac8e0521a93e6ea198df045608edd198b1.nq.gz
│   ├── 17de371548fb03b3fa33670e577c33371358b28c.nq.gz
│   ├── 1b6c787337ffb79f0e3cf8b1e9f00f680a959de1.nq.gz
│   ├── 1c2fda565b94d0f2b94cb65ba7cca866e7a25478.nq.gz
│   ├── 202ff96d1494b084a9a81b80e1145e4f1be97f10.nq.gz
│   ├── 249e5832f090a2944b7473328c07c9755baa3196.nq.gz
│   ├── 413b40c4b8a899b90964855287228c489ff74de2.nq.gz
│   ├── 4b823b5ee9d03be124c97f65611e0b3d0367f99b.nq.gz
│   ├── 7723d5ccc921cb1a58f41f506b4841e60684f2a0.nq.gz
│   ├── 7fc6f1ff272ee12d8be9694acdaa36b4284eefdb.nq.gz
│   ├── 8527f20b801771d7479a31475f62530dd41b2f8f.nq.gz
│   ├── 8ca3a5154009c955b6fe7b9bd50915cd118cb41f.nq.gz
│   ├── 9c9784eec8b8e899844e8025401626548fb9427a.nq.gz
│   ├── ac1b06f93825db68fb0c0b5150917f340eaa5d02.nq.gz
│   ├── b668cdbb815a097bc9a6379bf4d2ecd432103583.nq.gz
│   ├── bd145fb179515eb2ed6e442713c9bc904d877ec9.nq.gz
│   ├── bd68789be32131939ee329a5f3658653aeafa2f0.nq.gz
│   ├── bde2df33484582801593054402b83aeb561f7681.nq.gz
│   ├── c6214f2b89a7fddf6183a8c378210dc73aa01f3d.nq.gz
│   ├── df4bcc2e8df0c9c754a9858b1fb6d377e581bf95.nq.gz
│   ├── eb0a1049b21cd18209afa5cbf8fd74c1b7f238ce.nq.gz
│   ├── f1fd2cd592d4ea23e5c8c4aae6ed7b0a1ace8974.nq.gz
│   ├── f39c3c653ce9fd81ee4191e43394e958418ce113.nq.gz
│   ├── f5f8d23827e43faf033549ebbacc27a87f6cf9ba.nq.gz
│   └── f70795c54b5afd432d051dbf8fd1969fde5c9ea8.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 98d7e9b4e32172cfba350cef8fd465f681ff0003.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 34 files
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

[NousResearch/kaida-gencritique](https://github.com/NousResearch/kaida-gencritique)

---
*Parsed on 2026-10-09 by [repolex](https://repolex.ai)*
