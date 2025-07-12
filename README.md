# NovelAdvisor
Built on top of **FLAN-T5**, the model has been adapted using **LoRA (Low-Rank Adaptation)** to align tightly with specific user intent and book recommendation structure. This approach enables efficient, CPU-friendly training on low-resource environments like Google Colab.

---

## 🚀 Features

- 🎯 **Instruction-following**: Tailored to respond only to book-related queries.
- 🧠 **LoRA Fine-Tuning**: Lightweight adapter-based tuning for faster training and inference.
- 🔒 **Output Control**: Custom prompt templates + banned word filters prevent off-topic or toxic responses.
- ⚡ **Optimized for Free-tier**: Works on CPU-only runtimes (no GPU/fp16 needed).

---

## 🛠️ Tech Stack

- `FLAN-T5` base model via Hugging Face 🤗
- `PEFT` for LoRA adapter training
- `Seq2SeqTrainer` for supervised fine-tuning
- Custom dataset of book queries and recommendations
- Trained on **Google Colab (Free tier)**

---

## 🧪 Example Prompts

| Prompt | Output |
|--------|--------|
| "Recommend a historical romance under 300 pages." | *“Try ‘The Duchess Deal’ by Tessa Dare – a witty historical romance, ~285 pages.”* |
| "Sci-fi book involving time travel and moral dilemmas" | *“Consider ‘The First Fifteen Lives of Harry August’ by Claire North.”* |

---

## 📁 Structure

📦bookbuddy
├── data/
│ └── train.json
├── training/
│ ├── lora_config.json
│ └── run_lora_train.py
├── inference/
│ └── generate.py
├── README.md
└── requirements.txt

yaml
Copy
Edit

---

## ✅ How to Use

1. Install dependencies:  
   `pip install -r requirements.txt`

2. Run inference with your own prompt:  
   `python inference/generate.py --prompt "Suggest a thriller with unreliable narrator"`

---

## 💡 Use Cases

- Personal book advisors for websites/apps
- Niche genre recommendation bots
- Fine-tuning demo for instruction-tuned LLMs with LoRA

---

## 📌 Limitations

- May hallucinate titles not in dataset if prompt is vague.
- Designed specifically for book recommendation — off-topic prompts will be ignored or rejected by design.

---

## 📜 License

MIT License © 2025 Sanali Lokuge
