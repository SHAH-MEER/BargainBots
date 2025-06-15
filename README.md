## 📖 Project Overview
**BargainBots** is an advanced AI-powered system designed to discover, analyze, and recommend the best online deals in real time. The platform leverages a pipeline of collaborative agents, combining the strengths of Large Language Models (LLMs), traditional machine learning models, embeddings, and retrieval-augmented generation (RAG) for robust, accurate, and scalable deal processing.

The system is modular, extensible, and production-grade, with support for cloud-native deployment (Modal), CI/CD, and automated documentation. BargainBots is suitable for e-commerce, price comparison, and deal aggregation platforms.

---

## ✨ Features
- **Multi-Agent Pipeline:** Specialized agents for deal scanning, price prediction (XGBoost, fine-tuned LLMs), filtering, and orchestration.
- **Real-Time Deal Fetching:** Continuously monitors online sources for new deals.
- **Hybrid AI:** Combines LLMs, classic ML, and RAG for best-in-class accuracy.
- **Memory & Deduplication:** Avoids duplicate recommendations using memory modules.
- **Remote Execution:** Supports Modal for scalable, serverless execution.
- **Live Activity Logs:** Monitor agent activity and pipeline progress in real time.
- **Modern DevOps:** Dockerized, CI/CD with GitHub Actions, pre-commit hooks, and code quality enforcement.
- **Testing & Security:** Built-in unit testing and security checks.
- **Auto-Docs:** Generates changelogs and documentation with LLMs and MkDocs.
- **User Interface:** Clean UI for monitoring, configuration, and manual deal review.

---

## 🏗️ Architecture Overview
```
[Deal Sources] → [Deal Scanner Agent] → [Central Orchestrator] → [Price Agents (LLM/ML/RAG)] → [Filter/Memory] → [UI/API]
```

---

## 🚀 Deploying on Hugging Face Spaces

You can deploy BargainBots on [Hugging Face Spaces](https://huggingface.co/spaces) for free, using Gradio or Docker. Here’s how:

### Requirements
- `main.py` (entry point, launches Gradio app)
- `requirements.txt` (all dependencies listed)
- (Optional) `Dockerfile` for custom environments
- `README.md` (project info)

### Steps
1. **Push your code to a public GitHub repository.**
2. **Create a new Space:**
   - Go to [Hugging Face Spaces](https://huggingface.co/spaces).
   - Click "Create new Space".
   - Choose Gradio (or Docker if you have a custom Dockerfile).
   - Fill in the details and link your GitHub repo or upload files directly.
3. **Configure hardware:**
   - Select CPU or GPU as needed (GPU for LLMs/ML models).
4. **App launch:**
   - Hugging Face will auto-detect `main.py` or `app.py`.
   - The app should listen on port `7860` (default for Gradio).
5. **Wait for build & launch:**
   - The Space will build and deploy automatically.
   - Access your app at the provided Space URL.

### Example `requirements.txt`
```
gradio
modal
openai
requests
# ...other dependencies
```

### Example `main.py`
```python
from src.ui.gradio_app import build_ui

demo = build_ui()

demo.launch(server_name="0.0.0.0", server_port=7860)
```

### Tips
- Use a GPU Space for faster inference if you use LLMs or heavy ML models.
- Check the Hugging Face logs if the app fails to launch.
- For private Spaces, upgrade your Hugging Face account.

---
- **Deal Scanner Agent:** Scrapes and ingests deals from various sources.
- **Central Orchestrator:** Coordinates specialized agents and manages the pipeline.
- **Price Agents:** Use XGBoost, fine-tuned LLMs, and RAG for price prediction.
- **Filter/Memory:** Filters out duplicates and manages deal memory.
- **UI/API:** Presents results and allows user interaction.

---

## ⚙️ Setup & Installation

### Prerequisites
- Python 3.9+
- Docker (for containerized deployment)

### Local Setup
```bash
git clone https://github.com/SHAH-MEER/BargainBots.git
cd BargainBots
pip install -r requirements.txt
```

### Running the App
- **CLI:**
    ```bash
    python main.py
    ```
- **Docker:**
    ```bash
    docker build -t bargainbots .
    docker run -p 7860:7860 bargainbots
    ```

---

## 🚀 Usage
- Launch the app and access the UI at `http://localhost:7860` (if using Docker or Gradio UI).
- Configure agent parameters in the UI or via config files in `src/config/`.
- Monitor logs and results in real time.
- Extend or add agents by modifying files in `src/agents/`.

---

## 🤝 Contributing
Pull requests are welcome! For major changes, please open an issue first to discuss what you would like to change.

- Fork the repo and create your branch from `main`.
- Ensure code passes all tests and lints.
- Add/Update documentation as needed.

---

## 🪪 License

MIT
