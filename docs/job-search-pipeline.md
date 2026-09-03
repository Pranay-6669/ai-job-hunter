# Job Search Pipeline

This is a JSON object representing a workflow in N8N, a workflow automation tool. The workflow is a series of nodes connected together to perform a specific task. Here's a breakdown of the different parts of the JSON object:

**Workflow**

* `id`: A unique identifier for the workflow.
* `name`: The name of the workflow.
* `type`: The type of workflow (in this case, a data table workflow).
* `typeVersion`: The version of the workflow type.
* `position`: The position of the workflow in the workflow editor.

**Nodes**

* `n8n-nodes-base.dataTable`: A data table node that extracts data from a table.
* `n8n-nodes-base.scheduleTrigger`: A schedule trigger node that triggers a workflow at a specific time.
* `n8n-nodes-base.dataTable`: Another data table node that extracts data from a table.
* `n8n-nodes-base.httpRequest`: An HTTP request node that sends a request to a URL.
* `n8n-nodes-base.code`: A code node that executes a JavaScript function.
* `n8n-nodes-base.gmail`: A Gmail node that sends an email.
* `n8n-nodes-base.code`: Another code node that formats the data for email.
* `n8n-nodes-base.code`: A code node that creates a mail.
* `n8n-nodes-base.gmail`: Another Gmail node that sends a message.

**Connections**

* `On form submission`: A connection that connects the "Extract from File" node to the "Information Extractor" node.
* `Extract from File`: A connection that connects the "Information Extractor" node to the "Insert row" node.
* `Ollama Chat Model1`: A connection that connects the "Information Extractor" node to the "Insert row" node.
* `Information Extractor`: A connection that connects the "Insert row" node to the "Schedule Trigger" node.
* `Schedule Trigger`: A connection that connects the "Get row(s)" node to the "HTTP Request" node.
* `Get row(s)`: A connection that connects the "HTTP Request" node to the "Latest Jobs" node.
* `HTTP Request`: A connection that connects the "Latest Jobs" node to the "Format for Email" node.
* `Format for Email`: A connection that connects the "Format for Email" node to the "Create mail" node.
* `Latest Jobs`: A connection that connects the "Format for Email" node to the "Create mail" node.
* `Create mail`: A connection that connects the "Create mail" node to the "Send a message" node.

**Settings**

* `executionOrder`: The order in which the nodes are executed.
* `binaryMode`: The mode in which the nodes are executed (separate or combined).
* `availableInMCP`: A flag indicating whether the workflow is available in the MCP.
* `timeSavedMode`: The mode in which the time saved is calculated (fixed or variable).
* `timezone`: The timezone used for the workflow.
* `callerPolicy`: The policy for the caller (workflows from the same owner).

**Meta**

* `templateCredsSetupCompleted`: A flag indicating whether the template credentials are set up.
* `tags`: An array of tags associated with the workflow.

Overall, this workflow appears to be a data extraction and processing workflow that extracts data from a table, sends an HTTP request to a URL, processes the response, and sends an email with the data.
