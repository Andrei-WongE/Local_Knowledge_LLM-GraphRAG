# Local Knowledge Base using RAG for local LLM
------------------------------------------------------

## 1) Objective:
Create a local knowledge base from a curated set of PDFs. Interest is in finding specific conceptual entities/relationships within and between documents.

## 2) Problem:
Local hardware has 32GB RAM, Intel Iris Xe and no dedicated GPU.

## 3) Solution:
1st CONCEPT: PDF curation [Zotero] → Export → Local PDF extraction [OlmoCR] → Cloud GPU indexing [Lambda Labs] → Local querying [qwen2.5:7b-instruct]

1st IMPLEMNTATION:
| Objective | Main Tool | Pipeline | Tokens per sec | Run time | Cost | Evaluation |
|-----------|-----------|----------|----------------|------------|------------|------------|
| Simple, integrated| AnythingLLM          | 60 PDFs insert → Lance DB → nomic-embed-text → llama3.1:8b-instruct-q4_K_M         |       2.4         | 18h 37 min           | $0  | Extreemly slow and low complexity of anwsers
| Simple, sequential          |  GPT4All         | 60 PDFs insert → PaperMage → ChroneDB → GPT4All → Phi-3.5-MoE-instruct-Q3_K_M           |                |            |           |             |
|           |           |      Vectorless-Reasoning-based RAG    |                |            |           |             |     
|           |           |  Graph RAG         |                |            |           |             |
|           |           |     PageIndex Reasoning-based RAG     |                |            |           |             |
| Extremly simple, semi-integrated   | NotebookLM MCP      | 60 PDFs insert → NotebookLM RAG → NotebookLM MCP → Gemini CLI + Co-Research Agent   |                218   |            |    Tokens cost       |  Easy set-up and reliable answers       |
| Extremly simple, semi-integrated   | NotebookLM MCP      | 60 PDFs insert → NotebookLM RAG → NotebookLM MCP → Gemini CLI + Co-Research Agent + Obsidian vault as shared memory for agents |                218   |            |    Tokens cost       |  Easy set-up, agentic tasks and reliable answers       |
## 4) Cost:
~$5-7 total
