# n8n + Pinecone templates

A collection of ready-to-use [n8n](https://n8n.io/) workflow templates for building intelligent automations using Pinecone.

These workflows let you chat with your data, process documents, and generate content by connecting sources like Google Drive, email attachments, and more.

## Quick start

You can import any workflow in three ways:

### Option 1: Paste JSON directly

1. Copy the contents of the json file from this repo
2. In n8n, select Create Workflow
3. Paste the template onto the workflow canvas

### Option 2: Import from file

1. Download the .json file you want to use from this repository
2. In n8n, select Create Workflow
3. From the Settings menu, select Import from File...
4. Select the .json file you downloaded

### Option 3: Import from URL

1. Grab the URL of the .json file you want to use from this repository
2. In n8n, select Create Workflow
3. From the Settings menu, select Import from URL...
4. Enter the Workflow URL
5. Select Import

Then, add your credentials (OpenAI, Pinecone, Google Drive, etc.) and you’re ready to run!

## Templates overview

|Template|File|Integrations used|
| ------------- | ------------- | ------------- |
|Assistant quickstart|quickstart/assistant-quickstart.json|[Pinecone Assistant](https://docs.pinecone.io/guides/assistant/overview), Open AI|
|Database quickstart|database-quickstart/database-quickstart.json|[Pinecone Database](https://docs.pinecone.io/guides/get-started/overview), Open AI|
|Chat with your Google Drive docs Using Pinecone Assistant|document-chat/chat-with-google-drive-docs.json|Google Drive, [Pinecone Assistant](https://docs.pinecone.io/guides/assistant/overview), Open AI|

## Finding help

You can find help by asking in the [Pinecone Discord community](https://discord.gg/tJ8V62S3sH), asking on the [Pinecone Forum](https://community.pinecone.io/), or [filing an issue](https://github.com/pinecone-io/n8n-templates/issues/new/choose) on this repo.

## Contributing

Have an idea for a new workflow using Pinecone?

1. Fork this repo
2. Add your workflow .json file and a short README.md
3. Update this README.md to include a link and description in the Templates overview above
4. Submit a pull request

## License

These templates are licensed under the MIT-0 License. See the LICENSE file.
