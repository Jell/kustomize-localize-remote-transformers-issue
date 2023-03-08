# kustomize localize issue with remote transformers

To reproduce:

```
kustomize localize example/
```

The image in `config.yaml` doesn't matter to reproduce the issue as the bug happens before the image is fetched.

Kustomize version 5.0.0 fails with this error:

```
Error: unable to localize target ".": unable to load transformers entry: unable to load resource entry "git@github.com:Jell/kustomize-localize-remote-transformers-issue?ref=main": when parsing as inline received error: missing Resource metadata
when parsing as filepath received error: invalid file reference: evalsymlink failure on '/Users/jell/Reify/kustomize-issue-4958/example/git@github.com:Jell/kustomize-localize-remote-transformers-issue?ref=main' : lstat /Users/jell/Reify/kustomize-issue-4958/example/git@github.com:Jell: no such file or directory
```
