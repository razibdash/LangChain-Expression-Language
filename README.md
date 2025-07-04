# LangChain Expression Language (LCEL) Demo

This project demonstrates the use of the LangChain Expression Language (LCEL) for building and running language model chains using the [langchain](https://python.langchain.com/) ecosystem. The notebook [LCEL.ipynb](LCEL.ipynb) showcases how to use Groq's Llama 3 model with LangChain, prompt templates, output parsers, and both modern and legacy chain APIs.

## Topics Covered

### 1. Environment Setup
- Loads environment variables using `python-dotenv` to securely access the Groq API key.

### 2. Model Initialization
- Initializes a `ChatGroq` model with the Llama 3 70B model, specifying parameters like temperature, max tokens, and top_p.

### 3. Prompt Templates and Output Parsers
- Uses `ChatPromptTemplate` to create dynamic prompts.
- Utilizes `StrOutputParser` to parse model outputs as strings.

### 4. LCEL Chain Construction
- Demonstrates the new LCEL chaining syntax:  
  `chain = prompt | model | output_parser`
- Shows how to invoke the chain with input variables (e.g., asking for a curious fact about a politician).

### 5. Legacy Chain API
- Shows the deprecated `LLMChain` class for backward compatibility.
- Compares the legacy approach with the new LCEL chaining.

### 6. Batch and Streaming Inference
- Demonstrates batch inference with multiple inputs using `chain.batch`.
- Shows streaming output from the model using `chain.stream`.

## Example Use Cases

- Querying the model for interesting facts about politicians or soccer players.
- Comparing outputs between legacy and modern LangChain APIs.
- Running batch and streaming predictions.

## Requirements

See [requirements.txt](requirements.txt) for all dependencies.

## Usage

1. Install dependencies:
    ```sh
    pip install -r requirements.txt
    ```
2. Set your Groq API key in the `.env` file.
3. Open and run [LCEL.ipynb](LCEL.ipynb) in Jupyter or VS Code.

---

This notebook is a practical introduction to building flexible, composable LLM chains using LangChain's