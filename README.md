# LangGraph Agent Deployment

This repository contains the source code for a LangGraph agent deployed
to **LangGraph Cloud**.\
The LangGraph Platform builds, hosts, and manages the agent from this
repository.

## Project Structure

    .
    ├── langgraph.json          # Defines the graph ID and entrypoint for LangGraph Cloud
    ├── pyproject.toml          # Project dependencies
    ├── src/                    # Agent source code
    │   └── agent/
    │       └── graph.py        # Main LangGraph graph definition
    ├── static/                 # Static assets (optional)
    └── tests/                  # Unit tests (optional)

## Running the Agent Locally

Before deploying, you can run the agent locally for testing.

### Install Dependencies

``` bash
pip install --upgrade "langgraph-cli[inmem]"
pip install -e .
```

### Start Local LangGraph Server

``` bash
langgraph dev
```

Local server will start at:

    http://localhost:2024

LangGraph Studio will be available at the URL printed in the terminal.

## Deploying to LangGraph Cloud

This repository is configured for deployment using **LangGraph Cloud**.

### Deployment Steps

1.  Go to **LangGraph Platform → Deployments**
2.  Click **New Deployment**
3.  Choose:
    -   Repository: `mrishav/langgraph-deployment`
    -   Branch: `main`
4.  Deploy

LangGraph Cloud will automatically build and host the agent.

## Updating the Deployment

To update the deployment:

``` bash
git add .
git commit -m "Update agent"
git push origin main
```

Pushing to `main` triggers a new deployment.
