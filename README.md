# SIVRAJ
A Basic Prototype for SIVRAJ

1️⃣ main.py (FastAPI Backend)
This is the main API server that receives job posting links and runs validation checks.

from fastapi import FastAPI
from job_validation import validate_job

app = FastAPI()

@app.get("/")
def home():
    return {"message": "Welcome to Job Validator AI"}

@app.post("/validate_job/")
def validate_job_posting(job_url: str):
    result = validate_job(job_url)
    return {"job_url": job_url, "validation_result": result}
2️⃣ job_validation.py (Basic Job Validation Logic)
This is the job scanning logic (we will improve it later with AI & APIs).


import re

def validate_job(job_url):
    
    Dummy function to check job posting validity.
    Later, we will use web scraping, API calls & AI models.
    
    fake_job_patterns = ["earn quick money", "no experience needed", "work from home $$$"]
    
    # Dummy logic: If URL contains "linkedin.com", assume it's valid
    if "linkedin.com" in job_url:
        return "Legitimate Job Posting ✅"
    
    # Simulated check against scam keywords
    for pattern in fake_job_patterns:
        if re.search(pattern, job_url, re.IGNORECASE):
            return "Warning: This job post may be a scam! ⚠️"

    return "Not Enough Data to Validate ❓"
3️⃣ requirements.txt (Python Dependencies)
Install these dependencies using:

pip install -r requirements.txt
Copy
Edit
fastapi
uvicorn
requests
beautifulsoup4
4️⃣ README.md (Project Documentation)
Create a simple README.md file explaining the project.

JobValidator-AI

A web-based tool that validates job postings to detect scams and fraud.

Features
✅ Validate job postings from various sources  
✅ Identify scam patterns in job descriptions  
✅ Compare recruiter emails with official company domains  

How to Run (Local)
1️⃣ Clone the repository  
2️⃣ Install dependencies: `pip install -r requirements.txt`  
3️⃣ Start the FastAPI server: `uvicorn main: app --reload`  
4️⃣ Open `http://127.0.0.1:8000` to test the API  

🚀 **More features coming soon!**
1 branches found 
