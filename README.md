# grep-checkout
checkout the branch matching a grep

Since my branch names always contain a reference to an issue/ticket, but that is at the end of the branch name, I created this little function to make checking out a branch based on the ticket number easier.

example branch name `bug/some-bug-happened-JIRA-707`
example usage `co 707` or `co JIRA-707`

If more than one branch matches, it picks the first.

## Install
add this to your .bash_profile
```
function co {
  term=`git branch | grep -m 1 "$1"`
  git checkout $term
}
export -f co
```
