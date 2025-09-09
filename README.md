# MADS-EDA
## To run the container, go to the folder containing the docker-compose file you want to run, and run:
``` docker compose up --build -d ```

## If you want to use your own settings for the docker containers, rename the .env.example file to .env, and fill in the values you want the configuration to use.

#### To prevent notebooks from littering the git repo, nbstripout has been installed with pipx.
```brew install pipx ```

```pipx install nbstripout ```

#### .gitattributes has been added.
```
# Strip Jupyter notebook outputs & execution counts before committing
*.ipynb filter=nbstripout diff=jupyternotebook

*.zpln filter=nbstripout
*.ipynb diff=ipynb
```
#### To configure nbstripout
```nbstripout --install --attributes .gitattributes ```

#### To keep your git status clean, run this command.
``` 
git config diff.jupyternotebook.textconv "jq -r '.cells[].source | select(. != null) | .[]'" 
```

If this fails, it might mean you have to install jq
```brew install jq ```
