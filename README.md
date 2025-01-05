# Flowise Chatbot
This is what works the magic behind curia.chat – you can think of it as the glue that holds everything together.  
The chatbot is based on the software Flowise, which is essentially a GUI for creating LLM-flows.

# Prerequisites
* A Flowise Instance  
* An OpenAI API Key  
* A Groq API Key  

# What you will find here:
- **ECJ Judgments Agents.json**  
  This file contains the agent flow that can be imported into Flowise. Note that you will need to update several details (e.g., all connection data for models).  
  The flow uses different LLM providers and various LLMs for specific purposes while keeping the budget in mind. You are free to modify this. However, due to the numerous (small) completion requests required, I found Groq preferable to OpenAI in most cases. On the other hand, I found OpenAI's embeddings to be quite effective.

- **judgment_finder-CustomTool.json**  
  This custom tool enables the chatbot to find judgments based on case numbers or ECLI.  
  You need to update the connection settings to your MySQL database within the tool (look for *XXXX*). Please note that your password must be inserted in plain text (there is no secrets management for custom tools), so it is highly recommended to use a read-only user.

- **judgment_summarizer-CustomTool.json**  
  This custom tool allows the chatbot to retrieve summaries of judgments from the database based on the ECLI. It does not create summaries itself but instead relies on them being present in the database.  
  You need to update the connection settings to your MySQL database within the tool (look for *XXXX*). Please note that your password must be inserted in plain text (there is no secrets management for custom tools), so it is highly recommended to use a read-only user.
