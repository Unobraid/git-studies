Languages Available: [English](INSTALLATION.md)

### ← [Return](../README.md)

# Git Basics

These are the basics of using Git with GitHub.

### Installation

A working Linux machine (In my case Arch distro) and internet access are required.

1. Try `pacman -S git`
* In case of errors, run as root or use `sudo`.

### Local Repository

With git intalled, create a local repo.

1. Select a folder to host the repo.
2. `git init`
3. `git config --global user.email "you@example.com"`
4. `git config --global user.name "Username"`
* Credentials are needed for commits, try to use the same identity as in GitHub.
* For an individual identity on the repo, remove `--global`
* More about `git-init` on [git-init](https://git-scm.com/docs/git-init), and `git config` on [git-config](https://git-scm.com/docs/git-config).

### Remote Repository

To sync a local repo over the web, create a remote repo.

1. Create an account on [GitHub](https://github.com).
2. Add a new empty repo.
3. Copy the repo SSH key, It should look like `git@github.com:Username/RepoName.git`
4. `git remote add origin git@github.com:Username/RepoName.git`
* There ar HTTPS and SSH keys, copy the correct one.
* More about `git remote` on [git-remote](https://git-scm.com/docs/git-remote).

### SSH Authentication

To access and modify remote repos, a form of authentication is needed.

1. `ssh-keygen -t ed25519 -C "youremail@example.com"`
2. `eval "$(ssh-agent -s)"`
3. `ssh-add ~/.ssh/id_ed25519`
4. Copy the contents of the SSH key file `~/.ssh/id_ed25519.pub`
5. Go to [GitHub](https://github.com) settings and add the copied SSH key.
* The key can be saved on a default location and the passphrase can be null.
* More about generating SSH keys [here](https://docs.github.com/en/free-pro-team@latest/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent#).

### Adding Files

A file is needed to make the first commit.

1. `nano README.md`
2. Edit the file and type any content, like *# Hello World*.
3. `git add filename.extension`
* Any text editor can be used, nano is being used here.
* Using `git add .` will add all files on the folder to the changes list.
* More about `git add` on [git-add](https://git-scm.com/docs/git-add).

### Commiting Changes

With all the files and changes added to the list, they can be commited.

1. `git commit -m "Commit Message"`.
* A message is needed for a commit to be made.
* To check the status of the files before commiting use `git status`
* A log of previous commits can be seen with `git log`
* More about `git commit` on [git-commit](https://git-scm.com/docs/git-commit).

### Pushing Commits

After commiting all the local changes, they can be pushed to the remote repo.

1. `git branch -M main`
2. `git push -u origin main`
* The dafault branch on GitHub is main.
* With the origin and branch set after the first push, a short `git push` can be used as well.
* More about `git branch` on [git-branch](https://git-scm.com/docs/git-branch), and `git push` on [git-push](https://git-scm.com/docs/git-push).
