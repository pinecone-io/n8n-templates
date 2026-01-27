# Extract insights from LinkedIn comments using Apify and Pinecone Assistant

![Visual diagram of the n8n workflow to extract insights from LinkedIn](extract-insights-from-linkedin-comments.png)

This n8n workflow template lets you extract insights from comments on your LinkedIn posts using Pinecone Assistant, Apify, and OpenAI. It scrapes LinkedIn comments using Apify and then retrieves relevant context from this data using Pinecone Assistant and generates insights with OpenAI, all without the need to train your own LLM.

### What is Pinecone Assistant?

[Pinecone Assistant](https://docs.pinecone.io/guides/assistant/overview) allows you to build production-grade chat and agent-based applications quickly. It abstracts the complexities of implementing retrieval-augmented (RAG) systems by managing the chunking, embedding, storage, query planning, vector search, model orchestration, reranking for you.

## Try it out

### Prerequisites

* A [Pinecone account](https://app.pinecone.io/) and [API key](https://app.pinecone.io/organizations/-/projects/-/keys)
* An [Open AI account](https://auth.openai.com/create-account) and [API key](https://platform.openai.com/settings/organization/api-keys)
* An [Apify account](https://apify.com/) and [API token](https://console.apify.com/settings/integrations)

### Setup

1. Create a Pinecone Assistant in the Pinecone Console [here](https://app.pinecone.io/organizations/-/projects/-/assistant) 
	1. Name your Assistant `n8n-assistant`
	2. No need to configure a Chat model or Assistant instructions
2. Setup Pinecone API key, OpenAI API key, and Apify API token as credentials in n8n
3. In the Set LinkedIn url node, enter your LinkedIn profile url, for a personal or company profile
4. Select your Assistant Name in each of the Pinecone Assistant nodes, if it's not already
5. Schedule or manually execute Step 1 and 2 to extract the LinkedIn comment data and upload to Pinecone Assistant
6. Once the data is uploaded, ask a question in the chat: `Summarize the comments related to [SOME TOPIC YOU TALK ABOUT] and categorize into positive, neutral, and negative.`

### Ideas for customizing this workflow

- Connect to other social platforms to extract insights from Instagram, X/Twitter, etc. in addition to LinkedIn

### Need help?

You can find help by asking in the [Pinecone Discord community](https://discord.gg/tJ8V62S3sH) or [filing an issue](https://github.com/pinecone-io/n8n-templates/issues/new/choose) on this repo.