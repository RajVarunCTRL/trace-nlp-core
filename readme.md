# T.R.A.C.E. Core

### Temporal Real-Time Analysis & Concurrent Engine

<div align="center">

[![Python 3.11](https://img.shields.io/badge/Python-3.11-3776AB?style=for-the-badge&logo=python&logoColor=white)](#)
[![Node.js](https://img.shields.io/badge/Node.js-18+-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)](#)
[![React](https://img.shields.io/badge/React-Vite-61DAFB?style=for-the-badge&logo=react&logoColor=0b1f33)](#)
[![Kafka](https://img.shields.io/badge/Kafka-Aiven-231F20?style=for-the-badge&logo=apachekafka&logoColor=white)](#)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)

**A scalable event-driven framework for real-time conversational analytics and temporal behavioral modeling.**

</div>

T.R.A.C.E. Core decouples high-speed WebSocket communication from CPU-intensive natural language processing. Messages are delivered immediately, while sentiment analysis and behavioral telemetry run asynchronously through Apache Kafka.

---

## System Overview

```text
React / Vite
      |
      | Socket.IO
      v
Node.js Transport Service ---- MongoDB Atlas
      |
      | chat-messages
      v
Aiven Apache Kafka
      |
      | consumer
      v
Python Intelligence Service ---- InfluxDB Cloud
      |
      | behavioral-metrics
      v
Aiven Apache Kafka
      |
      | metrics_update
      v
Live React Telemetry Dashboard
```

---

## Core Features

- **Real-Time Chat:** Room-based Socket.IO message delivery
- **Asynchronous Processing:** Kafka decouples transport latency from NLP inference
- **Sentiment Analysis:** Weighted VADER and DistilBERT ensemble
- **Privacy Pipeline:** spaCy PERSON detection with email, phone, and ID masking
- **Temporal Metrics:** Engagement, dominance, ghosting, and sentiment velocity
- **Advanced Analytics:** Volatility, reciprocity, lexical diversity, and interaction graphs
- **Cloud Infrastructure:** Aiven Kafka, MongoDB Atlas, and InfluxDB Cloud
- **Live Dashboard:** React and Recharts telemetry visualization

---

## Technology Stack

| Layer | Technologies |
|---|---|
| Frontend | React, Vite, Tailwind CSS, Socket.IO Client, Recharts |
| Transport | Node.js, Express, Socket.IO, KafkaJS, Mongoose |
| Intelligence | Python 3.11, FastAPI, aiokafka, NLTK VADER, DistilBERT |
| Privacy | spaCy, regex fallbacks |
| Event Broker | Apache Kafka on Aiven |
| Data Stores | MongoDB Atlas, InfluxDB Cloud |
| Benchmarking | Locust, Matplotlib |

---

## Temporal Metrics

### Engagement Score

An exponentially weighted score combining sentiment, message effort, and response speed.

### Dominance Index

A rolling measure based on word contribution, message frequency, and consecutive floor-holding bursts.

### Ghosting Probability

Modeled using exponential temporal decay:

```text
P_g(t) = 1 - e^(-lambda * delta_t)
```

where `delta_t` represents the silence duration since the latest room message.

---

## Data Flow

1. A React client sends a chat message through Socket.IO.
2. The transport broadcasts it immediately to the room.
3. The transport persists the message in MongoDB Atlas.
4. The event is published to the `chat-messages` Kafka topic.
5. The intelligence service masks PII, analyzes sentiment, and updates temporal metrics.
6. Metrics are written to InfluxDB Cloud.
7. The service publishes `behavioral-metrics` back to Kafka.
8. The transport emits `metrics_update` events to the live dashboard.

---

## Project Status

T.R.A.C.E. Core includes a working real-time chat pipeline, cloud service integration, privacy-preserving NLP processing, temporal telemetry, graph-based influence analysis, and native Windows benchmarking support.
