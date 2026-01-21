PDF to Pinecone Vector Store - N8N Workflow (EXAMPLE:RESTURENT MENU PDF)

Overview

This n8n workflow automates the process of extracting menu information from PDF files stored in Microsoft OneDrive and indexing them into a Pinecone vector database. This enables semantic search capabilities for restaurant menu items using AI embeddings.

Use Case

Perfect for restaurant management systems, food ordering applications, or customer service chatbots that need to quickly search and retrieve menu information based on natural language queries.

Workflow Steps

1. Manual Trigger
Initiates the workflow execution when clicked manually

2. Search File in OneDrive
Searches for a specific PDF file named "menu_pdf(1)" in your Microsoft OneDrive account

3. Download File
Downloads the found PDF file from OneDrive

4. Process and Store in Pinecone
Converts the PDF content into vector embeddings and stores them in Pinecone vector database for semantic search

5. OpenAI Embeddings
Uses OpenAI's embedding model to convert text into numerical vectors

6. Default Data Loader
Loads the PDF document data and extracts metadata including the filename

Prerequisites

Before running this workflow, you need:

- n8n instance (self-hosted or cloud)
- Microsoft OneDrive account with OAuth2 credentials configured
- OpenAI API key for embeddings
- Pinecone account with an index named "resturentagent"
- PDF menu file named "menu_pdf(1)" uploaded to your OneDrive

Required Credentials

Microsoft OneDrive OAuth2 API
Configure your Microsoft account credentials in n8n

OpenAI API
Add your OpenAI API key for generating embeddings

Pinecone API
Set up your Pinecone API credentials and ensure the index "resturentagent" exists

Configuration Details

Pinecone Vector Store Settings
- Mode: Insert
- Index Name: resturentagent
- Stores document vectors with metadata

Document Metadata
Each document chunk is stored with metadata containing:
- file_name: Original PDF filename

How to Use

1. Clone this repository
2. Import the workflow JSON into your n8n instance
3. Configure all required credentials (OneDrive, OpenAI, Pinecone)
4. Ensure your Pinecone index "resturentagent" is created
5. Upload your menu PDF to OneDrive with the name "menu_pdf(1)"
6. Click "Execute workflow" to run

Customization Options

Search Query
Modify the search query parameter in "Search a file" node to look for different files

Pinecone Index
Change the pineconeIndex value to use a different vector database index

Metadata Fields
Add additional metadata fields in the "Default Data Loader" node to capture more document information

Embedding Model
Adjust the OpenAI embeddings model in the "Embeddings OpenAI" node settings

Future Enhancements

- Add support for multiple PDF files in batch processing
- Implement automatic file watching and processing
- Add error handling and notification system
- Include text chunking customization options
- Support for other document formats beyond PDF

Troubleshooting

File Not Found
Ensure the PDF file exists in OneDrive with exact name "menu_pdf(1)"

Authentication Errors
Verify all API credentials are correctly configured and not expired

Pinecone Index Error
Check that the "resturentagent" index exists in your Pinecone account

Embedding Failures
Confirm OpenAI API key has sufficient credits and proper permissions

License

This workflow is provided as-is for educational and commercial use.

Contributing

Feel free to fork this workflow and submit improvements via pull requests.

Support

For issues or questions, please open an issue in this repository.
