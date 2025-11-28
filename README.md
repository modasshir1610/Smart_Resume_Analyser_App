# Smart_Resume_Analyser_App
# Smart Resume Analyzer

**Project:** Smart Resume Analyzer (SRA)

**Short description**
A Streamlit-based web application that extracts information from PDF resumes, analyzes skills and sections, recommends skills and courses, scores resume writing, and stores user results in a local MySQL database.

---

## Features

* Upload PDF resume and preview it inside the app
* Extract name, email, phone, skills, and number of pages from resumes using `pyresparser` and `pdfminer3`
* Intelligent recommendations for career tracks (Data Science, Web, Android, iOS, UI/UX)
* Suggested skills and curated course links
* Resume-writing checks (Objective, Declaration, Hobbies/Interests, Achievements, Projects)
* Resume score with progress visualization and short videos for tips
* Admin dashboard to view stored user data and download CSV
* Simple charts for quick insights into collected data (Plotly)

---

## IMPORTANT: Academic Integrity & AI USAGE POLICY

**Using AI to write, modify, or assist this project is strictly prohibited.** This includes but is not limited to ChatGPT, Copilot, Bard, Claude, or any other AI assistants or code generation tools. If any part of the submitted project (code, README, documentation, or supporting files) is found to be created or significantly modified by an AI tool, it will be considered a violation of academic integrity and the submission will receive **zero marks**.

By submitting this project you confirm that all code and documentation are your own work or properly attributed where external (non-AI) resources were used.

---

## Tech stack / Dependencies

* Python 3.10+ (recommend 3.10 — test your environment)
* Streamlit
* nltk
* spacy (with `en_core_web_sm` model)
* pyresparser
* pdfminer3
* pandas
* pymysql
* pillow (PIL)
* streamlit-tags
* pafy, youtube-dl or youtube-dl replacement
* plotly.express
* Any other Python packages referenced in the code

**Notes:**

* `pyresparser` may require Java & other system-level dependencies. See pyresparser documentation if extraction fails.
* If `pafy` or `youtube_dl` fails due to changes in YouTube, you may need to replace them with actively maintained libraries.

---

## Setup / Installation

1. Create and activate a Python virtual environment:

```bash
python -m venv venv
# Windows
venv\Scripts\activate
# macOS / Linux
source venv/bin/activate
```

2. Upgrade pip and install requirements (example):

```bash
pip install --upgrade pip
pip install streamlit nltk spacy pyresparser pdfminer3 pandas pymysql pillow streamlit-tags pafy youtube_dl plotly
```

3. Download spaCy model:

```bash
python -m spacy download en_core_web_sm
```

4. NLTK: download stopwords when running the app for the first time (the code contains `nltk.download('stopwords')`).

5. Ensure MySQL (or MariaDB) is installed and running locally. Update connection credentials in the script if needed.

---

## How to run

1. Place the project folder in a working directory. Ensure the following folders/files exist (create if missing):

   * `Logo/` (contains `SRA_Logo.jpg` or `.ico`)
   * `Uploaded_Resumes/` (writable folder where uploaded resumes will be saved)
   * `Courses.py` (contains course lists used by the recommender)

2. Start the Streamlit app:

```bash
streamlit run app.py
# or the filename you are using, e.g. streamlit run main.py
```

3. Open `http://localhost:8501` in your browser.

---

## Database

* The app creates a database named `SRA` and a table `user_data` if they don't exist.
* Default connection uses `host='localhost'`, `user='root'`, `password=''`. Change these credentials in the script to match your MySQL setup.

---

## Project structure (suggested)

```
SRA/
├─ app.py                # main Streamlit script (your code)
├─ Courses.py            # course lists used by recommender
├─ Logo/
│  ├─ SRA_Logo.jpg
│  └─ SRA_Logo.ico
├─ Uploaded_Resumes/
└─ README.md
```

---

## Troubleshooting & Common issues

* **pyresparser fails to parse**: Ensure Java is installed and configured on your system; check that `pyresparser` dependencies are satisfied.
* **pdfminer errors**: Confirm the `pdfminer3` import matches your installed package — some environments have `pdfminer.six` or different names.
* **YouTube video fetching errors**: YouTube libraries frequently break when YouTube updates. Consider removing the fetch call or using a stable embedding approach.
* **Database connection errors**: Check MySQL server status and credentials. Test connection via a MySQL client.


## Credits

* Original developer:Shaikh MOdasshir Rabbani
Email:shaikh.25mim10082@vitbhopal.ac.in
