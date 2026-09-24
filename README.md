# Repolex Knowledge Graph of repolex-ai/subtext-mcp

RDF knowledge graph data for [repolex-ai/subtext-mcp](https://github.com/repolex-ai/subtext-mcp), parsed by [repolex](https://repolex.ai).

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
lexq download repolex-ai/subtext-mcp
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 8a0801f35176710f17afb3b73951fbec629bcb7c
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 8a0801f35176710f17afb3b73951fbec629bcb7c.nq.gz
│   └── repolex
│       └── 8a0801f35176710f17afb3b73951fbec629bcb7c
│           └── chunk-001.nq.gz
├── blob
│   ├── 02c0d5299ad7f8269c308492b952af335a0e78cb.nq.gz
│   ├── 28f3a144b85cff308df0712c78a9c9bbf5defa25.nq.gz
│   ├── 30769f4b47d825f1194ea56fa00516d014125b8d.nq.gz
│   ├── 32e943d2c5beae26dac73d2d28311415698251f5.nq.gz
│   ├── 3cf3b69ac19ec4307293b52212c5789e6d30286d.nq.gz
│   ├── 4a9a9786f21e02e66843c673e64c3ed83756338c.nq.gz
│   ├── 4d269657d0d8d70744f08ced728f86adf1b01319.nq.gz
│   ├── 6d35014d1ec1095cc6848849b5f971c4e0cb9c15.nq.gz
│   ├── 84180c8b6ec23299cb16da3686e6279ec6da7044.nq.gz
│   ├── 99287473b1fd0154324dd5a66fd7d17aff29c09d.nq.gz
│   ├── a4ad718035d0cc88d2d48eb7b0f01a2a1f117f43.nq.gz
│   ├── bd63cf66f8b5b008abb20079d0032b58fc46ac16.nq.gz
│   ├── bf7fb876804eb5e880cca91836d5790759b2b110.nq.gz
│   ├── bfa0fead54e8070848b4572df2e14b62a86d570f.nq.gz
│   ├── e0c2d38f802711de0050871ba2150d5de21eae74.nq.gz
│   ├── e21f9b7d982e11936bf4598ebce554c8b1385cb3.nq.gz
│   ├── f302f93ad46d381bb510c8a42eb64cab2c6fc919.nq.gz
│   ├── f830fee6b1118884619237cc3502d899bdbdb5b8.nq.gz
│   ├── fb1130fb93f0ac2a4c75bc5e1d3162dc6c24a4df.nq.gz
│   ├── fda58d7c72094a6641de46725a44538a16b60581.nq.gz
│   └── fefe2738d638cf3940c520db1a1a27c940364c38.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 8a0801f35176710f17afb3b73951fbec629bcb7c.nq.gz
├── filetree
│   └── 8a0801f35176710f17afb3b73951fbec629bcb7c.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 31 files
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

[repolex-ai/subtext-mcp](https://github.com/repolex-ai/subtext-mcp)

---
*Parsed on 2026-09-24 by [repolex](https://repolex.ai)*
