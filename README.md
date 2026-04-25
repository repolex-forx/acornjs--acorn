# Repolex Knowledge Graph of acornjs/acorn

RDF knowledge graph data for [acornjs/acorn](https://github.com/acornjs/acorn), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [lexq](https://github.com/repolex-ai/lexq) query tool using [uv](https://docs.astral.sh/uv/getting-started/installation/).

If you have uv installed, just copy/paste this into your terminal:

```bash
uv tool install git+https://github.com/repolex-ai/lexq
```

This installs lexq onto your system, in your user context. Verify the install:

```bash
lexq --help
```

**lexq is designed to be used primarily by LLMs in a terminal.** Start up your favorite LLM and ask it to use the lexq tool. It's that easy!

To load this repo's data:

```bash
lexq download acornjs/acorn
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── c108741d0796be08592dc9b1493c740be9ff804a
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── c108741d0796be08592dc9b1493c740be9ff804a.nq.gz
│   └── repolex
│       └── c108741d0796be08592dc9b1493c740be9ff804a
│           └── chunk-001.nq.gz
├── blob
│   ├── 04cc7ecb8a689250f255f9ca5ad6363368921e0e.nq.gz
│   ├── 282b13325f1250a6301bcd640370c980738b5b3e.nq.gz
│   ├── 3916e96b2dd2b96c863f9cd8e9709109f67512ed.nq.gz
│   ├── 41c09018a459404f6856a2f8c463bfb0308593b8.nq.gz
│   ├── 492805dc2ea2c3cc6857fc16467d56b814b658c7.nq.gz
│   ├── 4c4dab9d03a23bacaa506e1e2241052f61e30745.nq.gz
│   ├── 59277d5533e0d68497a0a43ae15ae43b54e5b275.nq.gz
│   ├── 5bb27bbf9db1e1d5043ca44015b5d8c6049864a7.nq.gz
│   ├── 7048e91b5f79e7f55f28f60d237c89176da8abbd.nq.gz
│   ├── 729550cbde53e0967ca4dcbd4551bffc18615dd8.nq.gz
│   ├── 97a4dd036ed65085c174c4ceb82e0a5f379fabe9.nq.gz
│   ├── b22fdeb5304020d8da08fbbc6c48b850b7e4c990.nq.gz
│   ├── f01f5d3c5322ffd4672708f5d779ade53abdf09c.nq.gz
│   ├── f02305edfb20c8b3cc891b8abaab8793680292ef.nq.gz
│   ├── f75aa1a521b061a8565eb0dac3b855009b78b798.nq.gz
│   └── ff6eb889d80454651e46009d88d8a4095254cc33.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── c108741d0796be08592dc9b1493c740be9ff804a.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

14 directories, 25 files
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

## Source repository

[acornjs/acorn](https://github.com/acornjs/acorn)

---
*Parsed on 2026-04-25 by [repolex](https://repolex.ai)*
