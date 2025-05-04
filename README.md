# 🔧 Fine-tuning LLMs for Python Code Generation

This project focuses on fine-tuning Microsoft's [`phi-1.5`](https://huggingface.co/microsoft/phi-1_5) language model for Python code generation using natural language problem descriptions. It leverages the CodeParrot/APPS dataset and utilizes efficient fine-tuning techniques like PEFT and LoRA to achieve significant performance improvements on code synthesis tasks.

---

## 📌 Project Overview

- **Goal:** Enhance Python code generation capabilities of a pretrained LLM using domain-specific fine-tuning.
- **Base Model:** Microsoft phi-1.5 (a small yet effective LLM)
- **Dataset:** CodeParrot / APPS (10,000+ Python problems with solutions)
- **Techniques Used:** PEFT (Parameter-Efficient Fine-Tuning), LoRA (Low-Rank Adaptation)
- **Environment:** Google Colab (GPU-enabled)

---

## 📁 Dataset Overview

- **Source:** [CodeParrot / APPS](https://huggingface.co/datasets/codeparrot/apps)
- **Description:** A collection of English programming problem statements paired with corresponding Python solutions.
- **Dataset Used:** First 500 samples.
  - **Training:** 300 samples
  - **Validation:** 100 samples
  - **Testing:** 100 samples


---

## 🛠️ Tools & Libraries

- **Python** – Core language used for training and scripting.
- **Google Colab** – Platform for training with free GPU resources.
- **[Hugging Face Transformers](https://huggingface.co/docs/transformers/index)** – Loading and interacting with pretrained models.
- **[PEFT Library](https://huggingface.co/docs/peft/index)** – Implements LoRA for efficient model fine-tuning.
- **[Datasets](https://huggingface.co/docs/datasets/index)** – Used to load and process the CodeParrot/APPS dataset.
- **[Accelerate](https://huggingface.co/docs/accelerate/index)** – Facilitates training on available hardware (Colab GPU). 
- **[ROUGE Evaluation](https://huggingface.co/spaces/evaluate-metric/rouge)** – Used to evaluate generated Python code quality.

---

## 🔁 Methodology

### 1. Preprocessing
- Filter and clean dataset
- Tokenize using `phi-1.5` tokenizer
- Split into training, validation, and test sets

### 2. Fine-Tuning Strategies
- **Original Data Training:** Fine-tune using human-annotated problems
- **Synthetic Data Training:** Generate synthetic problem-code pairs using ChatGPT and fine-tune
- **Combined Data Training:** Merge both datasets and perform final fine-tuning

### 3. Training Setup
- Used LoRA to fine-tune efficiently on limited hardware
- Conducted training on Google Colab with ~16GB GPU memory

---

## 📈 Evaluation

- **Metrics:** ROUGE (Recall-Oriented Understudy for Gisting Evaluation)
  - ROUGE-1: Unigram overlap
  - ROUGE-2: Bigram overlap
  - ROUGE-L: Longest common subsequence
- **Results:**
  - Best performance observed when trained on **combined dataset**
  - Achieved **~30% improvement** in code generation quality (based on ROUGE scores)

---

## 🧠 Key Learnings

- Domain-specific fine-tuning greatly enhances LLM performance for code generation.
- Synthetic data generated using OPEN AI API helps boost generalization.
- LoRA + PEFT allows efficient training even on resource-limited platforms like Google Colab.

---

## 🚀 Future Improvements

- Expand to support multiple programming languages.
- Evaluate using additional metrics like BLEU, CodeBLEU, and Human Eval.
- Explore model deployment as a code-assist tool or IDE extension.

---

## 📎 Acknowledgments

- [Microsoft's phi-1.5 Model](https://huggingface.co/microsoft/phi-1_5)
- [CodeParrot/APPS Dataset](https://huggingface.co/datasets/codeparrot/apps)
- [Hugging Face Transformers and PEFT libraries](https://huggingface.co/docs)

---

## 📬 Contact

If you have any questions or would like to collaborate, feel free to reach out:

**Prateek Kumar Sharma**  
📧 [Prateeksharma0112@gmail.com](mailto:Prateeksharma0112@gmail.com)  
🌐 [LinkedIn](https://www.linkedin.com/in/prateek-sharma-576105135/)

