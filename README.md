# MLOPs-DVC-Prac
Implementing data versioning with DVC tool

📘 Day 2 – MLOps Pipeline & DVC Concepts
✅ What I Learned
ML Project Pipeline:

Data Ingestion – Pull raw data from external sources (e.g., S3).

Data Preprocessing – Clean and structure the data.

Feature Engineering – Derive meaningful features.

Feature Extraction – Select relevant features for training.

Model Training – Train machine learning models.

Model Evaluation – Assess performance with metrics.

DVC (Data Version Control):

Git handles code versioning, DVC handles data and model versioning.

Each data version gets a unique hash that is committed alongside code.

This ensures reproducibility of results.

🗃️ My Practical Workflow Today
Initialized Git repo and cloned it locally.

Created mycode.py to generate and save data into a data/ folder.

Committed and pushed initial code using Git.

Installed DVC and initialized it using dvc init.

Created a mock S3/ folder to simulate remote storage.

Added remote using:
dvc remote add -d myremote S3/

Stopped Git from tracking data/ and handed it off to DVC using:
dvc add data/
Then:
git rm -r --cached data/
git commit -m "Stopped tracking data with Git"

Added DVC files:
git add .gitignore data.dvc
dvc commit
dvc push

Committed code changes with Git – first version complete!

Repeated the flow (steps 7–9) for second and third versions.

Verified version tracking using:

git log --oneline

git checkout <commit-hash>

dvc pull to retrieve correct data version.
