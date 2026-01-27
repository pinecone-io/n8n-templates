# n8n + Pinecone templates

A collection of ready-to-use [n8n](https://n8n.io/) workflow templates for building intelligent automations using [Pinecone](https://www.pinecone.io/).

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
|Assistant quickstart|[assistant-quickstart/assistant-quickstart.json]()|Pinecone Assistant, Open AI|
|Database quickstart|[database-quickstart/database-quickstart.json]()|Pinecone Vector Store, Open AI|
|Chat with your Google Drive docs Using Pinecone Assistant|[document-chat-assistant/chat-with-google-drive-using-pinecone-assistant.json]()|Google Drive, Pinecone Assistant, Open AI|
|Chat with your Google Drive docs Using Pinecone Vector Database|[document-chat-database/chat-with-google-drive-using-pinecone-vector-database.json]()|Google Drive, Pinecone Vector Store, Open AI|
|Extract insights from LinkedIn comments using Apify and Pinecone Assistant|[extract-insights-from-linkedin-comments/extract-insights-from-linkedin-comments.json]()|LinkedIn, Apify, Pinecone Assistant, Open AI|
|Query support docs via Dropbox and Slack using Pinecone Assistant|[query-support-docs-via-dropbox-and-slack/query-support-docs-via-dropbox-and-slack.json]()|Dropbox, Slack, Pinecone Assistant, Open AI|

## Finding help

You can find help by asking in the [Pinecone Discord community](https://discord.gg/tJ8V62S3sH) or [filing an issue](https://github.com/pinecone-io/n8n-templates/issues/new/choose) on this repo.

## Contributing

Have an idea for a new workflow using Pinecone?

1. Fork this repo
2. Add your workflow .json file and a short README.md
3. Update this README.md to include a link and description in the Templates overview above
4. Submit a pull request

## License

These templates are licensed under the MIT-0 License. See the LICENSE file.
