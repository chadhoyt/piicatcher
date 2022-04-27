# Local Setup Steps

## PII Catcher Setup

Reference: <https://tokern.io/docs/piicatcher/installation>

    git clone https://github.com/tokern/piicatcher.git
    cd piicatcher
    poetry install

## Poetry Pyenv Config

Reference: <https://blog.jayway.com/2019/12/28/pyenv-poetry-saviours-in-the-python-chaos/>

If error about python version then configure poetry project to use pyenv with following, then re-run "poetry install":

    zsh pyenv local 3.8.13 
    poetry config virtualenvs.in-project true
