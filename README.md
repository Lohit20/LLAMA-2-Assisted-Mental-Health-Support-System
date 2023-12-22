# LLM-Assisted Mental Health Support System

## Project Definition

The LLM-Assisted Mental Health Support System aims to provide on-the-spot guidance and support for individuals dealing with mental health issues. The core of the system is a 7 billion parameter Llama 2 language model (LLM) utilized as a virtual assistant. Key components include implementing quantization techniques for memory optimization, and fine-tuning the LLM using Huggingface's Amod/mental_health_counseling_conversations dataset tailored for mental health Q&A.

## Dataset

The project utilizes the Amod/mental_health_counseling_conversations dataset for its rich collection of real-world mental health-related conversations. This dataset captures diverse language patterns and nuances present in actual counseling scenarios, contributing to the robustness of the model.

## Tools Used

- **Deep Learning Framework:** PyTorch
- **Library:** Transformers from Hugging Face
- **Model:** 7 billion parameter Llama 2 model
- **Quantization Tools:** PeFT and QloRA
- **GPUs:** One P100 GPU and a pair of T-4 GPUs

## Methodology

### Model Selection

Chose the 7 billion parameter Llama 2 model for its advanced language processing capabilities.

### Optimization Techniques

Applied quantization from 32-bit float to 4-bit to optimize GPU memory usage and increase training speed.

### Fine-Tuning Process

Utilized Hugging Face's Transformers library to load the model from Meta. QloRA library by HF was used for quantization, and PeFT (Parameter Efficient Finetuning) was used to update the weights of adaptor layers. The model was fine-tuned on 1000 rows for 1 epoch using a 512-max sequence length.

### Data Preprocessing

Cleaned and preprocessed the dataset, ensuring privacy and relevance.

### Training and Evaluation

Trained the model with careful consideration of parameters, continuously evaluated on LangSmith framework against chatGpt. The model achieved similar accuracy with 85% less computation cost.

### User Interface Development

Designed the user interface using Gradio to enhance interactivity and user experience.

## Model

The model is live on Hugging Face.

## Challenges and Bottlenecks

- Obtaining official llama 2 weights required submitting a form on Meta and waiting for 2 days.
- Initial attempts with Llama2-13B parameters model exhausted 3 GPUs.
- Tiny Llama, a sharded version, produced redundant responses.
- Experimenting with different max sequence lengths revealed trade-offs between context clarity and response speed.
- Training on 3000 rows led to overfitting and poor performance on test prompts.
- Initial issues with reloading the finetuned model on Hugging Face were resolved by defining a config.json file.
- Transitioned from Streamlit to Gradio for UI due to GPU requirements and performance on Kaggle notebook.

## Results

Remarkable results were achieved as the chatbot effectively responded to depression-based queries with various contexts.

## Conclusion

The development of the LLM-Assisted Mental Health Support System successfully leveraged cutting-edge technologies and methodologies to address the immediate need for accessible mental health resources. The utilization of the 7 billion parameter Llama 2 model, optimized through quantization, and fine-tuned on the Amod/mental_health_counseling_conversations dataset, ensures a robust understanding of natural language in addressing mental health queries. The incorporation of Gradio for user interface design enhances user interaction, making the system user-friendly and responsive. This endeavor signifies a significant step toward making immediate mental health guidance accessible to individuals in need.

## Hugging Face Repository

[Lohit20/Depressed_Llama-2-7b](https://github.com/Lohit20/Depressed_Llama-2-7b)
