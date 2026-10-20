# Create virtual environment
python -m venv .venv

# Activating virtual environment
.venv\Scripts\Activate.ps1

# Git
# Initialise git to start a fresh tracking history: 
git init

# Stage files so git prepares them for upload
git add .

# Commit files locally
git commit -m "Initial commit"

# Rename default branch to main
git branch -M main

# Link repository URL
git remote add origin https://...
 
# Push code to github
git push -u origin main

# Clone Turner datasets from github
git clone --depth 1 https://github.com/clarifying-EM/model-organisms-for-EM.git
pip install easy-dataset-share
cd model-organisms-for-EM/em_organism_dir/data
easy-dataset-share unprotect-dir training_datasets.zip.enc -p model-organisms-em-datasets --remove-canaries

# RUN MODEL
# To run model from turners git hub
# Deactivate my venv, then go into turner's folder, sync then activate turner's venv
deactivate
cd .\model-organisms-for-EM\  

# makes the project’s virtual environment match its dependency list exactly
uv sync 
.\.venv\Scripts\Activate.ps1
uv run pip install -e .    