# DataCamp Code Along: Build a customer assistant with multi-domain RAG

This workflow was built for the DataCamp code along session [Build a Customer Assistant AI with Multi-Domain RAG, n8n, and Pinecone](https://www.datacamp.com/webinars/build-a-customer-assistant-ai-with-multi-domain-rag-n8n-and-pinecone).

It shows how a vacation rental property manager can manage multiple properties, each with different information, using Pinecone Assistant. Guests can ask questions about their property and get a personalized answer back.

### Key takeaways

- Learn what knowledge is, why it matters for AI, and where Pinecone fits in.
- Understand why specialized knowledge bases beat single-index RAG.
- Build a multi-domain query routing system in n8n with Pinecone Assistant.

### What is Pinecone Assistant?

[Pinecone Assistant](https://docs.pinecone.io/guides/assistant/overview) allows you to build production-grade chat and agent-based applications quickly. It abstracts the complexities of implementing retrieval-augmented (RAG) systems by managing the chunking, embedding, storage, query planning, vector search, model orchestration, and reranking for you.

## Try it out

### Prerequisites

* A [Pinecone account](https://app.pinecone.io/?sessionType=signup&utm_source=datacamp&utm_medium=webinar&utm_campaign=datacamp_codealong_2026_04_29&utm_content=template) and [API key](https://app.pinecone.io/organizations/-/projects/-/keys)
* An [OpenAI account](https://auth.openai.com/create-account) and [API key](https://platform.openai.com/settings/organization/api-keys) with credits loaded (this will cost less than $1)
  * If you have an Anthropic API key with credits loaded, that will work too.

### Setup

1. Create three Pinecone Assistants in the [Pinecone Console](https://app.pinecone.io/organizations/-/projects/-/assistant) named:
   - `n8n-vacation-rental-property-lakeside`
   - `n8n-vacation-rental-property-birchwood`
   - `n8n-vacation-rental-property-hillcrest`
2. Use the **Connect to Pinecone** button to authenticate, or if you self-host n8n, create a Pinecone credential and add your API key directly.
3. Add your OpenAI credential in n8n.
4. Select the correct Assistant Name in each of the respective Pinecone Assistant nodes.
5. The workflow fetches fictional property data from [this GitHub folder](https://github.com/pinecone-io/n8n-templates/blob/main/vacation-rental-property-manager-assistants/fictional-data) automatically — no manual download needed.
6. Run the **Upload documents** section of the workflow to upload all documents to Pinecone.
7. Once the data is uploaded, ask questions in the chat about a property:
   - `I need help with the coffee maker`
   - `The air fryer isn't working at the Lakeside property`
   - `I'm staying at Lakeside and the refrigerator is leaking`

### Ideas for customizing this workflow

- This workflow uses one Assistant per property. You could also use one Assistant and separate the data by setting a metadata field, `property`, to the name of the property the file is for.
- Use your own data and adapt to your use case: multiple store locations, restaurants, teams, users, or anywhere you need different context per domain.

### Need help?

You can find help by asking in the [Pinecone Discord community](https://discord.gg/tJ8V62S3sH) or [filing an issue](https://github.com/pinecone-io/n8n-templates/issues/new/choose) on this repo.
