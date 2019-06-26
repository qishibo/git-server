# Git Server For Multi-User

> Running in docker, just like a simple gitlab. The user created is a real linux user but cannot login. Different users' repository cannot be accessed to each other.

## Install

```bash
docker run -itd  -p2022:22 --name git-server qii404/git-server:latest
```

## RUN

```bash
# create a user
docker exec git-server create_user username password

# create a  repository for a user
docker exec git-server create_project username repository

# clone
git clone ssh://username@127.0.0.1:2022/git_codes/username/repository.git
# enter password

# push
git push origin master
```


You can also run commands inside docker, such as:

```bash
# in docker
docker exec -it git-server sh

# create a user
create_user username password

# create a repository for a user
create_project username repository
```

## Tips

If you want to exec `ssh username@127.0.0.1 -p2022` to login git server, you will get this error:

```bash
> You Wanna Login ?? No Way!!
> fatal: Interactive git shell is not enabled.
> hint: ~/git-shell-commands should exist and have read and execute access.
> Connection to 127.0.0.1 closed.
```

-------
Contact me in [Weibo](https://weibo.com/shiboooo), or [qii404.me](https://qii404.me)
