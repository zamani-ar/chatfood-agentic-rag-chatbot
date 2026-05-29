# 🍔 ChatFood — Agentic Food Ordering Chatbot with LangGraph

An intelligent food-ordering and food-assistant chatbot built using `LangGraph`, `LangChain`, and `Gemini`.

The system supports:

* Food-related question answering using RAG
* Hybrid retrieval from vector database + internet
* Restaurant and food price search
* Order management (cancel / status / comments)
* AI-powered food recommendation
* Tool-calling agents with LangGraph workflows

---

# Features

## ✅ Food-related Query Detection

The chatbot first determines whether a user query is related to food and restaurants.

* Food-related → continue processing
* Non-food-related → politely reject the request

---

## ✅ Retrieval-Augmented Generation (RAG)

The system retrieves information from:

1. Internal food knowledge base (vector database)
2. Internet search (fallback using Tavily)

The retrieved context is filtered before answer generation to improve response quality.

### Workflow

```text
User Query
   ↓
Food-related?
   ↓
Retrieve from database
   ↓
If insufficient → Search Internet
   ↓
Filter relevant context
   ↓
Generate final response
```

---

## ✅ Order Management

The chatbot can:

* Cancel orders
* Check order status
* Add/update comments for orders

The system automatically extracts the intended user action from natural language queries.

Example:

```text
"Can you cancel my order?"
"What is the status of order 152?"
"I want to leave a comment for my order."
```

---

## ✅ Food Search

Supports:

* Search by food name
* Search by restaurant
* Search by both restaurant and food name

Examples:

```text
"How much is pepperoni pizza?"
"What foods does Milad restaurant have?"
"Price of burger in Star Restaurant?"
```

---

## ✅ AI Food Recommendation System

The chatbot can recommend foods based on user preferences.

Examples:

```text
"I want something spicy and fast food."
"Suggest healthy Iranian food."
"I want a cheesy dinner."
```

The system:

1. Generates candidate foods using the LLM
2. Checks database availability
3. Returns available foods with pricing information
4. Generates alternative suggestions if needed

---

# Tech Stack

## Frameworks & Libraries

* LangGraph
* LangChain
* Gemini 1.5 Flash
* Tavily Search API
* Pydantic
* Python

## Concepts Used

* Agentic AI
* Tool Calling
* Retrieval-Augmented Generation (RAG)
* Structured Output Generation
* State Machines
* Multi-step LLM Workflows
* Conversational AI

---

# Architecture

The chatbot is implemented using a graph-based workflow with `LangGraph`.

## Main Components

### 1. Relatedness Detection

Determines whether the query belongs to the food domain.

### 2. Knowledge Retrieval

Retrieves information from:

* Vector database
* Internet search

### 3. Context Filtering

Removes irrelevant retrieved information.

### 4. Final Answer Generation

Generates concise responses using filtered context.

### 5. Tool Calling Agent

Handles:

* Order management
* Food search
* Food recommendation

---

# Example Workflow

```text
User:
"I want spicy fast food."

↓
LLM generates candidate foods

↓
Database search for availability

↓
Filter available foods

↓
Return recommendation + pricing
```

---

# Running the Project

## Install Dependencies

```bash
pip install -r requirements.txt
```

## Set API Keys

Create a `.env` file:

```env
GOOGLE_API_KEY=your_key
TAVILY_API_KEY=your_key
LLAMA_API_KEY=your_key
```

## Run

```bash
python main.py
```

---

# Future Improvements

* Better memory handling
* Streaming responses
* Cleaner modular architecture
* Docker support
* Web interface
* Better retrieval ranking
* Persistent vector database
* Multi-agent planning

---

# Project Motivation

This project was developed as an exploration of:

* Agentic LLM systems
* LangGraph workflows
* Tool-using AI assistants
* RAG pipelines
* Conversational food-ordering systems

---

# Disclaimer

This project is primarily educational/research-oriented and may still contain experimental or non-production-ready components.
