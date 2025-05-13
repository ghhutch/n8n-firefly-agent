# n8n Firefly Image Generation Agent
This is an n8n agent that utilizes a chat input, Ollama AI model (llama3.2:3b), and Adobe Firefly Services Generate Image API to generate images and optimize prompts.  This model is 

DISCLAIMER: This was developed for exploratory purposes and has not been thoroughly tested.

Conceptual Use Case:
* As a creative, I need to generate ideas and imagery for a marketing campaign.
* As a creative, I need coaching to create stellar prompts for image generation.
* As a creative, I want to iterate on my ideas using natural language using modern technology.

## Screenshot of Agent Flow:
![image](https://github.com/ghhutch/n8n-firefly-agent/blob/main/n8n_firefly_agent.png?raw=true)

## Screenshot of Generate Firefly Image Sub-flow
![image](https://github.com/ghhutch/n8n-firefly-agent/blob/main/n8n_generate_firefly_image.png?raw=true)


## Pre-Requisites
1. Install n8n local
2. Install ollama and pull the model llama3.2:b
3. Get Firefly Services API credentials from your Adobe Admin.
4. Install Open-WebUI
5. Install the Open-WebUI [n8n_pipe from Cole Medin](https://openwebui.com/f/coleam/n8n_pipe)

## Setup
1. Download the n8n_firefly_agent.json and n8n_generate_firefly_image.json
2. In n8n, create a new workflow
3. Click ... > Import From FIle > Choose the n8n_generate_firefly_image.json
4. Edit the Authentiate step
5. Enter your client_id and client_secret
6. Enter the name "Generate Firefly Image"
7. Save
8. Activate
9. Create a new workflow.
10. Click ... > Import From File > Choose the n8n_firefly_agent.json
11. Click Save
12. Activate and copy the webhook URL
13. In Open-WebUI go to Admin Settings > Functions
14. Create the n8n_pipe function.
15. Configure the valve settings and paste your webhook url. NOTE: Sometimes accessing n8n from open-webui can be tricky. I installed n8n using docker desktop, went into the container Exec area and ran the command "hostname -i" to get the IP of the n8n instance for the n8n host.
16. Save the settings
17. Go to models and enable the n8n_pipe.

# Usage
In n8n:
1. Use the n8n chat and enter a prompt such as "Generate an image of a dog and pony show"
2. Use the prompt suggestions to improve image generation.

In Open-WebUI:
1. Open up a new chat
2. Choose the N8N Pipe model
3. Enter a prompt such as "Generate an image of a dog and pony show"
4. Use the prompt suggestions to improve image generation.

