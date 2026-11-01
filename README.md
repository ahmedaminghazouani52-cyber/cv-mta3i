# CV Mta3i — AI Resume Analyzer

CV Mta3i is an AI-powered resume analysis application built with Python and Streamlit. It helps users evaluate how well a CV matches a job description and receive suggestions for improving their application.

## Features

- Upload a CV in **PDF** or **DOCX** format.
- Extract text from the uploaded document.
- Analyze the CV in relation to a job description using a large language model (LLM).
- Highlight relevant skills and potential gaps.
- Generate suggestions to help improve the CV's relevance to the target role.

> **Note:** AI-generated feedback is advisory. Review the suggestions carefully and verify their accuracy before editing or submitting a CV.

## Tech Stack

- **Python** — application logic
- **Streamlit** — web interface
- **Groq API** — access to the language model
- **`pypdf`** — PDF text extraction
- **`python-docx`** — DOCX text extraction
- **`python-dotenv`** — load environment variables during local development

## How It Works

1. The user uploads a CV in PDF or DOCX format.
2. The application extracts the document's text.
3. The user provides a job description.
4. The application sends the relevant text to an LLM through the Groq API.
5. The model returns an analysis and suggestions that help the user understand how their CV aligns with the role.

## Getting Started

### Prerequisites

- Python installed on your computer
- A Groq API key
- Git (optional, for cloning the repository)

### 1. Clone the repository

Replace `<YOUR-REPOSITORY-URL>` with the URL of your GitHub repository.

```bash
git clone <YOUR-REPOSITORY-URL>
cd <YOUR-REPOSITORY-FOLDER>
```

Alternatively, download the repository from GitHub and open its folder in your terminal.

### 2. Create and activate a virtual environment

**Windows (Command Prompt):**

```bat
python -m venv .venv
.venv\Scripts\activate
```

**Windows (PowerShell):**

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

### 3. Install dependencies

If the project includes a `requirements.txt` file:

```bash
pip install -r requirements.txt
```

Otherwise, install the packages used by the application:

```bash
pip install streamlit groq python-dotenv pypdf python-docx
```

### 4. Configure your API key

Create a file named `.env` in the project root:

```env
GROQ_API_KEY=your_groq_api_key_here
```

Replace the placeholder with your own key. Do not share your key or commit the `.env` file to GitHub.

Make sure `.env` is listed in `.gitignore`, for example:

```gitignore
.env
.venv/
__pycache__/
```

The application must load the environment variable and use it when initializing the Groq client. If your code uses a different environment-variable name, use that same name in `.env` and in the application.

### 5. Run the application

From the directory containing `app.py`, run:

```bash
streamlit run app.py
```

Streamlit will provide a local URL in the terminal. Open that URL in your browser.

## Deployment

The application can be deployed using **Streamlit Community Cloud**:

1. Push the project code to a GitHub repository.
2. Open Streamlit Community Cloud and connect your GitHub account.
3. Select the repository and the `app.py` entry point.
4. Add `GROQ_API_KEY` in the app's **Secrets** settings.
5. Deploy the application and test it with sample CVs and job descriptions.

For cloud deployment, store secrets in the hosting platform's secrets manager. Never put API keys directly in source code or in a public repository.

## Example Use Case

A candidate wants to apply for a Python Developer internship. They upload their CV, paste the internship description, and use the generated feedback to identify matching skills, missing keywords, and areas of the CV that may need clarification or improvement.

## Limitations

- Analysis quality depends on the text extracted from the uploaded document and the job description provided.
- Scanned PDFs may require OCR if they do not contain selectable text.
- LLM output can be incomplete or inaccurate; users should verify recommendations.
- A match assessment is guidance, not a guarantee of being shortlisted or hired.

## Security and Privacy

CVs can contain personal information. Only upload documents you are comfortable processing with the application and its configured AI provider. Review the provider's data policies before using real or sensitive documents. Keep API keys private.

## Future Improvements

Possible future enhancements include:
- More detailed, structured analysis results
- Exportable feedback reports
- Better handling of scanned PDFs
- Saved analysis history
- Additional language support

These are ideas for future work and should not be considered implemented features unless they have been added to the code.

## Author

**Ahmed Amine Ghazouani**

Software Engineering Student | Interested in AI, Data Science, and Software Development

---

If you find the project useful, feel free to explore the code and share feedback.
