1. Navigate to project folder.

2. Set Python version using pyenv:
    ```terminal
    pyenv local 3.8.10   # example version
    ```
3. Create virtual env:
    ```terminal
    python3 -m venv .venv   # .venv is name of environment
    ```
4. Activate env:
    ```terminal
    source .venv/bin/activate
    ```    
5. pip install poetry
6. poetry init
7. poetry add pandas sklearn  
    #(choose versions with package1=^1.2)
10. poetry update
11. deactivate
