# Analyse It: News Research Tool 📊

## Overview

"Analyse It" is a powerful chatbot designed to assist business analysts and decision-makers by quickly extracting relevant insights from large articles. By leveraging state-of-the-art natural language processing (NLP) techniques, this tool simplifies the process of finding answers, enabling quicker and more informed decision-making.

## Features

- **Streamlined Article Analysis**: Processes up to three article URLs at a time for efficient data retrieval.
- **Question Answering**: Extracts precise answers from large articles using advanced embeddings and language models.
- **Source Attribution**: Displays sources for answers to ensure transparency and reliability.
- **User-Friendly Interface**: Intuitive interface built with Streamlit for seamless interaction.

## How It Works

1. **Input Article URLs**: Users provide up to three URLs of news articles via the sidebar.

2. **Data Processing**:
    - Articles are loaded and split into smaller chunks using a recursive text splitter.
    - Embeddings are generated for each chunk using the `sentence-transformers/all-MiniLM-L6-v2` model.
    - These embeddings are stored in a FAISS index for efficient retrieval.

3. **Ask Questions**:
    - Users input their query.
    - The tool retrieves relevant chunks and uses Google Generative AI (model: "gemini-1.5-flash") to generate an accurate response.

4. **Display Results**:
    - Provides the answer and lists the sources for the response.

## Tech Stack

- **Frontend**: Streamlit
- **Natural Language Models**:
  - Google Generative AI
  - Hugging Face Embeddings
- **Vector Storage**: FAISS (Facebook AI Similarity Search)
- **Text Processing**: RecursiveCharacterTextSplitter (from LangChain)
- **Document Loading**: UnstructuredURLLoader (from LangChain)

## Installation

### Prerequisites

- Python 3.8+
- API Key for Google Generative AI

### Steps

1. **Clone the repository**:

    ```bash
    git clone https://github.com/yourusername/analyse-it.git
    cd analyse-it
    ```

2. **Install dependencies**:

    ```bash
    pip install -r requirements.txt
    ```

3. **Set up environment variables**:

    - Create a `.env` file in the project directory.
    - Add your Google API key:

      ```env
      GOOGLE_API_KEY=your-api-key
      ```

4. **Run the application**:

    ```bash
    streamlit run app.py
    ```

## Usage

1. Enter up to three article URLs in the sidebar.
2. Click the "Process URLs" button to process the articles.
3. Type a question in the input box to retrieve answers.
4. View the generated answer along with its sources.

## File Structure

```plaintext
.
|-- app.py               # Main application file
|-- requirements.txt     # Python dependencies
|-- .env                 # Environment variables (not included in repo for security)
|-- faiss_store_google.pkl # Pickle file for FAISS index (generated during runtime)
```

## Demo
Image1
![gs-ba](https://github.com/user-attachments/assets/242ed8cb-6bc1-41ad-a142-9196e94b7467)

## Contribution

Contributions are welcome! Please create an issue or pull request to discuss your ideas or improvements.

## License

This project is licensed under the MIT License.

## Contact

For any inquiries, please contact:

- **Email**: tajmalnas36@gmail.com
