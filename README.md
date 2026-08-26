# 🐋 Automated Containerization Pipeline

A lightweight, production-ready web server container setup built using Docker and Nginx. This repository demonstrates automated infrastructure configuration and cloud-based verification testing.

```mermaid
graph LR
    subgraph Local Workspace [💻 Local Environment (WSL2)]
        A[index.html] -->|Packaged By| B(Dockerfile)
        B -->|Local Test| C(Docker Engine)
    end

    subgraph Version Control [🌐 GitHub Cloud]
        D[git push] -->|Triggers| E{GitHub Actions CI}
    end

    subgraph Automated Runner [⚡ Cloud Virtual Machine]
        E -->|Spins Up| F[Ubuntu Runner]
        F -->|Executes| G[docker build]
        G -->|Result| H[✅ Verified Image]
    end

    C -.->|Synced Via| D
    Local Workspace -->|Code Upload| Version Control
    Version Control -->|Pipeline Execution| Automated Runner

    style E fill:#f9f,stroke:#333,stroke-width:2px
    style H fill:#bbf,stroke:#333,stroke-width:2px
```

## 🛠️ Tech Stack
* **Container Engine:** Docker Desktop (WSL 2 Integration)
* **Automation Engine:** GitHub Actions (CI/CD Pipeline)
* **Base Web Server:** Nginx (Alpine Linux distro)

## 🚀 How to Run It Locally

1. **Build the Docker Image:**
   ```bash
   docker build -t my-first-web-app .
   ```

2. **Launch the Container:**
   ```bash
   docker run -d -p 8080:80 my-first-web-app
   ```

3. **Access the Application:**
   Open your browser and navigate to `http://localhost:8080`

