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



## [Git] - Remove node_modules from git

1. Add a `.gitignore` file.
2. Add `node_modules/` config to `.gitignore` file.
3. Run the following commands in Terminal:

```bash
- git rm -r --cached .
- git add .
- git commit -m "chore: add node_modules config to gitignore file"
- git push
```



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



## [Pm2] - Most frquently used commands

PM2 is a daemon process manager that will help you manage and keep your application online 24/7. For more information, please also refer to: https://pm2.keymetrics.io/

```bash
Globally Installed: npm install -g pm2

## After entering into root directory:
Restart application/process: pm2 start bin/www or pm2 start app.js

Rename application/process: pm2 start app.js --name web123

Add application to watch: pm2 start bin/www --watch

End application/process: pm2 stop www

End all the applications/processes: pm2 stop all

Delete all the applications/processes: pm2 delete all

List all the applications/processes: pm2 list

Check application status: pm2 describe www

Check application resource usages: pm2 monit

Check application logs: pm2 logs

Check specified application logs: pm2 logs www

Restart application: pm2 restart www

Restart all the applications: pm2 restart all
```



## [Curl] - Most frequently used commands

Curl is a command-line tool for transferring data specified with URL syntax. For more information, please also refer to this link: https://github.com/curl/curl

Curl parameters meaning explained:

`-d, --data <data>` Send specified data in POST request.

`-H, --header <header>` Headers to supply with request.

`-X, --request` The request method to use. Request methods could be GET, POST, PUT, DELETE, OPTIONS etc.

`-s, --slient` Slient mode. The command will not print out anything to the command line.

```bash
## GET simple
curl -X GET https://www.baidu.com
or
curl https://www.baidu.com

## POST application/x-www-form-urlencoded( default )
curl -d "param1=value1&param2=value2" -X POST http://localhost:3000/data

## POST with a data file
curl -d "@data.txt" -X POST http://localhost:3000/data

## POST with application/json
curl -d '{"key1":"value1", "key2":"value2"}' -H "Content-Type: application/json" -X POST http://localhost:3000/data

## POST with a data file
curl -d "@data.json" -X POST http://localhost:3000/data
```


## [Linux] - Add & remove writable permission
```bash
add: chmod u+w file_name

remove: chmod u-w file_name
```


## [Linux] - Add global alias command
Take `ll` as a example:
```bash
# edit ./bash_profile file
vi ~/.bash_profile

# add the following line of code
alias ll='ls -l'
```

## [Linux] - Close Chrome CORS
```
open -n /Applications/Google\ Chrome.app/ --args --disable-web-security --user-data-dir=/Users/chen/Documents/MyChromeDevUserData/
```
