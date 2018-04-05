# Git Server For Multi-User

> Running in docker. The user created is a real linux user but cannot login. Different users' repository cannot be accessed to each other.

## Install

```bash
docker run -itd  -p2022:22 --name git-server git-server:1.0
```

## RUN

```bash
# create a user
docker exec git-server create_user username password

# create a  repository for a user
docker exec git-server create_project username repository

# clone
git clone ssh://username@127.0.0.1:2022/git_codes/username/repository.git

# push
git push origin master
```

<br>
You can also run commands inside docker, such as:

```bash
# in docker
docker exec -it git-server sh

# create a user
create_user username password

# create a repository for a user
create_project username repository
```

-------
Contact me in [Weibo](https://weibo.com/shiboooo)
