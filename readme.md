# T.R.A.C.E. Core 
**Temporal Real-time Analysis & Concurrent Engine**

[![Thesis](https://img.shields.io/badge/-Thesis-blue.svg)](#)
[![Build Status](https://img.shields.io/badge/build-passing-brightgreen.svg)](#)
[![Python 3.10+](https://img.shields.io/badge/python-3.10+-blue.svg)](#)
[![Node.js](https://img.shields.io/badge/node.js-v18+-green.svg)](#)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

> **A Scalable Full-Stack Framework for Temporal Behavioral Modeling and Concurrent NLP in Real-Time Systems.**

T.R.A.C.E. is an event-driven intelligence core designed to extract temporal behavioral metrics and run concurrent NLP on real-time data streams. It completely decouples heavy machine learning inference from high-speed WebSockets, allowing for deep psychological and conversational analytics without bottling up the main web server.

---

## 🚀 Core Features

* **Event-Driven Decoupling:** Isolates the I/O layer (Node.js/WebSockets) from the compute layer (Python/NLP) using an asynchronous message broker.
* **Concurrent NLP Pipeline:** Processes live text simultaneously through VADER (lexical speed) and DistilBERT (contextual depth).
* **Temporal Behavioral Modeling:** Moves beyond static sentiment analysis by mapping response latency, interest shifts, and conversation dominance in real-time.

---

## 🧮 The Mathematics of Temporal Decay

Standard NLP treats messages as isolated strings. This engine factors in *time*. The system calculates real-time Engagement and Dominance scores, along with the **Ghosting Probability**, which is modeled as a temporal decay function:

$$P_g(t) = 1 - e^{-\lambda (t - t_{last})}$$

Where $\lambda$ represents the baseline latency decay constant for the specific user interaction, continuously updating as the conversation flows.

---

## 🏗️ System Architecture

1. **Presentation Layer:** React.js frontend visualizing real-time temporal metrics.
2. **I/O Gateway:** Node.js/Express server handling high-throughput WebSocket connections.
3. **Event Broker:** Apache Kafka (or Redis Pub/Sub) buffering payloads to prevent thread-blocking.
4. **Compute Tier:** Python (FastAPI) microservices executing multi-threaded VADER and DistilBERT inference.
5. **Storage:** MongoDB for unstructured chat persistence, paired with a Time-Series Database for rapid analytics retrieval.

---

## 💻 Tech Stack

* **Frontend:** React, TailwindCSS, Chart.js
* **Backend (I/O):** Node.js, Express, Socket.io
* **Message Broker:** Apache Kafka
* **AI/Compute:** Python, FastAPI, HuggingFace Transformers (DistilBERT), NLTK (VADER)
* **Database:** MongoDB, InfluxDB (Time-Series)

---