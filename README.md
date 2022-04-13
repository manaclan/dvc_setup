```
dvc init
dvc add stored_models
git rm -r --cached 'stored_models'\n            
git commit -m "stop tracking stored_models"
git add .gitignore stored_models.dvc

dvc remote add --default ssh-storage-name ssh://vinhngo@xxx.xxx.xxx.xxx:/path/to/store
dvc remote modify ssh-storage user vinhngo
#dvc remote modify ssh-storage-name port 22 (optional)
dvc remote modify --local ssh-storage-name password 123456789
```
