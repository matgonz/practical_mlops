install:
		pip install --upgrade pip && pip install - requirements.txt

lint: 
		pylint --disable=R,C hello.py

test:
		python -m pytest -vv --cov=hello test_hello.py