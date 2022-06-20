```
dvc init
dvc add stored_models
git rm -r --cached 'stored_models'\n            
git commit -m "stop tracking stored_models"
git add .gitignore stored_models.dvc .dvc

(you can visit .dvc/config file after run all config commands)
# SSH Config
dvc remote add --default ssh-storage-name ssh://vinhngo@xxx.xxx.xxx.xxx:/path/to/store
dvc remote modify ssh-storage user vinhngo
#dvc remote modify ssh-storage-name port 22 (optional)
dvc remote modify --local ssh-storage-name password 123456789

# Local config
dvc remote add --default myremote /path/to/remote

# Change remote
dvc remote default

# Errors
- configuration error - config file error: expected 'url' for dictionary value @ data['remote']['m38']
dvc remote remove m38 --local

- ERROR: unexpected error - libffi.so.7: cannot open shared object file: No such file or directory
https://askubuntu.com/questions/1289782/pygobject-venv-and-ubuntu-20-10-importerror-libffi-so-7-cannot-open-shared-o
Actually we dont need to install the lib, it just read-write permission problem on the storage directory
```

