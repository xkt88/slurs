# Disguising Toxic Intent: Adversarial Exploitation of Cultural Slurs in Image Generation

This repository contains the code and demo data for the research paper: **Disguising Toxic Intent: Adversarial Exploitation of Cultural Slurs in Image Generation**. 

This project explores the vulnerabilities of Text-to-Image models (T2IMs) to implicit toxicity—specifically, culturally coded slurs that carry derogatory meanings but can bypass standard safety filters through benign interpretations. We introduce a multi-phase adversarial pipeline that leverages Large Language Models (LLMs) and Multimodal Large Language Models (MLLMs) to expose these blind spots.

## Repository Structure

Based on the root directory, the repository is organized as follows:

* **`/Dataset`**: Contains the implicit toxicity evaluation data.
    * `en.json`: Demo dataset containing English implicit toxic terms and their target demographics.
    * `zh.json`: Demo dataset containing Chinese implicit toxic terms and their target demographics.
    * `Readme.md`: Detailed documentation explaining the dataset schema, curation process, and category definitions.
* **`Pipeline.ipynb`**: The main Jupyter Notebook implementing the 3-phase adversarial generation pipeline.
    * *Phase 0 (Blatant Prompt)*: Establishes baseline filter vulnerability.
    * *Phase 1 (Context Injection)*: Uses an LLM to camouflage toxic slurs within benign visual narratives.
    * *Phase 2 (Context Pruning)*: Uses an MLLM to iteratively strip away benign elements and recover the toxic intent.
* **`Ablation_Study.ipynb`**: Jupyter Notebook containing the evaluation metrics, analyzing semantic recovery using automated metrics like CLIP and BLIP similarity across different prejudice categories.
* **`Readme.md`**: This file.

## Usage

1.  **Setup**: Ensure you have the necessary API keys configured for the target models you intend to test (e.g., Gemini 3.1, Nano-Banana-2, etc.).
2.  **Data**: Review the `/Dataset/Readme.md` to understand the schema of the `en.json` and `zh.json` demo files.
3.  **Pipeline**: Run `Pipeline.ipynb` to execute the multi-phase attack. The notebook will log the outputs of Phase 0, Phase 1, and Phase 2 sequentially.
4.  **Evaluation**: Use `Ablation_Study.ipynb` to calculate the visual-semantic alignment of the generated images and evaluate the attack success rate (ASR).

## Ethical Considerations

This repository is strictly intended for academic red-teaming and AI safety research. The multi-phase pipeline and accompanying datasets are provided to highlight concrete failure modes in existing safety alignments and to assist developers in building more robust, context-aware, and linguistically inclusive moderation systems. 

All experiments using this code should be conducted under strictly controlled environments to prevent the malicious deployment or dissemination of harmful content.
