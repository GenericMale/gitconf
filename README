# (Arch)Linux Config & Dotfile Backup Script

Git wrapper to version system configuration and user dotfiles.

File permissions and ownership is tracked in a ACL file and restored on clone.

Special git(hub) files like the README, .gitattributes, LICENSE etc
are not checked out but can be modified using the 'edit' command.

The working tree can be changed by setting the GITCONF_WORKTREE env var.
By default / is used, which will use sudo to restore files.
If GITCONF_WORKTREE is set to a user writeable director (e.g. $HOME),
no privilege escalation is required.

## Usage

### Initialization
To initialize a new bare git repository to store dotfiles metadata, set up sparse checkout, and create an initial commit, use the following command:

```bash
gitconf init [remote_url]
```

Replace `[remote_url]` with the URL of your remote repository (optional).

### Cloning
To clone an existing configuration repository and integrate it with the specified work tree (defaulting to /), use the following command:

```bash
gitconf clone [remote_url]
```

Replace `[remote_url]` with the URL of your remote repository. If existing files clash with repository files, they must be manually resolved.

### Listing Untracked Files
To list modified and user-created files under /etc that are not yet tracked by git, use the following command:

```bash
gitconf untracked
```
This helps identify configuration files that should be added to the configuration repository.

### Editing the README
To open the repository's README file in a text editor, allowing you to modify it, use the following command:

```bash
gitconf edit README
```
Changes are then committed to the repository. The edit command can be used with every file in the repo or also to ceate new files.

### Other Git Commands
All other git commands can be passed used directly:

```bash
gitconf [git_command] [git_options]
```

For example:

```bash
gitconf add /etc/pacman.conf
gitconf add ~/.config/nvim/init.lua
gitconf commit -m "Add dotfiles"
gitconf push
