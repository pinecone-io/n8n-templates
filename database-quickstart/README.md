# Database quickstart

This n8n workflow template lets you chat with Pinecone release notes files downloaded via HTTP using OpenAI and Pinecone vector database. It retrieves relevant context from your data in a Pinecone index in real time so you can get accurate, context-aware answers about your proprietary data—without the need to train your own LLM.

### What is Pinecone vector database?
[Pinecone vector database](https://docs.pinecone.io/guides/get-started/overview) indexes and stores vector embeddings for fast retrieval and searching for semantically similar data (semantic search over a dense index) or matching words or phrases (lexical or keyword search over a sparse index), or both (over a hybrid index). This template uses a dense Pinecone index for semantic search.

### Not interested in chunking and embedding your own data or figuring out which search method to use?

Try our n8n quickstart for Pinecone Assistant [here](https://docs.pinecone.io/guides/assistant/quickstart#n8n) or check out the full workflow to chat with your Google Drive documents [here](https://n8n.io/workflows/9942-rag-powered-document-chat-with-google-drive-openai-and-pinecone-assistant/).

## Try it out

### Prerequisites

* A [Pinecone account](https://app.pinecone.io/) and [API key](https://app.pinecone.io/organizations/-/projects/-/keys)
* An [Open AI account](https://auth.openai.com/create-account) and [API key](https://platform.openai.com/settings/organization/api-keys)

### Setup

1. Create a Pinecone index in the Pinecone Console [here](https://app.pinecone.io/organizations/-/projects/-/indexes) 
	1. Name your index `n8n-dense-index`
	2. Select OpenAI's `text-embedding-3-small`
	3. Set the Dimension to `1536`
	4. Leave everything else as default
	5. If you use a different index name, update the related nodes to reflect this change
2. Setup Pinecone API key credential in n8n
	1. In the Pinecone Vector Store node -> Credential to connect with, select Create new credential
	2. Paste in your Pinecone API key in the API Key field
	3. Name this credential  `Pinecone` so that other nodes reference it
3. Setup the Open AI credential in n8n
	1. In the OpenAI Chat Model node -> Credential to connect with, select Create new credential
	2. Set the API Key field to your OpenAI API key
4. Activate the workflow or test it with a manual execution to ingest the documents
5. Chat with the Pinecone release notes!

### Ideas for customizing this workflow

- Use your own data
	- Change the urls in Set file urls node to use your own files.
	- You may need to adjust the chunk sizes in the Recursive Character Text Splitter node or use a different chunking strategy. You want chunks that are big enough to contain meaningful information but not so big that the meaning is diluted or it can't fit within the context window of the embedding model. Refer to our [article about chunking strategies](https://www.pinecone.io/learn/chunking-strategies/) for more info.
	- Customize the System Message of the AI Agent node to reflect what the Pinecone Vector Store Tool will be used for. Be sure to include info on what data can be retrieved using that tool.
	- Customize the Description of the Pinecone Vector Store Tool to reflect what data you are storing in the Pinecone index.
- Use n8n, Pinecone Assistant, and OpenAI to [chat with your Google Drive documents](https://n8n.io/workflows/9942-rag-powered-document-chat-with-google-drive-openai-and-pinecone-assistant/).
### Need help?

You can find help by asking in the [Pinecone Discord community](https://discord.gg/tJ8V62S3sH), asking on the [Pinecone Forum](https://community.pinecone.io/), or [filing an issue](https://github.com/pinecone-io/n8n-templates/issues/new/choose) on this repo.