# BERT-Based LLM Classifier

This repository contains a simple example of how to build a binary classifier using a pre-trained BERT model from TensorFlow Hub. The classifier is designed to analyze text input and assign it to one of two classes.

## Dataset

The model is trained and evaluated on a routing dataset. The dataset is in JSONL format, where each line is a JSON object containing a `question` and a `target` (class label).

## Model

The classifier model consists of the following components:

* **Preprocessing Layer:** A `hub.KerasLayer` that applies BERT-specific preprocessing to the input text.
* **BERT Encoder:** A `hub.KerasLayer` that utilizes a pre-trained BERT model from TensorFlow Hub to generate embeddings from the preprocessed text.
* **Pooled Output:** The pooled output from the BERT encoder is used as the aggregated representation of the input text.
* **Classification Head:** A dropout layer and a dense layer with a single output unit (for binary classification) are used for classification.

**Model Architecture:**

![image](https://github.com/user-attachments/assets/dbc75786-cfeb-4003-9336-a4168d181ff7)


## Training and Evaluation

The model was trained for 10 epochs. The training progress, including loss and accuracy, is visualized in the following plots:

**Training Logs:**

![image](https://github.com/user-attachments/assets/a4e736e5-638b-4131-960d-a40799f1b935)


**Training and Validation Loss:**

![image](https://github.com/user-attachments/assets/dc1e450a-6bc0-4f10-b6f4-44626bb51e35)


**Training and Validation Accuracy:**

![image](https://github.com/user-attachments/assets/22f4eea1-58d1-4706-9d37-36db660ab9d9)


## Usage

1. **Install Dependencies:** Make sure you have TensorFlow, TensorFlow Hub, TensorFlow Text, and tf-models-official installed. Restart the session after installation.
2. **Download the Dataset:** Download the training and test datasets (`routing-dataset-train.jsonl` and `routing-dataset-test.jsonl`).
3. **Run the Notebook:** Execute the cells in the provided Jupyter Notebook (`llm-classifier-bert.ipynb`) to train and evaluate the model.

## Key Concepts

* **BERT:** Bidirectional Encoder Representations from Transformers, a powerful language model for text understanding.
* **Pooled Output:** A single vector representation of the entire input sequence, suitable for classification tasks.
* **TensorFlow Hub:** A library for reusable machine learning modules.

## Further Exploration

* **Experiment with Different BERT Models:** Try using different pre-trained BERT models from TensorFlow Hub.
* **Hyperparameter Tuning:** Explore different hyperparameters (e.g., learning rate, batch size, epochs) to optimize the model's performance.
* **Additional Classification Layers:** Consider adding more layers to the classification head for increased complexity.
