# Git things


## Proxy:
´´´git config --global http.proxy http://u620772:TVD5rhwn2svEllUc\!@bastet-test.corp.cablevision.com.ar:80´´´
´´´git config --global https.proxy http://u620772:TVD5rhwn2svEllUc\!@bastet-test.corp.cablevision.com.ar:80´´´

## Actualizar fork (ej.: github)
´´´
# If you haven't already added an upstream source, set your upstream
# to the fork's original source
git remote add upstream <url_to_original>

# Verify upstream is correct, you should see the URL for the upstream fetch and push
git remote -v

# Get all recent branches and commits from the upstream
git fetch upstream

# Check out your current master branch
git checkout master

# Merge the branches and commits from the upstream
git merge upstream/master

# Push the updated master to your forked remote repository
git push origin master
´´´