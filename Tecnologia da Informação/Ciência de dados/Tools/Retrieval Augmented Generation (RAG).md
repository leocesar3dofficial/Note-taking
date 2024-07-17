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

# Javascript library
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
import { ChromaClient } from 'chromadb';
const client = new ChromaClient();

// switch `createCollection` to `getOrCreateCollection` to avoid creating a new collection every time
const collection = await client.getOrCreateCollection({
  name: 'my_collection',
});

// switch `add` to `upsert` to avoid adding the same documents every time
await collection.upsert({
  documents: [
    'This is a document about pineapple',
    'This is a document about oranges',
  ],
  ids: ['id1', 'id2'],
});

const results = await collection.query({
  queryTexts: ['This is a query document about florida'], // Chroma will embed this for you
  nResults: 2, // how many results to return
});

console.log(results);
```

## Ollama

### Install or update server

```bash
curl -fsSL https://ollama.com/install.sh | sh
```

### Basic CLI usage

```bash
# Download a model from Ollama project
ollama pull <name of the model>

# List the available models
ollama list

# Start prompting the model
ollama run <name of the model>

# Start or stop ollama service
systemctl start ollama
systemctl stop ollama

# List options
ollama help

# Multiline input
"""
Hello,
world!
"""

# Make questions based on local text file (txt or md files)
ollama run <model name> "Question: $(cat /home/user/Downloads/filename.txt)"

# Make questions based on a image using llava:7b (a vision model)
ollama run llava:7b
>>> What's in this image? /home/user/Downloads/filename.jpg
```

### Install Node library in project

```bash
npm install ollama
```

## Utility functions

### Text chunking

```bash
npm install @stdlib/nlp-sentencize
```

```javascript
import sentencize from '@stdlib/nlp-sentencize';

export function chunkTextBySentences(sourceText, sentencesPerChunk, overlap) {
  if (sentencesPerChunk < 2) {
    throw new Error('The number of sentences per chunk must be 2 or more.');
  }

  if (overlap < 0 || overlap >= sentencesPerChunk - 1) {
    throw new Error(
      'Overlap must be 0 or more and less than the number of sentences per chunk.'
    );
  }

  const sentences = sentencize(sourceText);

  if (!sentences) {
    console.log('Nothing to chunk');
    return [];
  }

  const chunks = [];
  let i = 0;

  while (i < sentences.length) {
    let end = Math.min(i + sentencesPerChunk, sentences.length);
    let chunk = sentences.slice(i, end).join(' ');

    if (overlap > 0 && i > 1) {
      const overlapStart = Math.max(0, i - overlap);
      const overlapEnd = i;
      const overlapChunk = sentences.slice(overlapStart, overlapEnd).join(' ');
      chunk = overlapChunk + ' ' + chunk;
    }

    chunks.push(chunk.trim());

    i += sentencesPerChunk;
  }

  return chunks;
}
```
