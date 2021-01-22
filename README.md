# coding_notes

## Git

### Clone down repo

  - In terminal `cd ~/projects`
  - `git clone git@github.com:opencollective/opencollective-frontend.git`
    - NOTE: need [SSH set up](https://docs.github.com/en/github/authenticating-to-github/adding-a-new-ssh-key-to-your-github-account) to use git@github style repo addresses
  - `cd opencollective-frontend`
  
### Create a pull request

#### Update master branch

  - `git checkout master` Change to master branch
    - NOTE: if you have uncommitted changes it won't let you change branch. Run `git checkout .` to wipe away all uncommited changes (or commit)
  - `git pull origin master`
    - pull latest changes from: the "origin" remote (github here) and the "master" branch.
    - NOTE: this command pulls those changes into whatever branch you are currently standing in
    - NOTE: conflicts are possible (ask me)
  - Now master branch is up to date

#### Create a branch

  - `git checkout -b fix_typo` fix_typo is new branch name
    - zsh will show branch as `fix_typo`
    - to confirm what branch you're on: `git branch`

#### Make changes on branch
  
  - `git checkout fix_typos`
  - `git pull origin master` pulls in any changes made by others
  - Open text editor
  - Make changes
  - Save
  
#### Visually confirm changes

  - Go to terminal
  - Press enter and see ✗
  - `git status` shows files with changes
  - `git diff` shows actual changes
    
#### Commit to branch

Do this in small chunks by logical category, or when done for the day

 - we "stage" the files
    - this means mark them as wanting to include in a commit
    - `git add README.md`
    - `git add translations/*.json` gets you all json files in the translations folder
    - `git add --all` adds ALL files with changes 
 - we "commit" the staged files
    - git commit -m "update to README with new contributor section"
    - `git status` to check files not stages anymore
    
#### Push branch to origin (github)
Push every time you commit

- `git checkout fix_typo` (move to the branch you want to push)
- `git push origin fix_typo` (pushing my branch's state to my branch on the origin repo)

#### Open a pull request
