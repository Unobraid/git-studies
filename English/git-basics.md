Languages Available: [English](INSTALLATION.md)

# Git Basics

For this section, I'll cover the process to import, install and setup Git on Linux and Windows according to the [Platform Spectifications](README.md).

# Linux (Arch Distro)

### Installation

For this part, It's assumed that you a have a machine with Linux already running on It, internet acess and everything up-to-date.

1. Open the terminal (Usually by the hotkey CTRL+ALT+T, In my case is the **Konsole**).
2. Type: `pacman -S git` (You'll be intalling the core Git package).
   1. If you get any errors, try using `sudo` or running the command as root.
3. That's It, now you have the git library installed.

### Local Repository

With git intalled, now we can move to create our first repository.

1. Find or create a folder that you want to use as your repo. (I suggest to make a mother Git folder and other subfolders inside for all the repos that you'll be creating).
2. Make sure to be on the right folder and type: `git init` (Now you have a local repository).
3. Finally we need to set your account identify (I suggest to use your GiHub credentials).
   1. Type: `git config --global user.email "you@example.com"`
   2. Type: `git config --global user.name "Username"`
   3. If you want individual credentials for this an other repos omit the `--global` part.

### Remote Repository

If you want to work on your repository from multiple places, or have many people working together, you'll need to sync your local repo with a remote one.

1. Go to [GitHub](https://github.com), create an account and add a new empty repository like [this](GITHUB-REPO.md).
2. Open the terminal again and type: `git remote add origin git@github.com:Username/RepoName.git` (Now your local repo now where to push and pull information and files).
   1. The Username and RepoName are as stated, your GitHub username and the name of the repo you just created.

### Adding Files

With the repo ready, we can add our first file. Anything will do, but a readme to be displayed on GitHub would be a nice choice.*

1. Create a new markdown file typing: `nano README.md` (Im using nano here, but any text editor will do).
2. Edit the file with anything that you want, like "Hello World" or what not.
3. After that type: `git add filename.extension` (This add the individual file to the list of changes to be made, aka: commited).
   1. You can also type: `git add .` (This way, you add all the files changed whitin the folder).

### Commiting Changes

Now that you changed and added all the files, It's time to apply those changes.

1. To check the stauts of the files to be commited you can type: `git status`
2. Make sure that you have set your credential or else you be prompted to do so, then type: `git commit -m "Commit Message"`.
   1. If you want to check the commits history log type: `git log`.

### Pushing Changes

After commiting everything that is needed, now we send those changes to the remote repo.

1. Make sure you are using the correct branch, so type: `git branch -M main`.`
   1. The dafault branch for GitHub is **main**, but you can use whatever you want.
2. Finally type: `git push -u origin main` (Your commits will be pushed to the remote repo on GitHub).
   1. After the first push, you´ll only need to use `git push`, as the origin and branch are already set.
