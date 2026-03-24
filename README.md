# PathPlan AI Backend: Agentic Reasoning Engine

The PathPlan AI backend is a high-performance FastAPI application that powers the "Agentic Career Decision Engine." It utilizes a multi-agent orchestration layer to analyze professional profiles, fetch external presence data, and simulate strategic debates to generate realistic career roadmaps.

---

## 🧠 Multi-Agent Architecture

The backend is built on a modular agentic framework where specialized agents collaborate to process data:

* **Resume Parser Agent**: Extracts structured capability signals from PDF resumes using `PyMuPDF` and LLM-based entity extraction.

* **Capability Agent**: Evaluates the user's current skill set against target roles to generate readiness scores and gap analyses.

* **Professional Presence Agent**: Orchestrates data fetching from GitHub and LinkedIn to assess market visibility.

* **Orchestrator Agent**: Manages the "debate" logic between agents to ensure career decisions are grounded in realism rather than hype.

* **Route Planner Agent**: Generates the final, month-by-month adaptive roadmap based on the outcome of agent debates.

---

## 🛠️ Tech Stack

* **Framework**: FastAPI

* **Orchestration**: LangChain

* **LLM Provider**: Groq (Llama-3 models)

* **Data Handling**: Pydantic for schema validation and JSON for opportunity storage

* **Environment**: Python 3.10+

---

## 🚀 Getting Started

### Prerequisites

* Python 3.10 or higher

* A valid API Key for Groq (configured in environment variables)

### Installation

1\.  **Clone and Navigate**:

    ```bash

    cd PathPlanAI-backend

    ```

2\.  **Create Virtual Environment**:

    ```bash

    python -m venv venv

    source venv/bin/activate  # Windows: venv\Scripts\activate

    ```

3\.  **Install Dependencies**:

    ```bash

    pip install -r requirements.txt

    ```

### Running the Server

Start the development server with Uvicorn:

```bash

uvicorn app.main:app --reload

The API will be available at `http://localhost:8000` with interactive Swagger docs at `/docs`.

* * * * *

📡 Key API Endpoints

--------------------

| **Endpoint** | **Method** | **Description** |

| --- | --- | --- |

| `/upload-resume` | `POST` | Parses PDF resumes and extracts capability signals. |

| `/planner/` | `POST` | Initiates agentic debate and generates a career roadmap. |

| `/professional-insight` | `POST` | Analyzes GitHub and LinkedIn profiles for market readiness. |

| `/opportunities` | `POST` | Matches user capabilities against current market trends. |

* * * * *

📂 Project Structure

--------------------

-   **`app/agents/`**: Core logic for specialized AI agents.

-   **`app/routes/`**: FastAPI route definitions for frontend integration.

-   **`app/core/`**: LLM client configuration and model management.

-   **`data/`**: Storage for market trend data and temporary resume uploads.
