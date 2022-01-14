# Hide Email Address from expose

By default when you commit on a repo the associated email to your GitHub account will be visible to others

to see it you can run:

`git log`

and in the output you will see something like this:
```
commit 2750b03d990c1ecccxxxxxxxxxxxxxxxx
Author: John Smith <john.smith@domain.com>
Date:   Mon Jan 10 20:41:47 2022 -0800
```

## How to fix this

Github has a feature to address this issue. It will create an anonymous hashed email address based on your github username

1- Go to github.com and login with your account
2- Click on your profile image at top right corner of screen
3- Click on settings then go to emails tab
4- Enable `Keep my email addresses private`
5- After you enable this the generated email address will be shown on the bottom of checkbox
6- Copy email address and run `git config user.email <your-github-generated-hashed-email>` in the repository dir. (if you want to enable this feature globally you can add `--flag` to this command) 
