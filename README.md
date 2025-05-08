

# Gauging Large Language Models for Generative Story Evaluation

This project evaluates the ability of large language models (LLMs) to generate emotionally empathetic fictional stories. We compare the outputs of two models—**GPT-2** and **Mistral-7B-Instruct-v0.2**—using automated semantic similarity measures to assess empathy in narrative generation.

## 📌 Objective

To determine which LLM is more capable of producing emotionally rich and empathetic stories, using a benchmark dataset and automated evaluation pipeline. The study aims to move beyond traditional human evaluation toward scalable, objective assessments.

## 📂 Dataset

We use the **HANNA Stories Annotations** dataset:

* 1,056 machine-generated and human-written stories.
* Annotated on six narrative criteria: Relevance, Coherence, Empathy, Surprise, Engagement, and Complexity.
* Evaluated using both human raters and automatic metrics.

Dataset repo: [HANNA Benchmark Dataset](https://github.com/dig-team/hanna-benchmark-asg)

## 🧪 Methodology

The project pipeline consists of two main components:

1. **Story Generation**

   * Using prompts from the HANNA dataset.
   * Generating responses with GPT-2 and Mistral-7B-Instruct-v0.2.

2. **Empathy Evaluation**

   * Using [Sentence-BERT](https://www.sbert.net/) (SBERT) to embed both generated stories and an empathy prototype.
   * Computing cosine similarity between the embeddings to measure empathetic alignment.

A **paired t-test** is conducted to verify statistical significance in model performance differences.

## 📊 Results

| Model      | Win Rate | Mean Cosine Similarity | Statistical Significance |
| ---------- | -------- | ---------------------- | ------------------------ |
| GPT-2      | 6.0%     | Lower                  | Not significant          |
| Mistral-7B | 86.0%    | Higher                 | p < 0.001 ✅              |
| Tie        | 8.0%     | —                      | —                        |

**Conclusion**: Mistral-7B significantly outperforms GPT-2 in generating empathetic narratives.

## 📚 Technologies Used

* `transformers` (Hugging Face)
* `sentence-transformers`
* `scipy` (for statistical testing)
* Python, PyTorch



