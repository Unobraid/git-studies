Languages Available: [English](INSTALLATION.md)

### ← [Return](../README.md)

# Git Basics

These are the basics of using Git with GitHub.

### Installation

A working Linux machine (I'm using Arch Linux), internet access and everything up-to-date are required.

1. Open the terminal (I'm using **Konsole**).
2. Install the core Git package with `pacman -S git`.
   * If you get any errors, run the command as root or use `sudo`.

### Local Repository

With git intalled, you can create a local repo.

1. Select a folder that will be used as the repo root.
2. To initizalize the repo on the folder use `git init`.
3. An account identify is needed for signing the commits (Use the same credentials for the GitHub account).
   * Set the email with `git config --global user.email "you@example.com"`
   * Set the name with `git config --global user.name "Username"`
   * For and individual identity on the repo, remove `--global` from the command.

### Remote Repository

To export a local repo to other machines over the web, a remote repo is needed.

1. Go to [GitHub](https://github.com), create an account and add a new empty repository.
2. On GitHub, copy the repo SSH key, It should look like `git@github.com:Username/RepoName.git`.
3. In the terminal use `git remote add origin git@github.com:Username/RepoName.git`.
   * Now the local and remote repos are linked.

### SSH Authentication

To access and modify remote repos, a form of authentication is needed like a SSH key.

1. To generate a new key use `ssh-keygen -t ed25519 -C "youremail@example.com"`
   * The key can be saved on the default location.
   * The passphrase can be null.
2. Initiate the SSH-agent with `eval "$(ssh-agent -s)"`.
3. The key need to be added to the SSH-agent with `ssh-add ~/.ssh/id_ed25519`.
4. Copy the contents of the SSH key file that should be `~/.ssh/id_ed25519.pub`.
5. Go to [GitHub](https://github.com), settings, SSH & GPG keys and add the SSH key from the previous file.

### Adding Files

The repo isready, a first file will be needed to commit the first change.*

1. Create a new markdown file with `nano README.md` (Im using Nano).
2. Edit the file and type any content like `# Hello World`.
3. Add the file to the list of changes with `git add filename.extension`.
   * You can also use `git add .` to add all the files on the repo folder to changes list.

### Commiting Changes

With all the files and changes added to the list, they need to be commited.

1. A commit needs a message to be made, so use `git commit -m "Commit Message"`.
   * To check the status of the files before commiting use `git status`.
   * A log of previous commits can be seen with `git log`.

### Pushing Commits

After commiting all the local changes, they need to be pushed to the remote repo.

1. To select the repo branch needed use `git branch -M main`.`
   * The dafault branch for GitHub is main.
2. To push the commits use `git push -u origin main`.
   * With the origin and branch set after the first push, a short `git push` can be used as well.
