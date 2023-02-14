# Important Commands

## 1. How to create Virtual Environment

```python

python -m venv env

```
- env is the name of the virtual environment

## 2. How to activate Virtual Environment

```python

 env/Scripts/activate

```

## 3. How to deactivate Virtual Environment

```python

deactivate

```

## 4. if you are see any error like `(cannot be loaded because running scripts is disabled on this system)` then run this command

```python

Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy Unrestricted

```

## 5. How to install requirements.txt

```python

pip install -r requirements.txt

```
## 6. How to create requirements.txt

```bash

pip freeze > requirements.txt

```


