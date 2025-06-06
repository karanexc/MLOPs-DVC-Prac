🔧 Practical Steps I Followed
```bash
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
15. git commit -m "new version" && git push
