# Named Entity Recognition (NER)

A **BERT-based Named Entity Recognition (NER)** system developed for the **eBay University Machine Learning Competition (2025)**  
([competition page](https://eval.ai/web/challenges/challenge-page/2508/overview)).  
The goal is to extract structured automotive attributes (e.g., brand, model, part type) from **noisy German e-commerce product titles** using token-level sequence labeling.

## Approach (High-Level)

- **Model:** Pretrained BERT encoder + token-level classification head  
- **Training:** Supervised fine-tuning with a subword-aware label alignment strategy  
- **Label alignment:** Only the **first subword** of each word receives a label; subword continuations and padding are ignored (`-100`)  
- **Evaluation:** Entity-level metrics (F-beta score)

A CRF decoding layer was explored, but results showed negligible gains over a softmax-only classifier when using a strong contextual encoder, so the final model favors simplicity and faster inference.

**The dataset used for this competition is proprietary and cannot be shared publicly due to data use agreements.**
