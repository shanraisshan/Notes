# Terminal
must have terminal commands

# DOCKER
```
docker-compose up --build: start/run services in docker-compose.yml
docker-compose up --build -d: exit
```

# MAC OS
```
exit: Ctrl C
ls: Lists files in the default folder
mv: Moves a file
touch: Creates a text file
mkdir: Creates a directory
rmdir: Removes an empty directory
rm -R: Removes nested directories
sudo: Executes commands with superuser privileges
top: Lists actively running computer processes
ditto: Copies contents of a folder to a new folder
```

# MONGO DB

install
```
brew tap mongodb/brew
brew install mongodb-community
```

confirm
```
shayanrais@Shayans-MacBook-Pro ~ % which mongod
/opt/homebrew/bin/mongod
```

To start MongoDB in the background and keep it running:
```
brew services start mongodb-community
```

view MongoDB locally
```
mongosh
use dealflow_db
show collections
db.contacts.find().pretty()
```

# PHP
```
php artisan serve: start local dev server for laravel app
```

# PYTHON
pip: Pip Installs Packages

run script
```
python main.py
```
create venv
```
python3 -m venv venv
source venv/bin/activate
```
**FAST API**
```
pip install -r requirements.txt
uvicorn main:app --reload
```

# REACT NATIVE
npm: Node Package Manager
yarn: Yet another resource negotiator

default react native commands in package.json,
```
"android": "react-native run-android",
"ios": "react-native run-ios",
"start": "react-native start",
```
can be used by
```
npm start
npm run android
```

# SSH

### 2 Diff Github SSH on Single Mac 
1. Open terminal (Cmd+Space)
2. Check if you have an SSH key by running
```
ls -al ~/.ssh
```

3. If you see files like id_rsa and id_rsa.pub, you have an SSH key.
4. Generate new one
```
ssh-keygen -t rsa -b 4096 -C "shanraisshan@gmail.com"
```
5. Name it shanraisshan, 2 new files (shanraisshan, shanraisshan.pub) will be generated at /Users/sav-dev-shayanrais
6. Copy these files to /Users/sav-dev-shayanrais/.ssh/
7. Add the SSH key to ssh-agent (eval)
```
(base) sav-dev-shayanrais@DLB-DEV-SHAYANRAIS ~ % eval "$(ssh-agent -s)"
ssh-add ~/.ssh/shanraisshan
Agent pid 1780
Enter passphrase for /Users/sav-dev-shayanrais/.ssh/shanraisshan: 
Identity added: /Users/sav-dev-shayanrais/.ssh/shanraisshan (shanraisshan@gmail.com)
```
8. Copy the public key to clipboard
```
pbcopy < ~/.ssh/shanraisshan.pub
```
9. Go to GitHub > Settings > SSH and GPG keys > New SSH key, paste the key, and save.
10. Now clone the project using ssh url

⚠️ if you have more than 1 accounts in single computer, you need to active the account using ```eval``` command, and then cross check using ```ssh -T git@github.com```
