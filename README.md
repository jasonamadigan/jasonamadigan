# Jason | Practical AI Experiments

I'm an engineer with over 20 years in the network infrastructure and automation space. These days, I’m mostly interested in figuring out where AI actually helps in a production environment and where it's just hype.

I’m using GitHub to document my experiments while I try to explore practical use cases for AI in production environments. I use a combination of cloud and local infrastructure throughout the projects to simulate potential environments and to help me learn the advantages and drawbacks of each.

---

### 📂 Recent Projects
These are a few proof-of-concept projects where I’m testing AI’s practical limits in DevOps and networking. I worked with both Claude and Gemini to brainstorm the project ideas and used Claude Code and Gemini-CLI to write the bulk of the code.

* **Self-Healing Pipeline**: A small agent that monitors CloudWatch logs and tries to fix common errors using Ansible. I included guardrails like dry-run modes because I'm not ready to trust autonomous agents with a production environment just yet. I chose to use AWS here to become more familiar with the ecosystem through a practical use case.

* **Runbook Assistant**: A basic local RAG setup using LangGraph I built to query my own markdown notes on how to configure various network devices. This simulates a scenario with strict operational requirements where we want the LLM to return deterministic results. This project is geared toward a chatbot scenario, but the same concept could be used anywhere you want the LLM to be grounded to specific data.

* **RAG vs. Fine-Tuning**: A side-by-side comparison to see if fine-tuning a model (Mistral 7B) is actually worth the effort compared to a standard RAG setup. I ran this locally on an AMD 7900 XTX to keep the data private, simulating the privacy constraints many businesses prefer. The results were unexpected and gave me a much better understanding of what fine-tuning is actually for.

* **Config Auditor**: A multi-step flow using LangGraph to see if an LLM can reliably spot security holes in network configs before they get deployed. While LangChain worked for basic RAG, it became evident quickly that branching or looping workflows required LangGraph for this type of use case.

* **Hardware Benchmarking**: I developed Python telemetry tools to baseline CPU/GPU utilization and token-generation velocity for local LLM inference. This suite measures tok/s, latency, and thermals specifically for an AMD 7900 XTX using the ROCm stack, helping me understand the actual hardware cost of inference beyond just the "it works" stage.

* **Applied Inference & RAG**: I built and containerized a local inference cluster using K3s, Docker, and FastAPI. I used this infrastructure to deploy a secure, local RAG pipeline (LangChain and ChromaDB) for querying operational runbooks. This simulates an environment with strict operational and privacy requirements where data cannot leave the local network.

---

### 🛠️ Development Stack

#### 💻 Core Technologies
* **Languages:** `Python`
* **AI Frameworks:** `LangChain`, `LangGraph`, `PyTorch`, `Ollama`
* **Automation:** `Ansible`, `Docker`, `K3s`

#### 🏗️ Infrastructure & Compute
* **Local Environment:** Linux/Windows running on an AMD Radeon™ RX 7900 XTX
* **Driver Stack:** ROCm™ (Radeon Open Compute)
* **Cloud Environment:** AWS (EC2, CloudWatch, IAM)
