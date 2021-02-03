## [Git] - Delete .DS_Store files on Mac

1. Find all the .`DS_Store` files in current repo, and remove them with `git rm`.

   ```bash
   find . -name .DS_Store -print0 | xargs -0 git rm -f --ignore-unmatch
   ```

2. Add `.DS_Store` config to `.gitignore` file.

   ```bash
   # MISC
   .DS_Store
   ```

3. `Git add` & `Git commit`.

   ```bash
   git add .
   
   git commit -m "chore: remove .DS_Store files"
   ```



Note: In the Apple macOS operating system, **.DS_Store** is a file that stores custom attributes of its containing folder, such as the position of icons or the choice of a background image.



## [Git] - Print out log infomation in one line

```bash
git log --pretty=oneline --abbrev-commit
```



Note: `--abbrev-commit` would make git log hash become shorter.



## [Bash] - Find resources in current directory

```bash
## find by file name
find . -print | grep -i someFileName.java

## find by key words with grep
grep -rn search-string search-dir
```

