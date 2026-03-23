# LightRAG Knowledge Graph Explorer

A beautiful, interactive force-directed graph explorer for [LightRAG](https://github.com/HKUDS/LightRAG) knowledge graphs. Visualize entities and relationships extracted by LightRAG's RAG pipeline.

## Features

- **Force-directed graph** with D3.js — nodes sized by connection degree, colored by entity type
- **Multiple input formats**: KnowledgeGraph JSON (REST API), custom_kg JSON, GraphML, simple nodes+edges JSON
- **Interactive exploration**: hover to highlight connections, click for detail panel, drag to rearrange
- **Entity type filters**: filter by person, organization, concept, method, etc.
- **Search**: find entities by name with real-time highlighting
- **Detail panel**: view entity descriptions, connections, and metadata
- **Drag & drop**: drop a LightRAG graph file directly onto the page
- **Export**: save the current view as PNG
- **Demo data**: built-in LightRAG ecosystem knowledge graph for demonstration

## Supported Formats

| Format | Description |
|--------|-------------|
| **KnowledgeGraph JSON** | Output from LightRAG's `/graphs` REST API endpoint |
| **custom_kg JSON** | The `entities` + `relationships` format from `insert_custom_kg.py` |
| **GraphML** | NetworkX-generated `.graphml` files from LightRAG's default storage |
| **Simple JSON** | Any `{ nodes: [...], edges: [...] }` with `id`, `type`, `description` fields |

## Usage

Open `index.html` in any modern browser. No build tools, no dependencies beyond D3.js (loaded from CDN).

1. Click **Demo** to see a sample knowledge graph
2. Click **Load File** or drag a `.json`/`.graphml` file to visualize your own LightRAG graph
3. Click **Paste Data** to paste raw JSON or GraphML

### Keyboard Shortcuts

| Key | Action |
|-----|--------|
| `/` | Focus search |
| `Esc` | Clear search / close panels |

## LightRAG Graph File Location

LightRAG stores its knowledge graph at:
```
{working_dir}/{workspace}/graph_chunk_entity_relation.graphml
```

You can also export via the REST API:
```bash
curl http://localhost:9621/graphs?label=YourEntity&max_depth=3
```

## License

MIT
