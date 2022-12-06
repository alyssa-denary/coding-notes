
-  .gitignore [https://zellwk.com/blog/gitignore/](https://zellwk.com/blog/gitignore/)tldr: for all git repos, add a .gitignore file, add system tiles (`Thumbs.db` for Windows, `.DS_Store` for Mac) and `node_modules`

______________________________________________________________
![[gitignore-1670340132050.jpeg]]
[https://github.com/2DegreesInvesting/resources/issues/115](https://github.com/2DegreesInvesting/resources/issues/115)

![[gitignore-1670340156475.jpeg]]
```
echo .DS_Store >> ~/.gitignore_global
git config --global core.excludesfile ~/.gitignore_global
```

![[gitignore-1670340190306.jpeg]]
```
config = {
gitIgnore: {}
anotherGitProp: {}
etc...
}
```


![[gitignore-1670340216195.jpeg]]
```
git rm --cached FILENAME
```


![[gitignore-1670340267672.jpeg]]