# n8n Installer

**n8n Installer** is an open-source Docker Compose template designed to significantly simplify setting up a comprehensive, self-hosted environment for n8n and Flowise. It bundles essential supporting tools like Open WebUI (as an interface for n8n agents), Supabase (database, vector information storage, authentication), Qdrant (high-performance vector information storage), Langfuse (to observe AI model performance), SearXNG (private metasearch), Grafana/Prometheus (monitoring), Crawl4ai (web crawling), and Caddy (for managed HTTPS). Plus, during setup, you can optionally import over 300 community workflows into your n8n instance!

### Why This Setup?

This installer helps you create your own powerful, private AI workshop. Imagine having a suite of tools at your fingertips to:

- Automate repetitive tasks.
- Build smart assistants tailored to your needs.
- Analyze information and gain insights.
- Generate creative content.

This setup provides a comprehensive suite of cutting-edge services, all pre-configured to work together. Key advantages include:

- **Rich Toolset:** Get a curated collection of powerful open-source tools for AI development, automation, and monitoring, all in one place.
- **Scalable n8n Performance:** n8n runs in `queue` mode by default, leveraging Redis for task management and Postgres for data storage. You can dynamically specify the number of n8n workers during installation, allowing for robust parallel processing of your workflows to handle demanding loads.
- **Full Control:** All of this is hosted by you, giving you full control over your data, operations, and how resources are allocated.

### What's Included

✅ [**Self-hosted n8n**](https://n8n.io/) - A low-code platform with over 400 integrations and advanced AI components to automate workflows.
✅ **Caddy, Postgres, and Redis** - Core services for web proxy, database, and caching, which are always included.

The installer also makes the following powerful open-source tools **available for you to select and deploy** via an interactive wizard during setup:

✅ [**Supabase**](https://supabase.com/) - An open-source alternative to Firebase, providing database storage, user authentication, and more. It's a popular choice for AI applications.

✅ [**Open WebUI**](https://openwebui.com/) - A user-friendly, ChatGPT-like interface to interact privately with your AI models and n8n agents.

✅ [**LiteLLM**](https://www.litellm.ai/) – A lightweight proxy service that enables integration and management of multiple large language models (LLMs). Easily extend the range of available LLMs for tools like Open WebUI.

✅ [**Flowise**](https://flowiseai.com/) - A no-code/low-code AI agent builder that complements n8n perfectly, allowing you to create sophisticated AI applications with ease.

✅ [**ComfyUI**](https://github.com/comfyanonymous/ComfyUI) - A powerful, node-based UI for Stable Diffusion workflows. Build and run image-generation pipelines visually, with support for custom nodes and extensions.

✅ [**Dify**](https://dify.ai/) - An open-source AI application development platform that provides comprehensive LLMOps capabilities, including workflow management, prompt engineering, RAG pipelines, and AI agent orchestration. Perfect for building production-ready AI applications.

✅ [**Qdrant**](https://qdrant.tech/) - A high-performance open-source vector store, specialized for AI. While Supabase also offers vector capabilities, Qdrant is included for its speed, making it ideal for demanding AI tasks.

✅ [**SearXNG**](https://searxng.org/) - A free, open-source internet metasearch engine. It aggregates results from numerous search services without tracking or profiling you, ensuring your privacy.

✅ [**Caddy**](https://caddyserver.com/) - A powerful web server that automatically handles HTTPS/TLS for your custom domains, keeping your connections secure.

✅ [**Gotenberg**](https://gotenberg.dev/) - A stateless API for converting HTML, Markdown, Word, Excel, and other documents to PDF, PNG, or JPEG. Available only within the Docker network for internal use by n8n workflows and other services.

✅ [**Langfuse**](https://langfuse.com/) - An open-source platform to help you observe and understand how your AI agents are performing, making it easier to debug and improve them.

✅ [**Crawl4ai**](https://github.com/Alfresco/crawl4ai) - A flexible web crawler designed for AI, enabling you to extract data from websites for your projects.

✅ [**Letta**](https://docs.letta.com/) - An open-source agent server and SDK that can be connected to various LLM API backends (OpenAI, Anthropic, Ollama, etc.), enabling you to build and manage AI agents.

✅ [**Weaviate**](https://weaviate.io/) - An open-source AI-native vector database with a focus on scalability and ease of use. It can be used for RAG, hybrid search, and more.

✅ [**Neo4j**](https://neo4j.com/) - A graph database management system that allows you to model, store, and query data as a network of nodes and relationships.

✅ [**Ollama**](https://ollama.com/) - Run Llama 3, Mistral, Gemma, and other large language models locally.

✅ [**Prometheus**](https://prometheus.io/) - An open-source monitoring and alerting toolkit to keep an eye on system health.

✅ [**Grafana**](https://grafana.com/) - An open-source platform for visualizing monitoring data, helping you understand system performance at a glance.

✅ [**Portainer**](https://www.portainer.io/) - A lightweight, secure web UI to manage your Docker environment (containers, images, volumes, networks) with ease.

### Included Community Workflows

Get started quickly with a vast library of pre-built automations (optional import during setup)! This collection includes over 300 workflows covering a wide range of use cases:

🚦 **What's inside?**

- **AI Agents & Chatbots:** RAG, LLM, LangChain, Ollama, OpenAI, Claude, Gemini, and more
- **Gmail & Outlook:** Smart labeling, auto-replies, PDF handling, and email-to-Notion
- **HR, E-commerce, IT, Security, Research, and more!**
- **Notion, Airtable, Google Sheets:** Data sync, AI summaries, knowledge bases
- **PDF, Image, Audio, Video:** Extraction, summarization, captioning, speech-to-text
- **Slack, Mattermost:** Ticketing, feedback analysis, notifications
- **Social Media:** LinkedIn, Pinterest, Instagram, Twitter/X, YouTube, TikTok automations
- **Telegram, WhatsApp, Discord:** Bots, notifications, voice, and image workflows
- **WordPress, WooCommerce:** AI content, chatbots, auto-tagging

## Installation

### Prerequisites before Installation

1.  **Domain Name:** You need a registered domain name (e.g., `yourdomain.com`).
2.  **DNS Configuration:** Before running the installation script, you **must** configure DNS A-record for your domain, pointing to the public IP address of the server where you'll install this system. Replace `yourdomain.com` with your actual domain:
    - **Wildcard Record:** `A *.yourdomain.com` -> `YOUR_SERVER_IP`
3.  **Server:** Minimum server system requirements: Ubuntu 24.04 LTS, 64-bit.
    - For running **all available services**: at least **8 GB Memory / 4 CPU Cores / 60 GB Disk Space **.
    - For a minimal setup with only **n8n and Flowise**: **4 GB Memory / 2 CPU Cores / 30 GB Disk Space**.

### Running the Installer

The recommended way to install is using the provided main installation script.

1.  Connect to your server via SSH.
2.  Run the following command:

    ```bash
    git clone https://github.com/inode-khak/n8n-installer && cd n8n-installer && sudo bash ./scripts/install.sh
    ```

This single command automates the entire setup process, including:

- Preparing your system (updates, firewall configuration, and basic security enhancements like brute-force protection).
- Installing Docker and Docker Compose (tools for running applications in isolated environments).
- Generating a configuration file (`.env`) with necessary secrets and your domain settings.
- Launching all the services.

During the installation, the script will prompt you for:

1.  Your **primary domain name** (Required, e.g., `yourdomain.com`). This is the domain for which you've configured the wildcard DNS record.
2.  Your **email address** (Required, used for service logins like Flowise, Supabase dashboard, Grafana, and for SSL certificate registration with Let's Encrypt).
3.  An optional **OpenAI API key** (Not required. If provided, it can be used by Supabase AI features and Crawl4ai. Press Enter to skip).
4.  Whether you want to **import ~300 ready-made n8n community workflows** (y/n, Optional. This can take 20-30 minutes, depending on your server and network speed).
5.  The **number of n8n workers** you want to run (Required, e.g., 1, 2, 3, 4. This determines how many workflows can be processed in parallel. Defaults to 1 if not specified).
6.  A **Service Selection Wizard** will then appear, allowing you to choose which of the available services (like Flowise, Supabase, Qdrant, Open WebUI, etc.) you want to deploy. Core services (Caddy, Postgres, Redis) will be set up to support your selections.

Upon successful completion, the script will display a summary report. This report contains the access URLs and credentials for the deployed services. **Save this information in a safe place!**

## ⚡️ Quick Start and Usage

After successful installation, your services are up and running! Here's how to get started:

1.  **Access Your Services:**
    The installation script provided a summary report with all access URLs and credentials. Please refer to that report. The main services will be available at the following addresses (replace `yourdomain.com` with your actual domain):
    - **n8n:** `n8n.yourdomain.com` (Log in with the email address you provided during installation and the initial password from the summary report. You may be prompted to change this password on first login.)
    - **Open WebUI:** `webui.yourdomain.com`
    - **LiteLLM** `litellm.yourdomain.com`
    - **Flowise:** `flowise.yourdomain.com` (Log in with the email address you provided during installation and the initial password from the summary report.)
    - **Dify:** `dify.yourdomain.com` (AI application development platform with comprehensive LLMOps capabilities)
    - **Supabase (Dashboard):** `supabase.yourdomain.com`
    - **Langfuse:** `langfuse.yourdomain.com`
    - **Letta:** `letta.yourdomain.com`
    - **Weaviate:** `weaviate.yourdomain.com`
    - **Neo4j:** `neo4j.yourdomain.com`
    - **Grafana:** `grafana.yourdomain.com`
    - **SearXNG:** `searxng.yourdomain.com`
    - **Prometheus:** `prometheus.yourdomain.com` (Typically used as a data source for Grafana)
    - **Portainer:** `portainer.yourdomain.com` (Protected by Caddy basic auth; on first login, complete Portainer admin setup)
    - **ComfyUI:** `comfyui.yourdomain.com` (Node-based Stable Diffusion UI)

2.  **Explore n8n:**

    - Log in to your n8n instance. This is your central hub for workflow automation.
    - If you chose to import the community workflows during installation, you'll find over 300 examples in your "Workflows" section. These are a great way to learn and get ideas.
    - Start building your first workflow! You have access to over 400 integrations and powerful AI tools.

3.  **Utilize Integrated AI Tools:**

    - **Connect n8n with Vector Stores:** Use n8n to connect to Qdrant (accessible via its own endpoint if needed, typically `qdrant.yourdomain.com`), Supabase, or Weaviate (`weaviate.yourdomain.com`) to store and retrieve information for your AI tasks like Retrieval Augmented Generation (RAG).
    - **Build with Flowise:** Access Flowise at `flowise.yourdomain.com` to create AI agents and applications. You can trigger Flowise agents from n8n or vice-versa.
    - **Interact with Open WebUI:** Use Open WebUI at `webui.yourdomain.com` as a chat interface for your local AI models or n8n agents (e.g., using the n8n_pipe integration if configured).
    - **Configure LLMs:** If you wish to use large language models (LLMs) from providers like OpenAI, Anthropic, or locally via Ollama (if installed), you can easily configure credentials and connections within n8n nodes or in services like Flowise and Open WebUI.

4.  **Check Monitoring (Optional):**
    - Visit Grafana (`grafana.yourdomain.com`) to see dashboards monitoring your system's performance (data sourced from Prometheus).

### Using Pre-installed Libraries in n8n's Custom JavaScript

This setup pre-installs useful Node.js libraries for use in n8n's Code nodes, allowing you to write custom JavaScript snippets with enhanced capabilities:

- **`cheerio`**: For parsing and manipulating HTML/XML (e.g., web scraping).
- **`axios`**: A promise-based HTTP client for making requests to external APIs.
- **`moment`**: For parsing, validating, manipulating, and displaying dates/times.
- **`lodash`**: A utility library for common programming tasks (arrays, objects, strings, etc.).

## Upgrading

To update all components (n8n, Open WebUI, etc.) to their latest versions and incorporate the newest changes from this installer project, use the update script from the project root:

```bash
sudo bash ./scripts/update.sh
```

This script will:

1.  Fetch the latest updates for the installer from the Git repository.
2.  Temporarily stop the currently running services.
3.  Download the latest versions of the Docker images for all services.
4.  Ask if you want to re-run the n8n workflow import (useful if you skipped this during the initial installation or want to refresh the community workflows).
5.  Restart all services with the new updates.

## Cleaning up Docker

If you need to free up disk space, you can run the Docker cleanup script. This script removes all unused Docker containers, images, and volumes.

```bash
sudo bash ./scripts/docker_cleanup.sh
```

This can be useful for removing old images and freeing up space, but be aware that it will remove all unused data.

## Important Links

- Based on a project by [kossakovsky](https://github.com/kossakovsky/n8n-installer) and [coleam00](https://github.com/coleam00/local-ai-packaged)
- [Original Starter Kit](https://github.com/n8n-io/self-hosted-ai-starter-kit) by the n8n team
- [Community forum](https://thinktank.ottomator.ai/c/local-ai/18) over in the oTTomator Think Tank for discussions and support.
- [GitHub Kanban board](https://github.com/users/coleam00/projects/2/views/1) for tracking new features and bug fixes.
- Download an N8N + OpenWebUI integration [directly on the Open WebUI site.](https://openwebui.com/f/coleam/n8n_pipe/) (More instructions may be available on that page).

## Troubleshooting

Here are solutions to common issues you might encounter:

### Temporary "Dangerous Site" Warning in Browser

- **Symptom:** Immediately after deploying the services, your browser (e.g., Chrome) might display a "Dangerous Site" or similar security warning when you try to access your services. This warning typically disappears after some time (e.g., within a few hours or by the next day).
- **Cause:** This can happen for a couple of reasons:
  1.  **Brief use of a self-signed certificate:** When Caddy (the web server managing your SSL certificates) starts up for a new domain, it might briefly use a temporary, self-signed certificate while it's in the process of requesting and obtaining a valid SSL certificate from Let's Encrypt.
  2.  **Delay in applying the new certificate:** There might also be a short delay before the newly obtained certificate from Let's Encrypt is fully applied and recognized by all systems.
- **Solution:** This is usually a temporary issue and resolves itself. Give it some time. If the warning persists for more than 24 hours, check your Caddy logs for any errors related to certificate acquisition and ensure your DNS settings are correctly pointing your domain to the server's IP address. You can also try clearing your browser's cache or using an incognito/private window to re-check.

### Supabase Issues

- **Supabase Pooler Restarting:** If the `supabase-pooler` component keeps restarting, follow the instructions in [this GitHub issue](https://github.com/supabase/supabase/issues/30210#issuecomment-2456955578).
- **Supabase Analytics Startup Failure:** If the `supabase-analytics` component fails to start after changing your Postgres password, you might need to reset its data. **Warning: This will delete your Supabase database data. Proceed with extreme caution and ensure you have backups if needed.** The technical step involves deleting the `supabase/docker/volumes/db/data` folder.
- **Supabase Service Unavailable:** Ensure your Postgres database password does not contain special characters like "@". Other special characters might also cause issues. If services like n8n report they cannot connect to Supabase, and other diagnostics seem fine, this is a common cause.

### General Issues

- **VPN Conflicts:** Using a VPN might interfere with downloading Docker images. If you encounter issues pulling images, try temporarily disabling your VPN.
- **Server Requirements:** If you experience unexpected issues, ensure your server meets the minimum hardware and operating system requirements (including version) as specified in the "Prerequisites before Installation" section.

## 👓 Recommended Reading

n8n offers excellent resources for getting started with its AI capabilities:

- [AI agents for developers: from theory to practice with n8n](https://blog.n8n.io/ai-agents/)
- [Tutorial: Build an AI workflow in n8n](https://docs.n8n.io/advanced-ai/intro-tutorial/)
- [Langchain Concepts in n8n](https://docs.n8n.io/advanced-ai/langchain/langchain-n8n/) (Langchain is a framework n8n uses for some AI features)
- [Demonstration of key differences between agents and chains](https://docs.n8n.io/advanced-ai/examples/agent-chain-comparison/)
- [What are vector databases?](https://docs.n8n.io/advanced-ai/examples/understand-vector-databases/) (Explains tools like Supabase and Qdrant in more detail)

## 🎥 Video Walkthrough

- [Cole's Guide to the AI Starter Kit](https://youtu.be/pOsO40HSbOo) (Provides a visual guide to a similar setup)

## 🛍️ More AI Templates

For more AI workflow ideas, visit the [**official n8n AI template gallery**](https://n8n.io/workflows/?categories=AI). From each workflow, select the **Use workflow** button to automatically import it into your n8n instance.

### Learn AI Key Concepts (Examples from n8n.io)

- [AI Agent Chat](https://n8n.io/workflows/1954-ai-agent-chat/)
- [AI chat with any data source (using the n8n workflow tool)](https://n8n.io/workflows/2026-ai-chat-with-any-data-source-using-the-n8n-workflow-tool/)
- [Chat with OpenAI Assistant (by adding a memory)](https://n8n.io/workflows/2098-chat-with-openai-assistant-by-adding-a-memory/)
- [Use an open-source LLM (via HuggingFace)](https://n8n.io/workflows/1980-use-an-open-source-llm-via-huggingface/)
- [Chat with PDF docs using AI (quoting sources)](https://n8n.io/workflows/2165-chat-with-pdf-docs-using-ai-quoting-sources/)
- [AI agent that can scrape webpages](https://n8n.io/workflows/2006-ai-agent-that-can-scrape-webpages/)

### AI Templates (Examples from n8n.io)

- [Tax Code Assistant](https://n8n.io/workflows/2341-build-a-tax-code-assistant-with-qdrant-mistralai-and-openai/)
- [Breakdown Documents into Study Notes with MistralAI and Qdrant](https://n8n.io/workflows/2339-breakdown-documents-into-study-notes-using-templating-mistralai-and-qdrant/)
- [Financial Documents Assistant using Qdrant and MistralAI](https://n8n.io/workflows/2335-build-a-financial-documents-assistant-using-qdrant-and-mistralai/)
- [Recipe Recommendations with Qdrant and Mistral](https://n8n.io/workflows/2333-recipe-recommendations-with-qdrant-and-mistral/)

## Tips & Tricks

### Accessing Files on the Server

The installer creates a `shared` folder (by default, located in the same directory where you ran the installation script). This folder is accessible by the n8n application.
When you build automations in n8n that need to read or write files on your server, use the path `/data/shared` inside your n8n workflows. This path in n8n points to the `shared` folder on your server.

**n8n components that interact with the server's filesystem:**

- [Read/Write Files from Disk](https://docs.n8n.io/integrations/builtin/core-nodes/n8n-nodes-base.filesreadwrite/)
- [Local File Trigger](https://docs.n8n.io/integrations/builtin/core-nodes/n8n-nodes-base.localfiletrigger/) (To start workflows when files change)
- [Execute Command](https://docs.n8n.io/integrations/builtin/core-nodes/n8n-nodes-base.executecommand/) (To run command-line tools)

## 🙌 Contributors

Want to see who has contributed to this project? Check out the [**GitHub Contributors Page**](https://github.com/kossakovsky/n8n-installer/graphs/contributors)!

## 📜 License

This project (originally created by the n8n team, with further development by contributors - see "Important Links") is licensed under the Apache License 2.0. See the [LICENSE](LICENSE) file for details.
