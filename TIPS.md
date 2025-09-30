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

## [Git] - Remove git branch locally & remotely
```bash
Locally: 
git branch -D branch_name | git branch -D <branch_name>
git branch -d branch_name | git branch -d <branch_name>

Remotely:
git push -d origin branch_name | git push -d <remote_name> <branch_name>

````


## [Git] - Remove node_modules from git

1. Add a `.gitignore` file.
2. Add `node_modules/` config to `.gitignore` file.
3. Run the following commands in Terminal:

```bash
1. git rm -r --cached .
2. git add .
3. git commit -m "chore: add node_modules config to gitignore file"
4. git push
```


## [Git] - Amend the previous log message

```
git commit --amend -m "Your new log message"
```

## [Git] - Print out log infomation in one line

```bash
git log --pretty=oneline --abbrev-commit
```



Note: `--abbrev-commit` would make git log hash become shorter.


## [Git] - Undo last commit with reset
```bash
# The last commit will be removed from your Git history.
git reset --soft HEAD~1
```
## [Git] - Revert a single file
```bash
git checkout c5f567~1 -- file1/to/restore file2/to/restore
```

## [Git] - Update remote origin
```
# solution 1: update remote origin
git remote set-url origin new.git.url/here

# solution2:
# Edit .git/config and change the URLs there.
```

## [Git] - Update git commit information in current repo
```
# Update git commit information in current repo
git config user.name "tjcchen"
git config user.email "tjcchen.engineer@gmail.com"

# Check local and global commit user and email
git config user.name
git config user.email
git config --global user.name
git config --global user.email
```

## [Bash] - Find resources in current directory

```bash
## find by file name
find . -print | grep -i someFileName.java

## find by key words with grep
grep -rn search-string search-dir
```



## [PM2] - Most frquently used commands

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


## [PM2] - Difference between `pm2 save` and `pm2 list`
```sh
pm2 save: Saves the current process list for restoration after a reboot.

pm2 list: Displays all running processes managed by PM2.
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

## [Linux] - Check a folder size on Linux
```bash
# du: disk usage, -s: summary, h: human-readable
du -sh folder-name
```

## [Linux] - Close Chrome CORS
```
open -n /Applications/Google\ Chrome.app/ --args --disable-web-security --user-data-dir=/Users/chen/Documents/MyChromeDevUserData/
```

## [Linux] - Check and close a process, take node as an example
```bash
# find exist node process
ps aux | grep node

# or if we clearly know a specific port is used, then we need to find the process id first, take 3000 port as an example
lsof -i :3000

# kill process by PID(second from the left)
kill -9 PROCESS_ID
```

## [Linux] - Put process into background
```bash
# List all the process
screen -ls

# Create a process with name specified
screen -s name, eg: screen -s ftp or screen -s website

# Enter into a process/background with name specified
screen -r -d 1805

# Detach from a process/background
ctrl a + d
```

## [Linux] - replace old string with new string
```bash
grep "oldString" -rl dist-h5/dist | xargs sed -i "" -e "s/oldString/newString/g" 
```

## [Linux] - check linux & mac processes, and then kill a specific process
```bash
ps -ef | grep processName
kill -9 processId
```

## [Linux] - install node with nvm
```bash
# list remote versions
nvm list-remote

# install a specific node version
nvm install <version> # like: 14.17.6
```

## [Mongo] - login to mongoDB with shell
```bash
mongo host:port/dbname -u username -p password
```
