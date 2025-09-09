# MADS-EDA
# Running the containers:
cd to the folder containing the docker-compose file you want to start, and run:
``` docker compose up --build -d ```

If you want to use your own settings for the docker containers:
```mv .env.example .env ```
you can change all values you want to use in the .env file



# Housekeeping
### Prevent notebooks from littering the git repo, 
Installed pipx
```brew install pipx ```
installed nbstripout
```pipx install nbstripout ```

Add .gitattributes to configure nbstripout and gitdiff
```
# Strip Jupyter notebook outputs & execution counts before committing
*.ipynb filter=nbstripout diff=jupyternotebook

*.zpln filter=nbstripout
*.ipynb diff=ipynb
```
Install nbstripout in current repo with correct configuration
```nbstripout --install --attributes .gitattributes ```

Keeping git status clean
``` 
git config diff.jupyternotebook.textconv "jq -r '.cells[].source | select(. != null) | .[]'" 
```
If this fails, it might mean you have to install jq
```brew install jq ```
