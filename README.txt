--> Remove directory from git but NOT local
git rm -r --cached myFolder

--> Remove a file from git but NOT local
git rm --cached path/to/file

--> Download only latest version of repo
git clone --depth=1 <remote_repo_url>

--> Rename old email
$ git filter-branch --env-filter '
WRONG_EMAIL="old-email@gmail.com"
NEW_NAME="New Name"
NEW_EMAIL="new-mail@gmail.com"

if [ "$GIT_COMMITTER_EMAIL" = "$WRONG_EMAIL" ]
then
    export GIT_COMMITTER_NAME="$NEW_NAME"
    export GIT_COMMITTER_EMAIL="$NEW_EMAIL"
fi
if [ "$GIT_AUTHOR_EMAIL" = "$WRONG_EMAIL" ]
then
    export GIT_AUTHOR_NAME="$NEW_NAME"
    export GIT_AUTHOR_EMAIL="$NEW_EMAIL"
fi
' --tag-name-filter cat -- --branches --tags

-->  Show all users and the number of commits
git shortlog --summary --numbered -e

--> Undo a git add - remove files staged for a git commit
git reset filename.txt

To undo git add . use git reset (no dot).