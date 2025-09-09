# MADS-EDA

#### To prevent notebooks from littering the git repo, nbstripout has been installed with pipx.
'''brew install pipx '''
'''pipx install nbstripout '''

#### .gitattributes has been added.
'''
# Strip Jupyter notebook outputs & execution counts before committing
*.ipynb filter=nbstripout
'''
#### To configure nbstripout
'''nbstripout --install --attributes .gitattributes '''

#### To keep your git status clean, run this command.
'''git config diff.jupyternotebook.textconv "jq -r '.cells[].source | select(. != null) | .[]'"
'''
If this fails, it might mean you have to install jq
'''brew install jq '''
