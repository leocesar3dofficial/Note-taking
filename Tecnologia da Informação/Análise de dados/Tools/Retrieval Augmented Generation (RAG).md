# Retrieval Augmented Generation (RAG)

## LangChain

### Install

```bash
npm install langchain
```

## Chroma (vector database)

### 1. Install

```bash
# Python
pip install chromadb

# Javascript
npm install --save chromadb chromadb-default-embed

```

### 2. Run server

```bash
chroma run

# or
chroma run --host localhost --port 8000 --path ./my_chromadb_data
```

### 3. Create a collection

```bash
curl -X POST "http://localhost:8000/api/v1/collections" \
-H "Content-Type: application/json" \
-d '{
      "name": "my_collection",
      "description": "This is my collection",
      "metadata": {
          "key1": "value1",
          "key2": "value2"
      }
    }'
```

### 4. List collections

```bash
curl -X GET "http://localhost:8000/api/v1/collections"
```

### 5. Delete a collection

```bash
curl -X DELETE "http://localhost:8000/api/v1/collections/my_collection"
```

### 6 Create a Chroma client in Javascript

```javascript
import { ChromaClient } from 'chromadb'
const client = new ChromaClient();

// switch `createCollection` to `getOrCreateCollection` to avoid creating a new collection every time
const collection = await client.getOrCreateCollection({
    name: "my_collection",
});

// switch `add` to `upsert` to avoid adding the same documents every time
await collection.upsert({
    documents: [
        "This is a document about pineapple",
        "This is a document about oranges"
    ],
    ids: ["id1", "id2"],
});

const results = await collection.query({
    queryTexts: ["This is a query document about florida"], // Chroma will embed this for you
    nResults: 2, // how many results to return
});

console.log(results)
```