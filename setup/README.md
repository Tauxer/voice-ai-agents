# Setup

Builds the Qdrant knowledge base used by the voice agent: chunks the markdown
documents in `data/` and loads them into a Qdrant collection.

## Requirements

- Python 3.11
- conda (or another virtualenv tool)

## Environment

```bash
conda create -n vo311 python=3.11
conda activate vo311
pip install -r requirements.txt
```

Copy `.env.example` to `.env` and fill in the values:

```bash
cp .env.example .env
```

| Variable | Description |
| --- | --- |
| `OPENAI_API_KEY` | OpenAI API key |
| `QDRANT_URL` | Qdrant instance URL |
| `QDRANT_KEY` | Qdrant API key |
| `QDRANT_COLLECTION_NAME` | Name of the collection to create/populate |

## Usage

Run `qdrant-db.ipynb` end to end to chunk the documents in `data/` and upsert
them into the Qdrant collection.

`database.sql` contains the relational schema used alongside the vector
store.
