# Resume_ATS-Tracker

Resume ATS tracker is a Streamlit-based web application that evaluates a resume against a given job description using a generative AI model. The application provides feedback to improve the resume's compatibility with Applicant Tracking Systems (ATS) commonly used in the tech field. It uses Google Generative AI (Gemini) and PyPDF2 for processing PDF resumes.

## Features

- Upload your resume in PDF format.
- Paste a job description to compare your resume against.
- Uses Google Gemini AI to analyze and score the resume based on the job description.
- Provides a percentage match, highlights missing keywords, and offers a profile summary to help improve your resume.

## Prerequisites

- Python 3.8 or higher
- Streamlit
- Google Generative AI (Gemini) package
- PyPDF2 for PDF text extraction
- dotenv for loading environment variables

## Installation

1. **Clone the repository:**

    ```bash
    git clone https://github.com/prabhakarvenkat/Resume_ATS-Tracker.git
    ```

2. **Navigate to the project directory:**

    ```bash
    cd resume-ats-tracker
    ```

3. **Create and activate a virtual environment:**

    ```bash
    python3 -m venv venv
    source venv/bin/activate  # On Windows: venv\Scripts\activate
    ```

4. **Install the required packages:**

    ```bash
    pip install -r requirements.txt
    ```

5. **Set up environment variables:**

   - Create a `.env` file in the root directory of the project.
   - Add your Google API key to the `.env` file:

    ```env
    GOOGLE_API_KEY=your_google_api_key_here
    ```

## Usage

1. **Run the application:**

    ```bash
    streamlit run app.py
    ```

2. **Upload Resume and Job Description:**

   - Open the Streamlit application in your browser.
   - Paste the job description in the provided text area.
   - Upload your resume in PDF format using the file uploader.
   
3. **Get Evaluation:**

   - Click the "Submit" button to evaluate your resume.
   - The application will display a JSON-like string with the following information:
     - **JD Match**: Percentage match of the resume to the job description.
     - **Missing Keywords**: List of keywords missing in the resume.
     - **Profile Summary**: Suggestions to improve the resume.

## Code Explanation

- **Environment Variables:** Uses `dotenv` to load the Google API key.
- **PDF Text Extraction:** Uses PyPDF2 to read the uploaded PDF file and extract its content.
- **Google Generative AI:** Calls the Google Generative AI (Gemini) to analyze the resume content and provide feedback based on the input prompt.
- **Streamlit Interface:** Provides a simple web interface for users to input the job description, upload the resume, and view the analysis results.

## Code Structure

- **get_gemini_response(input):** Generates a response using Google Generative AI (Gemini) based on the input prompt.
- **input_pdf_text(uploaded_file):** Extracts text from the uploaded PDF file using PyPDF2.
- **input_prompt:** The template used to prompt the AI model for evaluation.
- **Streamlit UI:** Allows users to paste the job description, upload a PDF resume, and submit for evaluation.

## Dependencies

- `streamlit`
- `google-generativeai`
- `os`
- `PyPDF2`
- `python-dotenv`

Add these dependencies to a `requirements.txt` file for easier installation:

```text
streamlit
google-generativeai
PyPDF2
python-dotenv
```

## Notes

- Make sure you have a valid Google API key to use the Generative AI model.
- This application currently supports only PDF files for resume uploads.

## Output Screenshots
![logo](https://github.com/prabhakarvenkat/Resume_ATS-Tracker/blob/e23ae4f801dcbf4131369cf274c7edf89b011851/output_screenshot_1.png)
![logo](https://github.com/prabhakarvenkat/Resume_ATS-Tracker/blob/e23ae4f801dcbf4131369cf274c7edf89b011851/output_screenshot_2.png)

## Acknowledgements

- [Streamlit](https://streamlit.io/) for the web application framework.
- [Google Generative AI (Gemini)](https://developers.generativeai.com/) for resume analysis.
- [PyPDF2](https://pythonhosted.org/PyPDF2/) for PDF text extraction.

## License

This project is licensed under the MIT License.
