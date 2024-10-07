# Virtual Environments

## Conda 

```
conda create -n myenv python=3.9
conda activate myenv
python --version
conda search python
conda remove -n myenv --all
```

## For creating Conda env with specific Architecture

```
CONDA_SUBDIR=osx-64 conda create -n ds-core python=3.9
CONDA_SUBDIR=osx-arm64 conda create -n ds-core python=3.9
file $(which python)
```
* https://stackoverflow.com/questions/65415996/how-to-specify-the-architecture-or-platform-for-a-new-conda-environment-apple

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
# PIP
## Netomi Pip Install

```
pip install --upgrade pip && pip install --extra-index-url http://pypi.netomi.io --trusted-host pypi.netomi.io -r requirements/global_requirements.txt
```

## For handling multiple versions of Pip and Python

```
which python
which pip
python -m pip install elasticsearch
/opt/miniconda3/envs/rag_application/bin/pip install elasticsearch
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


# Error solutions:

* https://github.com/jax-ml/jax/discussions/19343

# AWS CLI Configure

```
(base) anirudh@Netomis-MacBook-Pro ~ % aws configure sso
SSO session name (Recommended): anirudh-netomi
SSO start URL [None]: https://d-906740505a.awsapps.com/start/#
SSO region [None]: us-east-1
SSO registration scopes [sso:account:access]: sso:account:access
Attempting to automatically open the SSO authorization page in your default browser.
If the browser does not open or you wish to use a different device to authorize this request, open the following URL:

https://device.sso.us-east-1.amazonaws.com/

Then enter the code:

NDFJ-CVRB
There are 2 AWS accounts available to you.
Using the account ID 721846126987
The only role available to you is: DevOpsTeamAccess
Using the role name "DevOpsTeamAccess"
CLI default client Region [None]: us-east-1
CLI default output format [None]: json
CLI profile name [DevOpsTeamAccess-721846126987]: anirudh-aws-netomi

To use this profile, specify the profile name using --profile, as shown:

aws s3 ls --profile anirudh-aws-netomi
```