# Implementing DevOps

The foundation of DevOps is continuous integration. Without automated testing, there is no way to move forward with DevOps. The first step is to build a "scaffolding" for a Python project.

The following Python project structure is straightforward to implement for ML projects.

- ```Makefile```: A Makefile runs "recipes" via the make system, which comes with Unix-based operating systems. Therefore, a Makefile is an ideal choice to simplify the steps involved in continuous integration, such as the following. Note that a Makefile is a good starting point for a project and will often evolve as new pieces need automation. When you embrace the Makefile approach, it simplifies your workflow and makes it easier to integrate your project into a continuous integration system. There is less code to type, and this is always a good thing for automation. Further, Makefile commands are recognized by shell auto-completion, making it easy to "tab-complete" the steps.

    ***Make install*** - This step install software via the make install command

    ***Make lint*** - This step checks for syntax errors via the make lint command

    ***Make test*** - This step runs tests via the make test command.
    ```
        install:
                pip install --upgrade pip && pip install -r requirements.txt
        lint:
                pylint --disable=R,C hello.py
        test:
                python -m pytest -vv --conv=hello test_hello.py

    ```
- ```requirements.txt```

- ```Source code and tests```: The python scaffolding's final portion is to add a source code file and a test file.

These four files: Makefile, requirements.txt, source code file and test file are all that is needed to start the continuous journey except for creating a local python environment. To do that, first, create it:
```
    pip install virtualenv

    virtualenv your-repo-name-venv
```
Next, you source it "activate" it:
```
    your-repo-name-venv/Scripts/activate
```
To deactivate:
```
    deactivate
```