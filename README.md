# Torch & Lily — Open Data

> *A digital archive of the Catholic intellectual tradition, freely available.*

This repository contains curated, machine-readable datasets exported from
the **[Torch & Lily](https://torchandlily.com)** project — an API-first platform
that provides structured access to Scripture, the Summa Theologiae, patristic
commentaries, catechisms, the lives of the saints, Catholic prayers, and more.

Whether you are a researcher, developer, educator, or simply curious, these
datasets are here for you to explore, build upon, and learn from.

**Last updated:** 2026-03-25 20:48 UTC  
**Total records:** 88,683

---

## Datasets

### Scripture & Theology (Veritas)

| File | Description | Records |
|---|---|---|
| `works.json.gz` | Catalog of theological works (Summa, commentaries, catechisms, etc.). | 18 |
| `bible_books.json.gz` | Books of the Bible with English and Latin names. | 73 |
| `bible_verses.json.gz` | Bible verses in English and Latin (Douay-Rheims / Vulgate). | 37,639 |
| `bible_commentaries.json.gz` | Patristic and medieval Bible commentaries keyed by book/chapter/verse. | 12,262 |
| `summa_parts.json.gz` | Top-level divisions of the Summa Theologiae (Prima Pars, etc.). | 5 |
| `summa_questions.json.gz` | Questions of the Summa Theologiae grouped by part. | 611 |
| `summa_articles.json.gz` | Articles of the Summa Theologiae — objections, sed contra, respondeo, replies. | 3,076 |
| `citations.json.gz` | Cross-references and citations between texts. | 8,093 |
| `capitula_part1.json.gz` | Chapters and sections from the Summa Theologiae and other Opera. (part 1/2) | 10,362 |
| `capitula_part2.json.gz` | Chapters and sections from the Summa Theologiae and other Opera. (part 2/2) | 10,360 |
| `catechism_versions.json.gz` | Catechism editions (e.g. Baltimore Catechism No. 1–3). | 3 |
| `catechism_lessons.json.gz` | Catechism lessons grouped by version. | 82 |
| `catechism_questions.json.gz` | Catechism questions and answers. | 1,721 |

### Saints & Devotion (Devotio)

| File | Description | Records |
|---|---|---|
| `saints.json.gz` | Catholic saints — verified (NIHIL_OBSTAT) records only. | 648 |
| `saint_relationships.json.gz` | Relationships between saints (teacher/student, founder, etc.). | 3,630 |
| `prayers.json.gz` | Catholic prayers with Latin and English text. | 100 |

---

## Format

All data files are **gzipped JSON** (`.json.gz`) in the `data/` directory.
Large datasets may be split into numbered parts (`_part1`, `_part2`, etc.).

```bash
# Decompress a file
gunzip data/saints.json.gz
```

```python
# Read directly in Python
import gzip, json

with gzip.open('data/saints.json.gz', 'rt') as f:
    saints = json.load(f)

print(f"Loaded {len(saints)} saints")
```

```javascript
// Read in Node.js
const { readFileSync } = require('fs');
const { gunzipSync } = require('zlib');

const raw = gunzipSync(readFileSync('data/saints.json.gz'));
const saints = JSON.parse(raw.toString());
```

---

## About Torch & Lily

**[Torch & Lily](https://torchandlily.com)** is an open, API-first platform
dedicated to making the Catholic intellectual tradition accessible to developers,
researchers, and AI agents alike.

- **The Torch** — A REST API serving structured data from the Summa Theologiae,
  the Douay-Rheims Bible, patristic commentaries, catechisms, saints, prayers,
  the liturgical calendar, and a sacred sites directory.
- **The Lily** — A family of frontend experiences built on the Torch API,
  including a developer portal, documentation, and community tools.

### Links

| Resource | URL |
|---|---|
| Website & Docs | [torchandlily.com](https://torchandlily.com) |
| API Base URL | `https://api.torchandlily.com/v1` |
| API Documentation | [torchandlily.com/docs](https://torchandlily.com/docs) |
| MCP Server (for AI agents) | [torchandlily.com/docs/docs/mcp](https://torchandlily.com/docs/docs/mcp) |
| Get an API Key | [torchandlily.com/signup](https://torchandlily.com/signup) |

### Want more than static files?

The Torch API provides full-text search, cross-references between texts,
liturgical calendar lookups, geographic queries, and more — things a flat
data dump can't offer. [Sign up for a free API key](https://torchandlily.com/signup)
to get started.

For AI agents and LLM-powered applications, Torch also exposes an
[MCP server](https://torchandlily.com/docs/docs/mcp) for direct tool-use integration.

---

## License

These datasets are provided freely for **educational, research, and devotional use**.
The underlying source texts (Scripture, the Summa, catechisms, etc.) are in the
public domain. Saint biographies and structured metadata were compiled by the
Torch & Lily project.

If you use this data in a project, a link back to
[torchandlily.com](https://torchandlily.com) is appreciated but not required.

---

*This repository is updated automatically. For questions or feedback, visit [torchandlily.com](https://torchandlily.com).*
