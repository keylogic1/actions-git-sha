# actions-git-sha
Retrieve git sha from a remote repository

## Usage
### Public repository
```
uses: keylogic1/actions-git-sha@main
with:
  repo: "https://github.com/keylogic1/dotfiles.git"

```

### Private repository
```
uses: keylogic1/actions-git-sha@main
with:
  username: "${{ github.actor }}"
  password: "${{ secrets.TOKEN }}"
  repo: "https://github.com/keylogic1/git-sha-test.git"
```

### Non-default branch
```
uses: keylogic1/actions-git-sha@main
with:
  repo: "https://github.com/keylogic1/dotfiles.git"
  branch: "git-sha-test"
```

### Using the output in a later step
```
- name: Retrieve sha from a repo
  id: remote_sha
  uses: keylogic1/actions-git-sha@main
  with:
    repo: "https://github.com/keylogic1/dotfiles.git"

- name: Print sha
  run: echo "The sha is ${{ steps.remote_sha.outputs.sha }}"
```

## Inputs
* `repo` - The remote repository you want the sha from
* `branch` - (optional) the branch you want the sha from
* `username` - (optional) the username for a private repository
* `password` - (optional) the password or token for a private repository

## Outputs
* `sha` - The git sha
