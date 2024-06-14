# LangChain

## Install

```bash
npm install langchain
```

## Chroma (vector database)

### 1. Install

```bash
pip install chromadb
```

### 2. Run server

```bash
chroma run
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
