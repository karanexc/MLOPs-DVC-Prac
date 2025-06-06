# MLOPs-DVC-Prac
Implementing data versioning with DVC tool

📘 Day 2 – MLOps Pipeline & DVC Concepts
🧠 What I Learned
🔁 ML Project Pipeline
📥 Data Ingestion – Pull raw data from sources (S3, APIs, etc.)

🧹 Data Preprocessing – Clean and format raw data

🛠️ Feature Engineering – Create new features

🔍 Feature Extraction – Select important features

🤖 Model Training – Train ML models

📊 Model Evaluation – Measure model performance

🗃️ DVC (Data Version Control)
🧬 DVC helps track large files and models like Git tracks code

Every version of your data/model is assigned a unique hash

Integrates with Git commits to ensure reproducibility

Stores `.dvc` metadata files that can be committed and pushed

🔧 Practical Steps I Followed
`bash
Copy
Edit
# Initialize git and clone repo
1. Create repo & clone locally

# Add sample code
2. Create mycode.py (saves data to /data)

# Start Git versioning
3. git add, commit, push

# Start DVC versioning
4. pip install dvc
5. dvc init
6. mkdir S3  # simulate cloud storage
7. dvc remote add -d myremote S3/

# Track data with DVC
8. dvc add data/
   git rm -r --cached data/
   git commit -m "stopped tracking data"

9. git add .gitignore data.dvc
10. dvc commit && dvc push
11. git commit -m "first version" && git push

# Make changes and repeat
12. Update code
13. dvc status
14. dvc commit && dvc push
15. git commit -m "new version" && git push`


🔄 Version Control Tips
View commit history:

bash
Copy
Edit
git log --oneline
Revert to a version:

bash
Copy
Edit
git checkout <commit-hash>
Restore data version:

bash
Copy
Edit
dvc pull
✅ Summary
DVC makes ML projects reproducible

Keeps data versions organized

Links code + data seamlessly for efficient collaboration
