# vernix

technology notes

* cloned from my setup_jekyll repo
```
git clone https://github.com/mattorama/setup_jekyll.git vernix
cd vernix
git remote set-url origin https://github.com/mattorama/vernix.git
git remote add upstream https://github.com/mattorama/vernix.git
```

* create an empty repo on GitHub called vernix

* push the cloned repo to the new repo
```
git push origin master
git push --all
```

* commit changes and push to gh-pages branch
```
git add .
git commit -m "fix url settings for github"
git push origin master
git checkout -b gh-pages
git rebase master
git push origin gh-pages
git checkout master
```
