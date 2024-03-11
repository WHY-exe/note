# Initializing git config

First thing first do, initializing your email and username which would be included in every git commit.

```shell
git config --global user.name <your_name>
git config --global user.email <your_email>
```

There are two things comming around here: **config** and **--global**

As you may expected here, git store its configuration as a file store in somewhere. There are 3 possible places where config file would be stored:

1. **[path]/etc/profile**: it contains value applied to every user in the system. You would run **git config** with **--system** option admin privilege in order to make changes to the file
2. **~/.gitconfig** or **~/.config/git/git**: "~" means user's home dir. This config file applied to specific user. Running **git config** with **--global** option would read or write this file
3. **<path_to_your_repo>/.git/config**: This file applied to the repo you currently working in

So what we doing up there is simply setting up the username and email for our current user.

If we want to view the git settings and where they comming from, we can use the command listed below:

```
git config --list --show-origin
```

# Setting up credential helper

If your are not using some fancy git GUI helper, you might want to store your password and username of your remote git repo account so that you don't have to type username and  password every time you pull or commit somthing to your remote repos. You could use the following command

```
git config (--global) credential.helper (store/manager)
```

The **store** command would come with the option **--file** to specify the path which credential file would be stored. By default it would store the credential infomation in the ` ~/.git-credential` or $XDG_CONFIG_HOME/git/credentials

On windows you could specify the **Git Credential Manager** useing the Windows Credential Store which provide a easy-to-use GUI by using the **manager** command

There is also a **cache** command which store the credential infomation in the memory with a certain period of time (15 min).

# Setting up proxy

You would have many good reasons to use git with the proxy. The git proxy could be stored as the config every time you use git in certain position and a temporary option for a git command. To use it as a store config, you could use:

```
git config --global http.proxy 'http://192.168.0.1:1080'
git config --global https.proxy 'http://192.168.0.1:1080'
```

To use it as a temporary option:

```
git clone <git_repo_url> --config(-c) "http(s).proxy=http(s)://<your_proxy_address>:<your_proxy_port>"
```

Normally, you would expect your vpn client is setuped on a certain port of the localhost
