# AI Job Hunter with n8n and Ollama

An n8n workflow that analyzes an uploaded PDF resume with a local Ollama model, stores a structured candidate profile, periodically searches for relevant jobs, formats the latest matches, and emails the results.

## Workflow paths

### Candidate profile

`Resume Form → Extract PDF → Ollama Information Extractor → Candidate Profile Data Table`

### Job alerts

`Schedule Trigger → Read Profile → Job Search API → Select Latest Jobs → Format Email → Gmail`

## Requirements

- n8n running locally
- Ollama with `llama3.2:3b`
- An n8n Data Table
- Job-search API credential for the HTTP Request node
- Gmail credential for email notifications

## Import and configure

1. Import `workflow.json` into n8n.
2. Connect **Ollama Chat Model1** to your local Ollama credential.
3. Create the **Candidate Profile** table using the included Create Data Table node.
4. Re-select that table in the Insert Row and Get Rows nodes.
5. Reconnect the job-search HTTP credential.
6. Reconnect Gmail and replace `YOUR_EMAIL@example.com`.
7. Check the Schedule Trigger and your n8n timezone.
8. Test both workflow paths before activation.

## Privacy

Resumes contain personal information. Run this locally, restrict access to the form and n8n editor, and define a retention period for stored profiles and execution data.
