# Ruby on Rails development using AWS Cloud 9 IDE

# Configure a new Cloud9 Environment on AWS

   * Sign in to Amazon Web Services https://console.aws.amazon.com/
   * Create an IAM Group
   * Create an IAM User and assign to the Group
   * Create a Cloud9 environment
      - open Cloud9 from the 'Services' menu
      - choose 'create environment'
      - enter a name for your dev environment (e.g. development-ruby)
      - in configure settings, choose 'create new instance' and choose t2.micro
  
# Create a Rails application in Cloud9
  
   * In the Cloud9 terminal window, run the following commands:
      - mkdir name-of-app
      - cd name-of-app
      - rvm use ruby-2.4.1@name-of-app --ruby-version --create
      - rails new . -T

# Initialize Git

   * In the Cloud9 terminal window, run the following commands:
     - git config --global user.name "Your Name"
     - git config --global user.email "you@youraddress.com"
     - git config --global push.default matching
     - git config --global alias.co checkout
     - git init

   * Useful git commands:
     - add files to git
       + git add .
       + git commit -am "Commit Message"
       + git push
     - roll back code to last commit
       + git checkout .
     - create and switch to a new branch
       + git checkout -b branch-name
     - switch to a different existing branch
       + git branch branch-name
     - push a branch
       + git push origin branch-name
     - push the master branch
       + git push origin master
     - switch to master branch
       + git checkout master
     - merge branch into master (when in the branch)
       + git merge
     - merge branch into master (when in the master)
       + git merge branch-name
     - delete branch after merging into master
       + git branch -d branch-name
     - see which branch you're on
       + git status
     - resolve merge conflicts visually
       + git mergetool

# Saving code to GitHub

   * In the Cloud9 terminal window, run the following commands:
      - ssh-keygen -t rsa -C "you@youraddress.com" -f ~/.ssh/id_rsa -P ""
      - cat ~/.ssh/id_rsa.pub
      - copy the ssh key
   * In GitHub 
      - go to Settings -> SSH and GPG Keys
         - click on 'New SSH Key'
         - enter a title (e.g. 'Learn Ruby on Rails')
         - paste the ssh key into the 'Key' textarea
      - go to 'Your profile'
         - create a new repository (e.g. 'learn-ruby-on-rails')
         - once created, run the following commands in the Cloud9 terminal window:
            - git remote add origin git@github:user-name/repo-name.git
            - git push -u origin master

# Configure a Run Configuration

   * In Cloud9, go to Run -> Run Configurations -> New Run Configuration
      - in the terminal window:
        - type the name of the application (e.g. 'learn-ruby-on-rails') in the run config name field
        - enter 'rails s -b 0.0.0.0' in the command field
        - click 'CWD', and select the application folder
        - click 'Run' to start the rails server
        
   * Previewing in the browser:
      - go to Preview -> Preview Running Application
      - in the browser window that appears, click the 'pop out into a new window' icon
