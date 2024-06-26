# gitignoreio

This adds a gi command, and wraps git to add .gitignore creation when you run git init.

## Install 

1. Download the .gitignoreio file and place it into your homedir.

2. Add the following line to your .bash_profile, .profile, or .bashrc

```bash
[[ -f ~/.gitignoreio ]] && source ~/.gitignoreio # gitignore.io
```

3. Restart your terminal or type:
```bash
$ source ~/.bash_profile
```

or

```bash
$ source ~/.gitignoreio
```

You will then be able to use the gi command, and calling git init will ask if you want to create .gitignore

## Help

To display the help menu, type gi help or simply gi

```bash
$ gi help
gitignore.io help:
  help - shows this help
  update - force an update of the project types database
  list - lists project types
  search :string: - fuzzy find
  base - create a .gitignore with only the values from EXTRA_LINES
  :type: - creates .gitignore file for a project
```

## Database

On initial launch, it will create a text file in ~/.config/gitignoreio/database.

This file stores all the currently available .gitignore templates. It is updated automatically if you call gi or git init and the database is older than 24h. You can adjust this inside the .gitignoreio file by changing the value DAYS_BEFORE_AUTO_UPDATE. 

## Config

Other config values you can adjust:
* URL Link to the API, or use your own. 
* EXTRA_LINES Lines which will be added by default to every .gitignore
* EXTRA_LINES_COMMENT The comment to denote the extra User Config lines
* DB_FILE The location of the database file

```bash
    local URL="https://www.toptal.com/developers/gitignore/api"
    local EXTRA_LINES=("*.DS_Store" ".env")
    local EXTRA_LINES_COMMENT="# User Config"
    local DB_FILE="$HOME/.config/gitignoreio/database"
    local DAYS_BEFORE_AUTO_UPDATE=1
```
