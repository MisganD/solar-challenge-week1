# Environment Setup
# Initialize Repository
# Using Git Ba
1. Clone the repository:  
   `git clone https://github.com/MisganD/solar-challenge-week1.git`  
2. Navigate to the project directory:
   `cd C:/Users/Misgan/solar-challenge-week1`
3. Create a virtual environment:  
   `py -m venv venv`  
4. Activate the environment:  
-  `source venv/Scripts/activate`   
# Branching and commits
# Create a new branch for your task:
-  `git checkout -b setup-task`
1 Make first commit .gitignore
# create .gitignore
-  `echo "data/" >> .gitignore`
-  `echo "*csv" >> .gitignore`
-  `echo ".ipynb_checkpoints/" >> .gitignore`
-  `echo "venv/" >> .gitignore`  # Add if not already there
# Staging and committing changes
-  `git add .gitignore`
-  `git commit -m "init: add .gitignore"`
2. Second Commit – requirements.txt
# create requirements.txt
-  `pip freeze > requirements.txt`
# Staging and committing changes
-  `git add requirements.txt`
-  `git commit -m "chore: venv setup"`
3. Third Commit – GitHub Actions Workflow
# Create a GitHub Actions workflow file 
-  `mkdir -p .github/workflows`
-  `touch .github/workflows/ci.yml`
# Add the following content to ci.yml
`name: CI
on: [push, pull_request]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Set up Python
        uses: actions/setup-python@v4
        with:
          python-version: "3.x"
      - name: Check Python version
        run: python --version
      - name: Install dependencies
        run: pip install -r requirements.txt`

# Staging and committing changes
-  `git add .github/workflows/ci.yml`
-  `git commit -m "ci: add GitHub Actions workflow"`

# Merge setup-task into main via a Pull Request.
