# jupyter-env
my environment for jupyter notebook

```bash
brew install pyenv
brew install pyenv-virtualenv
```

```bash
vim ~/.bash_profile

## Set path for pyenv
export PYENV_ROOT="${HOME}/.pyenv"
if [ -d "${PYENV_ROOT}" ]; then
    export PATH=${PYENV_ROOT}/bin:$PATH
    eval "$(pyenv init -)"
    eval "$(pyenv virtualenv-init -)"
fi
```

```bash
pyenv install 3.6.5
pyenv virtualenv 3.6.5 jupyter-notebook
pyenv local jupyter-notebook
```


```bash
pyenv exec pip freeze > requirements.txt
pyenv exec pip wheel --wheel-dir=/tmp/wheelhouse -r requirements.txt
pip install -r requirements.txt --use-wheel --no-index --find-links=/tmp/wheelhouse
pip freeze
```

https://qiita.com/yanagi4q/items/bd0a90318267614fb84b
https://github.com/takluyver/bash_kernel
