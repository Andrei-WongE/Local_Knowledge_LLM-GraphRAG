# Local Knowledge Base using GraphRAG for local LLM
------------------------------------------------------

## 1) Objective:
Create a local knowledge based of a curated set of corpus of PDFs. Interest is in finding specific conceptual entities/relationships within and between documents.

## 2) Problem:
Local hardware has 32GB RAM, Intel Iris Xe and no dedicated GPU.

## 3) Solution:
PDF curation [Zotero] → Export → Local PDF extraction [OlmoCR] → Cloud GPU indexing [Lambda Labs] → Local querying [qwen2.5:7b-instruct]

## 4) Cost:
~$5-7 total
