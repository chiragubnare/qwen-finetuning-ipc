# qwen-finetuning-ipc
Fine-tuned Qwen2.5 Inference

This repository contains a Jupyter Notebook Kuki_task_ipc.ipynb that demonstrates running inference on a fine-tuned Qwen2.5 model for Indian Penal Code (IPC) related tasks.
The notebook focuses on loading model weights from a provided zip file, preparing the environment, and generating outputs without requiring further training.

📂 Project Structure

Kuki_task_ipc.ipynb – Main notebook containing step-by-step code for inference.

qwen2.5-finetuned.zip – Model weights (fine-tuned or adapter files).

README.md – Documentation for setup and usage.

⚙️ Requirements

Before running the notebook, install the following dependencies:

pip install torch transformers peft accelerate bitsandbytes


Optional (for Colab users, GPU acceleration recommended):

pip install datasets

▶️ Usage

Unzip the Model Weights
The notebook automatically extracts qwen2.5-finetuned.zip into a working directory.

Load Model & Tokenizer

If the zip contains a full fine-tuned model → loads directly.

If the zip contains only PEFT adapters → loads the base model (Qwen/Qwen2.5-1.5B-Instruct) and applies adapters.

Run Inference
Use the generate() function defined in the notebook:

prompt = """### Instruction:
Explain IPC 420 in simple terms.

### Response:
"""
output = generate(prompt, max_new_tokens=128)
print(output)

🖥️ Example Output

Input:

### Instruction:
Explain IPC 420 in simple terms. Answer succinctly.

### Response:


Output:

IPC 420 deals with cheating and dishonestly inducing the delivery of property. In simple words, it applies when someone deceives another person to gain money or valuables unfairly.

💡 Notes

Update BASE_MODEL_NAME in the notebook if your adapter was trained on a different base model.

Set USE_8BIT = False if your environment does not support bitsandbytes.

Works best on GPU (CUDA) but will fall back to CPU if not available.

📜 License

This project is intended for research and demonstration purposes.
