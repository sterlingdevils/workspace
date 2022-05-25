# workspace
go workspace for developing gobase,pipelines,ratelimiter, etc.

This is using git submodules,  when cloning use:
```
git clone --recurse-submodules git@github.com:sterlingdevils/workspace.git
```

if you already have this cloned or forgot the --recurse-submodule do:
```
git submodule update --init --recursive
```

For developing, its nice to have the submodules not on a detached head.  To checkout main on each submodule:
```
git submodule foreach 'git switch main'
```

To use a different SSH key, you need to run your git config command in the workspace and all submodules:
```
git config core.sshCommand "ssh -i ~/.ssh/id_rsa_home"
git submodule foreach 'git config core.sshCommand "ssh -i ~/.ssh/id_rsa_home"'
```

After you make updates to a submodule and commit them.  Please update the submodule in the workspace repo and commit it.

Versions:
go 1.18.2
git 2.31.1
