# 🌤️ Weather AI Agent: Multi-Step Reasoner with Claude 4.5 & Bedrock
###  Developed during the BeSA Q1 2026 Cohort - Week 2: Agentic Building Blocks

# 🎯 Project Overview
This project implements an autonomous **Weather AI Agent** that leverages the reasoning capabilities of **Anthropic Claude 4.5 Sonnet** on **Amazon Bedrock**. Unlike a simple chatbot, this agent performs a multi-step "Plan-Execute-Summarize" workflow to interact with the real-world National Weather Service (NWS) API.

# 🧠 Why is this "Agentic"?
This assistant goes beyond standard automation by exhibiting three core agentic traits:
- **Autonomy**: It independently interprets location descriptions (e.g., "largest city in California") and dynamically constructs API strategies without hardcoded templates.
- **Reactivity**: It adapts to its environment, handling variable API response structures, network timeouts, and inconsistent weather data formats.
- **Proactivity**: It takes initiative by resolving coordinates first, then sequentially executing the Points-to-Forecast pipeline to deliver a polished insight.

# 🏗️ The Agentic Workflow
The agent follows a 6-step cognitive process:
1. **Planning**: AI identifies the location and generates the correct NWS Points API URL.
2. **Action (Points)**: The agent executes a `curl` command to fetch regional metadata.
3. **Extraction**: The agent parses the JSON to find the specific "Forecast URL" for that grid.
4. **Action (Forecast)**: The agent fetches the raw meteorological data.
5. **Processing**: AI converts complex JSON forecast data into a human-readable summary.
6. **Response**: The agent presents a professional, formatted weather outlook.

# 🔑 Core Patterns & Skills Gained
- **Agentic Workflows**: Mastering the Input → Plan → Execute → Process → Response loop.
- **Advanced Prompt Engineering**: Teaching the AI to handle ambiguous input and request specific formats for downstream processing.
- **Error-Resilient Architecture**: Implementing logic that handles network failures and unexpected data gracefully.
- **AWS Bedrock Mastery**: Hands-on integration with `Claude 4.5 Sonnet`, including inference parameter tuning and `boto3` runtime management.

# 🛠️ Technical Stack
- **Orchestrator**: `Amazon Bedrock (Claude 4.5 Sonnet)`.
- **Runtime**: `Python 3.x` with `boto3` (`AWS SDK`).
- **Interface**: `weather_agent_cli.py`: Command-line interface with step-by-step tracing.
- `weather_agent_web.py`: Interactive web dashboard built with `Streamlit`.
- **Integration**: Subprocess-based `curl` for secure API communication.

# 🚀 Future Roadmap
- **Multi-Agent Systems**: Creating a "Travel Agent" that coordinates with this Weather Agent.
- **Memory Integration**: Storing previous queries to learn and personalise user patterns.
- **Production Scaling**: Deploying the agent logic as an AWS Lambda-based microservice.

# 📸 Implementation Proof
To demonstrate the full agentic lifecycle, below are the visual walkthroughs of the configuration and execution phases.

**Step 1: CLI Agentic Trace**
- *This trace follows the terminal output of `weather_agent_cli.py` during a live query.*
1. [Initial User Input & AI Planning Phase](./screenshots/cli_trace_1.png)
2. [Complete Analysis & Forecast](./screenshots/cli_trace_2.png)
3. [Weekend Weather Forecast Output](./screenshots/cli_trace_3.png)
4. [Location description (tests AI reasoning)](./screenshots/cli_trace_4.png)
5. [Descriptive query (tests knowledge-based location finding)](./screenshots/cli_trace_5.png)

**Step-2: Streamlit Web UI**
- *Visualising the `weather_agent_web.py` dashboard and its transparent reasoning process.*
1. [Dashboard Landing: Title, Sidebars, and Model Info](./screenshots/web_ui_1.png)
2. [Input Trigger: Location entry and "Get Weather" action](./screenshots/web_ui_2.png)
3. [Sidebar Detail: "About the Agent" & Architecture workflow](./screenshots/web_ui_3.png)
4. [Step Containers: Visual Success Boxes for Planning & Execution](./screenshots/web_ui_4.png)
5. [Descriptive query (tests knowledge-based location finding)](./screenshots/web_ui_5.png)

**Note**: *This project was developed as part of the BeSA (Agentic AI on AWS) program*.


