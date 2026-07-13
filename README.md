# LangSmith

## 📖 Overview

**LangSmith** is a platform developed by **LangChain** for **debugging, testing, evaluating, and monitoring** AI applications. It helps developers understand how their LLM applications work internally by recording every step of execution.

Whether you're building applications with **LangChain**, **LangGraph**, or another LLM framework, LangSmith provides detailed insights into your application's behavior.

> **Think of LangSmith as the "DevTools" for AI applications.**

---

# Why Use LangSmith?

AI applications often involve multiple components working together:

- User Input
- Prompt Templates
- LLM Calls
- Tools
- APIs
- Databases
- Retrievers (RAG)
- Memory
- Agents

If something goes wrong, it can be difficult to identify the source of the problem.

LangSmith records every step, making debugging and optimization much easier.

---

# Key Features

## 1. Tracing

Tracing records the complete execution of your AI application.

Example:

```text
User
  │
  ▼
Prompt
  │
  ▼
LLM
  │
  ▼
Tool
  │
  ▼
Retriever
  │
  ▼
LLM
  │
  ▼
Response
```

Each execution is stored as a **Trace**.

Tracing helps you inspect:

- Inputs
- Outputs
- Prompts
- Tool Calls
- LLM Responses
- Execution Time
- Errors

---

## 2. Debugging

LangSmith makes debugging AI applications easier.

Without LangSmith:

```
Wrong Answer
     │
     ▼
Guess where the problem occurred.
```

With LangSmith:

```
Wrong Answer
     │
     ▼
Open Trace
     │
     ▼
Find the exact step causing the error.
```

You can determine whether the issue comes from:

- Prompt
- LLM
- Tool
- API
- Retriever
- Memory

---

## 3. Prompt Testing

Different prompts produce different results.

Example:

Prompt A

```
Explain AI.
```

Prompt B

```
Explain Artificial Intelligence in simple words with examples.
```

LangSmith allows you to compare:

- Response Quality
- Accuracy
- Token Usage
- Cost
- Latency

---

## 4. Evaluation

Evaluation measures how well your AI application performs.

Example metrics include:

- Correctness
- Relevance
- Helpfulness
- Faithfulness
- Hallucination Detection
- Similarity to Expected Output

Example:

```
Question
      │
      ▼
Expected Answer
      │
      ▼
Model Answer
      │
      ▼
Evaluation Score
```

---

## 5. Monitoring

Once deployed, LangSmith continuously monitors your application.

It tracks:

- Errors
- Failed Requests
- Slow Responses
- Token Usage
- API Cost
- User Activity

Monitoring helps maintain application quality in production.

---

## 6. Dataset Management

Datasets are collections of test examples.

Example:

| Question | Expected Answer |
|-----------|-----------------|
| Capital of France? | Paris |
| 5 + 7 | 12 |
| Largest Ocean | Pacific Ocean |

These datasets can be used to evaluate your application automatically.

---

## 7. Experiment Tracking

LangSmith helps compare different versions of your application.

Example:

```
Version 1
Accuracy: 82%

↓

Version 2
Accuracy: 91%
```

This makes it easier to identify improvements after changing prompts or models.

---

# Core Concepts

## Project

A project groups all traces, datasets, and experiments for a single AI application.

Example:

- Customer Support Bot
- Medical Assistant
- PDF Chatbot
- Travel Planner

---

## Trace

A **Trace** is the complete execution of one user request.

Example:

```
User Question
      │
      ▼
Prompt
      │
      ▼
LLM
      │
      ▼
Tool
      │
      ▼
Retriever
      │
      ▼
Final Response
```

---

## Run

A **Run** is a single operation inside a trace.

Example:

```
Trace
 ├── Prompt Run
 ├── LLM Run
 ├── Tool Run
 ├── Retriever Run
 └── Output Run
```

---

## Dataset

A dataset contains multiple test examples used for evaluation.

---

## Evaluation

Evaluation measures application quality using predefined or custom metrics.

---

# LangSmith Workflow

```text
User
   │
   ▼
AI Application
   │
   ▼
LangSmith Records Everything
   │
   ▼
Developer Dashboard
   │
   ├── View Traces
   ├── Debug Errors
   ├── Evaluate Outputs
   ├── Compare Prompts
   └── Monitor Performance
```

---

# LangSmith Architecture

```text
                User
                  │
                  ▼
        AI Application
   (LangChain/LangGraph)
                  │
                  ▼
           LangSmith SDK
                  │
                  ▼
      LangSmith Cloud Platform
                  │
      ┌───────────┼────────────┐
      ▼           ▼            ▼
   Tracing    Evaluation   Monitoring
                  │
                  ▼
       Developer Dashboard
```

---

# LangSmith with LangChain

```text
User
   │
   ▼
Chain
   │
   ▼
Prompt
   │
   ▼
LLM
   │
   ▼
Parser
   │
   ▼
Response

↓

Everything is recorded by LangSmith.
```

---

# LangSmith with LangGraph

```text
User
   │
   ▼
Graph
   │
   ▼
Node A
   │
   ▼
Conditional Edge
   │
   ▼
Node B
   │
   ▼
Tool Node
   │
   ▼
Memory
   │
   ▼
Final Response

↓

Entire graph execution is stored as a Trace.
```

---

# Typical Development Workflow

```text
Build AI Application
          │
          ▼
Connect LangSmith
          │
          ▼
Run Application
          │
          ▼
Inspect Traces
          │
          ▼
Fix Bugs
          │
          ▼
Evaluate Results
          │
          ▼
Optimize Prompts
          │
          ▼
Deploy
          │
          ▼
Monitor Production
```

---

# Advantages of LangSmith

- Easy debugging
- Complete execution traces
- Prompt comparison
- Automatic evaluations
- Performance monitoring
- Token usage tracking
- Cost analysis
- Experiment management
- Production observability
- Supports LangChain and LangGraph

---

# Real-World Example

Imagine you're building a **customer support chatbot**.

A user asks:

> "Where is my order?"

The chatbot:

1. Receives the user's question.
2. Searches the order database.
3. Calls an API to fetch order details.
4. Uses an LLM to generate a response.
5. Sends the answer back.

If the chatbot gives the wrong answer, LangSmith allows you to inspect every step and determine whether the problem was caused by:

- The prompt
- The retrieved data
- The API response
- The tool
- The LLM

This makes debugging much faster and improves application reliability.

---

# Common Use Cases

- AI Chatbots
- AI Agents
- RAG Applications
- Multi-Agent Systems
- Customer Support Bots
- Document Q&A
- Healthcare AI
- Financial AI
- Coding Assistants
- Workflow Automation

---

# Key Terms

| Term | Description |
|------|-------------|
| **LangSmith** | Platform for debugging, evaluating, and monitoring AI applications |
| **Project** | Collection of traces, datasets, and experiments |
| **Trace** | Complete execution of a single user request |
| **Run** | One individual operation inside a trace |
| **Dataset** | Collection of test examples |
| **Evaluation** | Measuring application quality |
| **Monitoring** | Tracking production performance |
| **Experiment** | Comparing prompts, models, or application versions |

---

# Summary

LangSmith is a powerful developer platform for building reliable AI applications. It provides **tracing**, **debugging**, **evaluation**, **monitoring**, and **experiment tracking**, allowing developers to understand every step of an AI application's execution. By integrating LangSmith with LangChain or LangGraph, developers can improve application quality, reduce debugging time, and confidently deploy AI systems into production.
