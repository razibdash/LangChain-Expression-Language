# LangChain Expression Language (LCEL)

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

# LangChain Expression Language (LCEL) Built-in Runnables

This project demonstrates the use of LangChain's built-in "runnables" for building flexible and composable language model pipelines. The notebook [`LCEL_builtin_runnables.ipynb`](LCEL_builtin_runnables.ipynb) provides practical examples of how to use core LCEL components such as `RunnablePassthrough`, `RunnableLambda`, and `RunnableParallel`, as well as how to integrate them with prompt templates, output parsers, and retrieval-augmented generation.

## Topics Covered

### 1. Environment Setup

- Loads environment variables using `python-dotenv` to securely access the Groq API key.

### 2. Model Initialization

- Initializes a `ChatGroq` model with the Llama 3 70B model, specifying parameters like temperature, max tokens, and top_p.

### 3. RunnablePassthrough

- Demonstrates `RunnablePassthrough`, which simply passes its input through unchanged.
- Example: Passing a string directly through the chain.

### 4. RunnableLambda

- Shows how to use `RunnableLambda` to wrap a custom Python function for use in a chain.
- Example: Appending "ovich" to a name to simulate a Russian-style last name.

### 5. Chaining Runnables

- Combines `RunnablePassthrough` and `RunnableLambda` using the `|` operator to build simple pipelines.

### 6. RunnableParallel

- Demonstrates `RunnableParallel` for running multiple operations in parallel and collecting their outputs in a dictionary.
- Example: Running both passthrough and custom lambda operations on the same input.

### 7. Prompt Templates and Output Parsers

- Uses `ChatPromptTemplate` to create dynamic prompts for the language model.
- Utilizes `StrOutputParser` to parse model outputs as strings.

### 8. Parallel Data Transformation and Prompting

- Shows how to use `RunnableParallel` to transform input data (e.g., generating a soccer player's name) and feed it into a prompt template for the model.

### 9. Advanced RunnableParallel with Retrieval-Augmented Generation

- Integrates a vector store (`FAISS`) and retriever with HuggingFace embeddings.
- Loads documents, creates embeddings, and builds a retriever for context-aware question answering.
- Uses `RunnableParallel` to fetch context and question, then prompts the model for an answer.

### 10. Using `itemgetter` for Flexible Input Mapping

- Demonstrates how to use Python's `itemgetter` to map specific fields from input dictionaries to different parts of the chain.
- Supports multi-language answers by passing a `language` variable through the chain.

## Example Use Cases

- Passing data through chains unchanged or with custom transformations.
- Running multiple operations in parallel and combining their results.
- Building retrieval-augmented question answering pipelines.
- Dynamically mapping and transforming input data for complex LLM workflows.

## Requirements

See [requirements.txt](requirements.txt) for all dependencies.

## Usage

1. Install dependencies:
   ```sh
   pip install -r requirements.txt
   ```
2. Set your Groq API key in the `.env` file.
3. Ensure you have the required data file (e.g., `data/Razib.txt`) for vector store examples.
4. Open and run [`LCEL_builtin_runnables.ipynb`](LCEL_builtin_runnables.ipynb) in Jupyter or VS Code.

---

This notebook is a practical introduction to building advanced, composable LLM chains using LangChain's built-in runnable
