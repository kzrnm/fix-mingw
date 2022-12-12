# Fix MinGW

In GitHub Actions `windows-2022` runner, `gcc` of MinGW is hidden by Strawberry. 
https://github.com/actions/runner-images/issues/5459

The action fix the problem.


## What the action doing?

Rewrite `$PATH`.

old

```
.......;C:\Strawberry\c\bin;C:\Strawberry\perl\site\bin;C:\Strawberry\perl\bin;.....;C:\Program Files\Git\mingw64\bin;....
```

new

```
C:\Program Files\Git\mingw64\bin;.......;C:\Strawberry\c\bin;C:\Strawberry\perl\site\bin;C:\Strawberry\perl\bin;.....;C:\Program Files\Git\mingw64\bin;....
```