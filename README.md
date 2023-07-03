"# keyword-winner"
echo "# test" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/hwang2006/keyword-winner-heroku-deployment.git
git push -u origin main
