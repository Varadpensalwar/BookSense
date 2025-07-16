# 📚 BookSense

Welcome to **BookSense** – an AI-powered semantic book recommender! This project leverages state-of-the-art NLP and vector search to help users discover books that match their interests, categories, and emotional tone. Whether you're a developer, data scientist, or book lover, BookSense is designed to be easy to set up, extend, and use.

## ✨ Features

BookSense offers semantic book recommendations that go beyond simple keyword matching, using natural language queries to understand user preferences. The system includes emotion and category filtering capabilities, allowing users to find books based on emotional tone such as happy, sad, or suspenseful content, combined with specific genre preferences. The modern Gradio dashboard provides a user-friendly web interface for instant recommendations, while rich data processing scripts and notebooks handle data cleaning, emotion analysis, and category classification.

The platform utilizes OpenAI embeddings and LangChain for advanced vector search capabilities, delivering high-quality recommendation results. Interactive Jupyter notebooks are included for data exploration, sentiment analysis, and model experimentation, making it accessible for both end users and developers who want to understand or modify the underlying algorithms.

## 🛠️ Tech Stack

**Backend:**
- Python 3.13+
- [Gradio](https://gradio.app/) (UI)
- [FastAPI](https://fastapi.tiangolo.com/) (dependency, not directly used in main app)
- [LangChain](https://python.langchain.com/) (vector search, embeddings)
- [ChromaDB](https://www.trychroma.com/) (vector database)
- [OpenAI API](https://platform.openai.com/docs/api-reference/embeddings) (embeddings)
- [Transformers](https://huggingface.co/docs/transformers/index) (emotion & category classification)
- [Pandas, NumPy, Seaborn, Matplotlib, tqdm](https://pandas.pydata.org/) (data processing & visualization)
- [python-dotenv](https://pypi.org/project/python-dotenv/) (env management)

**Frontend:**
- Gradio (Python-based, no separate JS frontend)

**DevOps & Environment:**
- JupyterLab/Notebook
- Python virtual environment (`venv`)
- MIT License

## 🗂️ Project Structure

```plaintext
BookSense/
├── gradio-dashboard.py         # Main Gradio app (entry point)
├── requirements.txt            # Python dependencies
├── LICENSE                     # MIT License
├── README.md                   # Project documentation
├── data-exploration.ipynb      # Data cleaning & exploration
├── sentiment-analysis.ipynb    # Emotion analysis with transformers
├── text-classification.ipynb   # Category classification
├── vector-search.ipynb         # Vector search experiments
├── books_cleaned.csv           # Cleaned book data
├── books_with_categories.csv   # Books with classified categories
├── books_with_emotions.csv     # Books with emotion scores
├── tagged_description.txt      # ISBN-tagged book descriptions
├── cover-not-found.jpg         # Placeholder image
├── pyvenv.cfg                  # Python venv config
├── Lib/, Scripts/, Include/    # Python venv folders
├── etc/, share/                # Jupyter & system config
└── .gitignore, .gitattributes  # Git config
```

## 📂 Data Files

This project uses several CSV and text files for book metadata and embeddings. The `books_cleaned.csv` file contains cleaned book data after initial processing, while `books_with_categories.csv` includes books with classified categories and `books_with_emotions.csv` contains books with emotion scores. The `tagged_description.txt` file provides ISBN-tagged book descriptions specifically formatted for vector search operations.

If you want to regenerate these files, use the provided Jupyter notebooks in the following order: `data-exploration.ipynb` for initial data cleaning, `text-classification.ipynb` for category assignment, `sentiment-analysis.ipynb` for emotion scoring, and finally `vector-search.ipynb` for testing and optimizing the recommendation algorithms.

## 🚦 Prerequisites & System Requirements

- **OS:** Windows 10+ (tested), Linux/Mac should work with minor tweaks
- **Python:** 3.13.x (see `pyvenv.cfg`)
- **RAM:** 4GB+ recommended (for vector search and model inference)
- **Internet:** Required for downloading models and embeddings
- **OpenAI API Key:** For semantic embeddings (see `.env` setup)

> **Note:** Python 3.13 is very new. If you have trouble installing it, consider using [pyenv](https://github.com/pyenv/pyenv) or a similar tool to manage Python versions.

## ⚙️ Environment Variables

Create a `.env` file in the project root with the following:

```env
OPENAI_API_KEY=your_openai_api_key_here
```

> **Note:** You can obtain an API key from [OpenAI](https://platform.openai.com/account/api-keys).

## 🏗️ Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/yourusername/BookSense.git
   cd BookSense
   ```

 2. **Create a virtual environment:**
    ```bash
     python -m venv booksence
     ```

2. **Activate the virtual environment:**
   - **Windows:**
     ```bash
     booksence\Scripts\activate.bat
     ```
   - **macOS/Linux:**
     ```bash
     source booksence/bin/activate
     ```

3. **Install dependencies:**
   ```bash
   pip install --upgrade pip
   pip install -r requirements.txt
   ```

4. **Set up environment variables:**
   - Copy the example above into a `.env` file and add your OpenAI API key.

## 🚀 Usage

### 1. **Run the Gradio Dashboard (Development):**

```bash
python gradio-dashboard.py
```

- The app will launch in your browser (default: http://localhost:7860).
- Use the interface to enter a book description, select a category and tone, and get recommendations!

### 2. **Jupyter Notebooks (Data Science/Customization):**

- Open any `.ipynb` notebook in JupyterLab/Notebook for:
  - Data cleaning (`data-exploration.ipynb`)
  - Sentiment/emotion analysis (`sentiment-analysis.ipynb`)
  - Category classification (`text-classification.ipynb`)
  - Vector search experiments (`vector-search.ipynb`)

## 🧑‍💻 JupyterLab Configuration

JupyterLab is enabled by default via config files in `etc/jupyter/`. To launch JupyterLab:

```bash
jupyter lab
```

If you encounter issues, check that the extensions are enabled in:
- `etc/jupyter/jupyter_server_config.d/jupyterlab.json`
- `etc/jupyter/jupyter_notebook_config.d/jupyterlab.json`

## 🔒 Security Note

By default, the Gradio dashboard is launched with `share=True`, which exposes your app to the public internet. For local-only use, change the last line in `gradio-dashboard.py` to:

```python
dashboard.launch(share=False)
```

### 3. **Production Deployment:**

- For public sharing, run:
  ```bash
  python gradio-dashboard.py
  ```
  - The app uses `share=True` for public Gradio links.
- For advanced deployment (Docker, cloud, etc.), adapt as needed.

## 🤝 Contributing

We welcome contributions! To get started:

1. Fork this repo and clone your fork.
2. Create a new branch for your feature or bugfix.
3. Commit your changes with clear messages.
4. Push to your fork and open a Pull Request.

**Guidelines:**
- Follow PEP8 for Python code.
- Add docstrings and comments.
- Test your changes before submitting.
- Be respectful and constructive in code reviews.

## ⚠️ Known Issues

- Requires Python 3.13+ (not all environments support this yet).
- Large CSV files may require significant RAM.
- First run may be slow due to model downloads.
- No automated tests included yet.

## 📄 License

This project is licensed under the [MIT License](LICENSE) © 2025 Varad Pensalwar.

## 💬 Contact & Support

- **Author:** Varad Pensalwar
- **GitHub Issues:** [Open an issue](https://github.com/yourusername/BookSense/issues)
- **Email:** varad.pensalwar@gmail.com

## 🙏 Acknowledgements

- [OpenAI](https://openai.com/)
- [HuggingFace Transformers](https://huggingface.co/)
- [Gradio](https://gradio.app/)
- [LangChain](https://python.langchain.com/)
- [ChromaDB](https://www.trychroma.com/)
- [Kaggle Datasets](https://www.kaggle.com/dylanjcastillo/7k-books-with-metadata)

---

Enjoy discovering your next favorite book with **BookSense**! 📖✨
