

# 🚀 Code Summary Generator

> **Generate intelligent summaries of any code snippet** using cutting-edge models like **Frontier Models** and **CodeQwen-7-B** — powered by HuggingFace Inference Endpoints.

---

## 📖 About The Project

This project uses **HuggingFace Inference Endpoints** to automatically generate **natural language summaries** for code snippets.  
It integrates powerful large language models trained specifically for understanding and explaining code:

- **FrontierCoder** – optimized for general code comprehension.
- **CodeQueen** – fine-tuned for high-quality, concise, and human-like code summarization.

**Perfect for:** developers, students, technical writers, and anyone who needs quick explanations of source code!

---

## ✨ Features

- 🔥 Instant Code Summarization
- 🛠 Supports multiple programming languages
- 🎯 Highly Accurate Summaries with specialized Code Models
- ☁️ Fast and Reliable via HuggingFace Inference API
- 📜 Beautiful, Clean, and Minimal UI (if you build a frontend)

---

## 🏗️ Tech Stack

- ⚡️ HuggingFace Inference Endpoint
- 🧠 FrontierCoder Model
- 👑 CodeQueen Model
- 🌐 Frontend (Optional) — React.js / Next.js / Plain HTML

---

## 🚀 Getting Started

### 1. Set up HuggingFace Inference Endpoint

- Deploy **FrontierCoder** and **CodeQueen** models to your HuggingFace Inference Endpoints.
- Note down your **Endpoint URLs** and **Bearer Token**.

### 2. Clone This Repository

```bash
git clone https://github.com/your-username/code-summary-generator.git
cd code-summary-generator
```

### 3. Install Dependencies

```bash
npm install
# or
yarn install
```

### 4. Configure Environment Variables

Create a `.env` file:

```bash
HUGGINGFACE_API_URL_FRONTIER=https://your-frontiercoder-endpoint
HUGGINGFACE_API_URL_CODEQUEEN=https://your-codequeen-endpoint
HUGGINGFACE_API_TOKEN=your_huggingface_bearer_token
```

### 5. Usage

Call the inference endpoints like this:

```javascript
async function summarizeCode(code, model = 'frontier') {
  const endpoint = model === 'frontier' ? process.env.HUGGINGFACE_API_URL_FRONTIER : process.env.HUGGINGFACE_API_URL_CODEQUEEN;

  const response = await fetch(endpoint, {
    method: 'POST',
    headers: {
      Authorization: `Bearer ${process.env.HUGGINGFACE_API_TOKEN}`,
      'Content-Type': 'application/json'
    },
    body: JSON.stringify({
      inputs: code
    })
  });

  const data = await response.json();
  return data[0]?.summary_text || 'No summary generated.';
}
```

---

## 📋 Example

### Input Code

```python
def add(a, b):
    return a + b
```


## 🎯 Roadmap

- [x] Basic working version with HuggingFace API
- [ ] Add model selection option in frontend
- [ ] Handle longer code files
- [ ] Add support for multiple programming languages highlighting

---

## 🤝 Acknowledgements

- [HuggingFace](https://huggingface.co) for providing free endpoints
- [FrontierCoder Model](https://huggingface.co/frontiercoder) (hypothetical)
- [CodeQueen Model](https://huggingface.co/codequeen) (hypothetical)

---

