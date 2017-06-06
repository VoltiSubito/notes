# Git

## [Git Book](https://git-scm.com/book/en/v2)

## [Submodules](https://git-scm.com/book/en/v2/Git-Tools-Submodules)
### [The page I always end up at](https://chrisjean.com/git-submodules-adding-using-removing-and-updating/)

### Adding a Submodule
  + `git submodule add {repo} {local path}`

### After cloning a repo with submodules
  + `git submodule init`
  + `git submodule update`

### Getting updates from submodules
  + `git submodule update --init --recursive`

## Other
  + Pruning branches no longer on origin 
    + `git fetch --prune`
  + Changing user information for a single repo
    + CD into specific repo
    + `git config --local user.email "an@email.address"
