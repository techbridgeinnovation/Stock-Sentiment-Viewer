
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

Feel free to do your own proto definations

## 🛠 Backend (Go)

- Implements the `SentimentService`
- Uses an in-memory slice to store `Sentiment` structs
- Randomly generates sentiment values (`Positive`, `Neutral`, `Negative`)
- Listens on `localhost:50051` for gRPC traffic

---

## 🖥 Frontend (Vue.js)

- Input form for entering stock symbols
- Table to display sentiment history
- Communicates with backend using **gRPC-Web**
- Uses a **proxy (Envoy or grpcwebproxy)** to convert HTTP/1.1 calls to gRPC




## 📌 Assumptions & Simplifications

- Sentiment values are randomly generated (no real ML model involved)
- Sentiments are stored in-memory (not persisted)
- gRPC-Web proxy is required to support browser-based clients

---

## ✅ Evaluation Criteria

- ✅ Correctness of Protobuf definitions
- ✅ Functional gRPC server implementation in Go
- ✅ Successful gRPC-Web setup and integration
- ✅ Clean and modular project structure
- ✅ Code readability, documentation, and comments

---

## 🧠 Notes

You do **not** need to build a real ML model — mocked/random data is acceptable. Focus on getting gRPC, Vue, and integration working smoothly.

---

## 👨🏽‍💻 Maintainer

