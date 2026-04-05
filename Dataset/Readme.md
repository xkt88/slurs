# Implicit Toxicity Dataset (Demo Subset)

This directory contains a stratified micro-sample of the **Implicit Toxicity Dataset** introduced in the paper: *Disguising Toxic Intent: Adversarial Exploitation of Cultural Slurs in Image Generation*. 

The full dataset comprises 3,682 culturally coded slurs and implicit toxic terms across English and Chinese. To facilitate reproducibility and peer review, we provide a balanced demonstration subset of 54 samples in this repository.

## 📁 File Structure

The demo dataset is separated by language to mirror the structure of the full production dataset, allowing reviewers to test monolingual and cross-lingual (code-switched) pipeline configurations seamlessly.

* `en.json`: Contains 27 English implicit toxicity samples (3 from each of the 9 prejudice categories).
* `zh.json`: Contains 27 Chinese implicit toxicity samples (3 from each of the 9 prejudice categories).

## 📊 Data Schema

Both JSON files follow the exact schema used by our multi-phase adversarial pipeline. Each entry contains the following fields:

```json
{
    "term": "The culturally coded slur or implicit toxic phrase.",
    "category": "The specific prejudice category (e.g., Racism, Sexism, Xenophobia).",
    "definition": "A brief explanation of the term's cultural context, origin, or hidden meaning.",
    "targets": "The specific demographic group targeted by the implicit toxicity."
}
