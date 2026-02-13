Got you ✅📦 Below is a clean, copy-paste command sequence to create a **new project folder**, move everything into it, add `requirements.txt`, `.gitignore`, `README.md`, then commit + push to GitHub.

I’m assuming you’re on **Windows PowerShell** (since your paths show Windows). I’ll also include Git Bash equivalents where useful.

---

## Option A — PowerShell (Recommended) 🪟✅

### 1) Create the project folder + go inside

```powershell
cd "C:\Users\ksuma\Lab3-ML\WranglingWorkshop"
mkdir Week5_DataPreprocessing_Submission
cd Week5_DataPreprocessing_Submission
```

### 2) Copy your notebook + dataset folder into it

Adjust names if yours differ (e.g., `CSVs`).

```powershell
# Copy notebook
copy ..\week5Lab_Final_10of10_Ready.ipynb .\week5Lab.ipynb

# Copy dataset folder (CSVs)
xcopy ..\CSVs .\CSVs /E /I /Y
```

### 3) Create `.gitignore`

```powershell
@"
# Python virtual environments
.venv/
venv/
env/

# Python cache / compiled
__pycache__/
*.py[cod]
*$py.class

# Jupyter
.ipynb_checkpoints/

# OS junk
.DS_Store
Thumbs.db

# IDEs
.vscode/
.idea/

# Env/secrets
*.env
.env

# Logs
*.log

# Build artifacts
build/
dist/
*.egg-info/
"@ | Out-File -Encoding utf8 .gitignore
```

### 4) Create `README.md`

```powershell
@"
# Week 5 — Data Preprocessing (Cleaning + Outlier Detection)

## Project Contents
- `week5Lab.ipynb` — Completed Week 5 lab notebook with improved markdown + visuals
- `CSVs/` — Input datasets used by the notebook (cars + diabetes)
- `requirements.txt` — Frozen Python dependencies
- `.gitignore` — Git exclusions for clean repo

## How to Run
1. Create and activate a virtual environment
2. Install dependencies:
   `pip install -r requirements.txt`
3. Open Jupyter and run:
   - `Kernel -> Restart & Run All`

## Replicability Notes
- Tested on: (Fill after testing in a clean environment)
- Issues encountered: (If any)
- Fix applied: (If any)
"@ | Out-File -Encoding utf8 README.md
```

### 5) Generate `requirements.txt` (must be in activated venv)

If your venv is one folder up (common), activate it first:

```powershell
# If your venv exists at ..\.venv
..\.\.venv\Scripts\Activate.ps1
pip freeze > requirements.txt
```

If your venv is in the current folder, then:

```powershell
.\.venv\Scripts\Activate.ps1
pip freeze > requirements.txt
```

### 6) Initialize git + commit

```powershell
git init
git add .
git commit -m "Week 5 submission: cleaned notebook, visuals, docs, requirements, gitignore"
```

### 7) Create GitHub repo + push

Create a **new public GitHub repo** (no README, no .gitignore) and copy the repo URL, then:

```powershell
git branch -M main
git remote add origin https://github.com/<YourUsername>/<YourRepoName>.git
git push -u origin main
```

---

## Option B — Git Bash (If you prefer) 🐧

```bash
cd /c/Users/ksuma/Lab3-ML/WranglingWorkshop
mkdir Week5_DataPreprocessing_Submission
cd Week5_DataPreprocessing_Submission

cp ../week5Lab_Final_10of10_Ready.ipynb ./week5Lab.ipynb
cp -r ../CSVs ./CSVs

cat > .gitignore << 'EOF'
.venv/
venv/
env/
__pycache__/
*.py[cod]
.ipynb_checkpoints/
.DS_Store
Thumbs.db
.vscode/
.idea/
*.env
.env
*.log
build/
dist/
*.egg-info/
EOF

cat > README.md << 'EOF'
# Week 5 — Data Preprocessing (Cleaning + Outlier Detection)

## Project Contents
- week5Lab.ipynb
- CSVs/
- requirements.txt
- .gitignore

## How to Run
pip install -r requirements.txt
Run all cells in the notebook.

## Replicability Notes
Fill after testing on another machine / clean environment.
EOF

pip freeze > requirements.txt

git init
git add .
git commit -m "Week 5 submission: cleaned notebook, visuals, docs, requirements, gitignore"
git branch -M main
git remote add origin <url>
git push -u origin main
```

---



---


