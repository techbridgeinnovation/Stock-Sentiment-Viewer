# 📈 Stock Sentiment Viewer

A simplified AI-style stock sentiment viewer that allows users to input stock symbols and receive basic sentiment insights (mocked data), while maintaining a history of all previously analyzed symbols.

---

## 🧠 Objective

This project tests your ability to:
- Build a **gRPC-based Golang backend**
- Define and implement **Protobuf APIs**
- Build a **Vue.js frontend** that communicates using **gRPC-Web**

---

## ⚙️ Tech Stack

- **Backend:** Golang + gRPC
- **Protobuf:** Used for API definition and code generation
- **Frontend:** Vue.js + gRPC-Web
- **Proxy:** Envoy or grpcwebproxy for gRPC-Web support

---

## ✨ Functionality Requirements

### 1. 🔍 Analyze Stock Symbol
- Input a stock symbol (e.g. `AAPL`, `TSLA`)
- Backend returns:
  - A random sentiment: `Positive`, `Neutral`, or `Negative`
  - A timestamp (`analyzed_at`)
- Store each analysis result in-memory

### 2. 📊 View Sentiment History
Display all previous analyses in a table:

| Symbol | Sentiment | Analyzed At        |
|--------|-----------|--------------------|
| AAPL   | Positive  | 2025-04-05 10:00AM |
| TSLA   | Neutral   | 2025-04-05 10:03AM |

---

## 🧾 Protobuf API Definition (sentiment.proto)

```proto
syntax = "proto3";

import "google/protobuf/empty.proto";

message Sentiment {
  string symbol = 1;
  string sentiment = 2; // "Positive", "Neutral", or "Negative"
  string analyzed_at = 3;
}

message AnalyzeRequest {
  string symbol = 1;
}

message AnalyzeResponse {
  Sentiment sentiment = 1;
}

message SentimentListResponse {
  repeated Sentiment sentiments = 1;
}

service SentimentService {
  rpc AnalyzeSymbol(AnalyzeRequest) returns (AnalyzeResponse);
  rpc GetAllSentiments(google.protobuf.Empty) returns (SentimentListResponse);
}
