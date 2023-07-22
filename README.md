- [Flask Deployment Tutorial](https://gabimelo.medium.com/developing-a-flask-api-in-a-docker-container-with-uwsgi-and-nginx-e089e43ed90e)
- Application will be run in docker container, most of the dependencies need not to be installed locally.
- In case you want to run the scripts locally, you can `pip install -r requirements.txt` inside your virtual environment.
- To include new dependency, we simply `pip install <the_dependecy_name> && pip freeze > requirements.txt`.
- The only python dependency we need locally is debugpy, which debugs the python program running inside a container.
- `sls wsgi serve` to start locally
- select desired layer in [here](https://github.com/keithrozario/Klayers/tree/master/deployments/python3.8). Sometimes lambda does not understand how to handle compiled library that we upload (due to OS difference).
- We add layer in serverless yml, and remove the corresponding dependency in requirement.txt
- `sls plugin install -n serverless-wsgi`
- `sls plugin install -n serverless-python-requirements`
