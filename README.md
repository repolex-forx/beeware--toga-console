# Repolex Knowledge Graph of beeware/toga-console

RDF knowledge graph data for [beeware/toga-console](https://github.com/beeware/toga-console), parsed by [repolex](https://repolex.ai).

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
rlex download beeware/toga-console
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── d2cdd49ff8a7f49738c7f3d749c53ca2a8df46a8
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── d2cdd49ff8a7f49738c7f3d749c53ca2a8df46a8
│           └── chunk-001.nq.gz
├── blob
│   ├── 04b4603c9f90a65a2f18a2533262b8e4592fa334.nq.gz
│   ├── 260ae8939294cf7b1d67248711ee1460f7910ece.nq.gz
│   ├── 2b2ecf09ef240e666d123937518b60c7392faad7.nq.gz
│   ├── 3260e9e08104ad83074fb6dea3e38a9094f75924.nq.gz
│   ├── 381bbda87debd272f19babb8267681cb792ea273.nq.gz
│   ├── 38eae71bcaf1d1265931847f7d964e28ba3782ea.nq.gz
│   ├── 48d36885be3835fc37b083ad21eefec10f0a6ce4.nq.gz
│   ├── 4a09c81e23ca735b7d235c71f9ed7feca8081af3.nq.gz
│   ├── 5b065bee2e496e3c5175856534980cdb7f9d8e79.nq.gz
│   ├── 5e5a15114a83a47fca1c332b8dddb35baa50cc5f.nq.gz
│   ├── 60632cd6286a6c049c1cc7b289e053154b00584f.nq.gz
│   ├── 606e5970fdc32ba7366b86165bea5e7ba72a9a1b.nq.gz
│   ├── 61b70af6f9a8a7ff1c646966d5761f438ed1daba.nq.gz
│   ├── 6234b0f06ce50951d6971801af698b7babe59399.nq.gz
│   ├── 6689317402a9f4b9d200523518790e89a9ae5b3b.nq.gz
│   ├── 6c4c99c7234d720005af77df91e5ad5e81fb0cfc.nq.gz
│   ├── 7c1f5d3c61b4fb4f2e4d34d408256f39317ae5bc.nq.gz
│   ├── 7c23dde4da4211c0c109da688e2377b38dc8e3ff.nq.gz
│   ├── 7d6b8b61969a683db59bb045a542e8f0b15087a4.nq.gz
│   ├── 819433657150aac87e7b599b1a0a2a564af1161d.nq.gz
│   ├── 85b9269631ae91558dedfb932f9cdf7702efa180.nq.gz
│   ├── 8e6c477126cec711db73f262c00d7a3bc787f390.nq.gz
│   ├── a1401f80392dc27983415429c6d061e7447c2a2a.nq.gz
│   ├── aa1886a880a071d0eb6cd93cea0f92f0a10ada4a.nq.gz
│   ├── acf0beae91a9f4b519706933deba7bbd8160db94.nq.gz
│   ├── b13237988ace1634cc8b858ebf75df65660de235.nq.gz
│   ├── b834affdddcf5014398ca9c16aafe3ea7f2d0422.nq.gz
│   ├── bb82b470bf4f145b82060b9e71d85e1b78410b49.nq.gz
│   ├── bdd995ecf26ae17f6cd99006964f5b77881933a0.nq.gz
│   ├── c4d88e8173e484996f9c1fe716bd0fb7e4c8a73b.nq.gz
│   ├── ca8d8c460a6aed377b3bb9a0e21b816c6be9bdfe.nq.gz
│   ├── d8a98d2e22375766b0b1b92342cf6edeba756082.nq.gz
│   ├── ddc676aaf5218daaf94e0539a09e99b5f6664123.nq.gz
│   ├── e2f95a10133754106d1672a544eee02de6870b01.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── f59ec3776c8a2533b077eb8bedf0685959475dab.nq.gz
│   └── fbd47e37e73b287ac01cb088ec42862c3890cad7.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── d2cdd49ff8a7f49738c7f3d749c53ca2a8df46a8.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 44 files
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

[beeware/toga-console](https://github.com/beeware/toga-console)

---
*Parsed on 2026-11-07 by [repolex](https://repolex.ai)*
