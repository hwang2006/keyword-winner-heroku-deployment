# keyword-winner-heroku-deployment
This repository serves as a step-by-step guide for connecting your GitHub repository to Heroku, enabling seamless app deployment on the Heroku platform. Heroku is a cloud platform-as-a-service (PaaS) that allows developers to build, deploy, and manage web applications. It provides a streamlined workflow for application deployment, making it easier for developers to focus on coding rather than managing infrastructure.

## Creating a repository on GitHub
1. log on to GitHub, create a repository, and copy the URL.
2. upload your app to the GitHub repository.
```
$ ls -al ./keyword-flask
total 49
drwxr-xr-x 1 quali 197121    0 Jul  3 12:40 ./
drwxr-xr-x 1 quali 197121    0 Jul  3 12:24 ../
drwxr-xr-x 1 quali 197121    0 Jul  3 13:09 .git/
drwxr-xr-x 1 quali 197121    0 Jul  3 12:07 __pycache__/
-rw-r--r-- 1 quali 197121  894 Jul  2 17:29 app.py
-rw-r--r-- 1 quali 197121  148 Jul  1 19:47 Dockerfile
-rw-r--r-- 1 quali 197121 1197 Jul  1 10:56 google_keyword.py
-rw-r--r-- 1 quali 197121   21 Jun 25 16:39 Procfile
-rw-r--r-- 1 quali 197121   21 Jul  3 12:00 README.md
-rw-r--r-- 1 quali 197121  309 Jun 25 15:07 requirements.txt
-rw-r--r-- 1 quali 197121   18 Jun 28 15:24 runtime.txt
drwxr-xr-x 1 quali 197121    0 Jul  3 12:07 static/
drwxr-xr-x 1 quali 197121    0 Jul  3 12:07 templates/

$ git init
$ git commit -m "first commit"
$ git branch -M main
$ git remote add origin https://github.com/hwang2006/keyword-winner-heroku-deployment.git
$ git push -u origin main
```
## Creating a Heroku project 
```
$ heroku login
$ heroku create keyword-winner # heroku create PROJECT-NAME and PROJECT-NAME should be unique
```
Now, you go to heroku.com, making sure that the project named "keyword-winner" has been created.

## Connecting Heroku to the GitHub repository
1. go to the Heroku website and click the project that you have created.
2. Click the following: (1) Deploy - (2) GitHub (Connect to GitHub) as for deployment method
3. Type the name of GitHub repository (e.g., hwang2006/keyword-winner-heroku-deployment).
Once connected successfully, you will see "GitHub Connected" in the deployment method.
```
$ heroku git:remote -a keyword-winner # $ heroku git:remote -a PROJECT-NAME
$ git remove -v
heroku  https://git.heroku.com/keyword-winner.git (fetch)
heroku  https://git.heroku.com/keyword-winner.git (push)
origin  https://github.com/hwang2006/keyword-winner-heroku-deployment.git (fetch)
origin  https://github.com/hwang2006/keyword-winner-heroku-deployment.git (push)
```
## Deploying 
You have two options to deploy your app. 
- Enable automatic deploys from GitHub: when the GitHub project is updated, it will be automatically updated.
- Deploy a GitHub branch: manually update by pressing the 'Deploy Branch' button.

Once the deployment is complete, you can confirm the deployed application by clicking the 'View' button, which will connect you to the deployed application. That's it!!

Here is the keyword-winner app deployed on Heroku:
- [keyword-winner](https://keyword-winner-39a53d276a1b.herokuapp.com/)
