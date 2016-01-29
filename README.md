# ldap_printer
LDAP based printer 

## Installation
- Make sure you have sudo permissions and python 2 installed. This project is written only for linux based OS
- Make sure firefox is installed in system and can be triggered using `firefox` command
- Install dependencies

  ```bash
  sudo apt-get install python-dev python-pip libcups2-dev
  ```
- Install python dependencies by running `sudo pip install -r requirements.txt`
- Run installation script as `bash install.sh` or `./install.sh`
- Add `/usr/local/ldap_printer` in `/etc/sudoers` secure path.
- Delete this directory

## Usage
- Add the list of roll numbers who are enlisted in the hostel mess to data/roll\_no\_list.txt
- To print a file run command `ldap_print`
- To get account information of all users run `sudo rootaccount.py`. You need to be a sudo user. You will find the resultant file in data/printer\_account.csv. It can even be called from any location as `rootaccount.py desired\_filename.csv` 
- For a new batch of accounting, empty the entries completely (don't leave even a space) from data/printer\_account.csv and data/account.csv

## Development
- Install python development kit by 

  ```bash
     sudo apt-get install python-dev python-pip libcups2-dev
  ```

### virtualenv configuration
- **Ignore these steps if you're familiar with virtualenv**
- Install necessary dependencies by running `sudo pip install virtualenv virtualenvwrapper`
- Add following lines to your `~/.bashrc`

  ```bash
    
  export WORKON_HOME=~/.envs
  mkdir -p $WORKON_HOME
  source /usr/local/bin/virtualenvwrapper.sh
  ```
- Create virtualenv by `mkvirtualenv ldap-printer`. Deactivate by `deactivate` and again activate by `workon ldap-printer`

### Installation for development
- Install Python dependencies by running `pip install -r requirements.txt`
- cpp wrapper is generated by running `python generate_wrapper.py`. Compile it with `g++` to get executable file
- Directly run application by `python printmain.py`


## Uninstall
- Delete project directory from `/usr/local/ldap_printer`
- Remove environment variable from `/etc/profile.d/ldap_printer.sh`
