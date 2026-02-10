# Vacation rental property manager with multiple Assistants

This workflow shows how a vacation rental property manager can manage multiple properties—each with different information—using [Pinecone Assistant](https://docs.pinecone.io/guides/assistant/overview). Guests can ask questions about their property in chat and get personalized answers from the right property’s documentation.

![Vacation rental property manager with multiple Assistants](vacation-rental-property-manager-assistants.png)

## What this workflow does

- **Step 1 – Upload property data:** Watches three Google Drive folders (`hillcrest`, `birchwood`, `lakeside`). When you add files to a folder, the workflow downloads them and uploads them to the corresponding Pinecone Assistant for that property.
- **Step 2 – Answer property questions:** A chat interface lets users ask questions (e.g. “How does the coffee maker work?” or “The air fryer isn’t working at the Lakeside property”). An AI agent infers which property they mean, then routes the question to the right Pinecone Assistant so answers come from that property’s docs.

## What is Pinecone Assistant?

[Pinecone Assistant](https://docs.pinecone.io/guides/assistant/overview) helps you build chat and agent apps with retrieval-augmented generation (RAG) without managing chunking, embeddings, vector search, or reranking yourself.

## Prerequisites

- A [Pinecone account](https://app.pinecone.io/) and [API key](https://app.pinecone.io/organizations/-/projects/-/keys)
- A GCP project with [Google Drive API enabled and configured](https://docs.n8n.io/integrations/builtin/credentials/google/oauth-single-service/)
- An [OpenAI account](https://auth.openai.com/create-account) and [API key](https://platform.openai.com/settings/organization/api-keys)

## Setup

1. **Create three Pinecone Assistants** in the [Pinecone Console](https://app.pinecone.io/organizations/-/projects/-/assistant):
   - `n8n-vacation-rental-property-hillcrest`
   - `n8n-vacation-rental-property-birchwood`
   - `n8n-vacation-rental-property-lakeside`  
   You can leave Chat model and Assistant instructions unset.

2. **In n8n**, add credentials for:
   - Google Drive (OAuth2)
   - Pinecone (Assistant API)
   - OpenAI

3. **In the workflow**, set the Assistant name in each Pinecone Assistant node to match the names above (if you used different names in the console, use those instead).

4. **In Google Drive**, create three folders named `hillcrest`, `birchwood`, and `lakeside`, and in the workflow point each “file added” trigger to the correct folder.

5. **Activate the workflow** so new files in those folders are uploaded to the assistants.

6. **Try the chat** with questions like:
   - “I need help with the coffee maker”
   - “The air fryer isn’t working at the Lakeside property”

## Customization ideas

- This template uses **one Assistant per property**. You can instead use a single Assistant and use a metadata field (e.g. `property`) on each document to filter by property.
- Adjust the AI agent’s system message to change how the assistant infers the property or handles “contact me” requests.

