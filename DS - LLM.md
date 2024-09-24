# Virtual Environments

## Conda 

```
conda create -n myenv python=3.9
conda activate myenv
python --version
conda search python
conda remove -n myenv --all
```

## Venv

```
python3 -m venv .venv
source .venv/bin/activate
pip freeze > requirements.txt
deactivate
```

# Docker

```
docker run -p 9200:9200 -e "discovery.type=single-node" elasticsearch:8.5.1
docker run -p 9200:9200 -e "discovery.type=single-node" -e "xpack.security.enabled=true" docker.elastic.co/elasticsearch/elasticsearch:8.15.1
docker ps
docker exec -it [container-id] /bin/bash
docker logs [container-id]

 curl -k -u elastic:lAZGOFmJV3rxpCUPNBhZ http://localhost:9200
```

# Netomi Pip Install

```
pip install --upgrade pip && pip install --extra-index-url http://pypi.netomi.io --trusted-host pypi.netomi.io -r requirements/global_requirements.txt
```

# For handling multiple versions of Pip and Python

```
which python
which pip
python -m pip install elasticsearch
/opt/miniconda3/envs/rag_application/bin/pip install elasticsearch
```

# For Checking python architecture

```
file $(which python)

```

# Git stuff

* For a fresh repo

```
git init
git add DS\ -\ LLM.md 
git commit -m "Initial Commit" 
git branch -M main  
git remote add origin git@github.com:anirudh-32/Notes.git
git push -u origin main
```