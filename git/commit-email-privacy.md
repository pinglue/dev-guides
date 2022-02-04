# Hide your email address from public exposure

did you know that your personal email address may be saved into every commit you make in Github (and other public repos)? And this way everybody can see it? so next time that received tons of spam emails and offers for viagra and 
ludicrous offers you may become interested in reading this guide:

In general, any commit on git (any git system, not just Github) saves the author name and email in it. To see what name and email are used for you try:

```
git config user.name
```

and 

```
git config user.email
```

If the outcome of the above commands (specially the last one) is not favorable to you, then you need to change them as explained below. One more thing to learn, is that, in your repo you can use `git log` to see these info for all the commits:

you will see something like this:
```
commit 2750b03d990c1ecccxxxxxxxxxxxxxxxx
Author: John Smith <john.smith@domain.com>
Date:   Mon Jan 10 20:41:47 2022 -0800

... more block similar to above

```

Note the *Author* field in the commits.

## How to hide your email address

Setting your email to some random string is not a good idea (like using `git config user.email non@not.no`). This is because your email is used in Github to track your contribution. If you do this, your Github contribution will be zero (no green dot!). 

A better way is this: Github has a feature to create an anonymous hashed email address for you:

1- Go to github.com and login with your account
2- Click on your profile image at top right corner of screen
3- Click on settings then go to emails tab
4- Enable `Keep my email addresses private`
5- After you enable this the generated email address will be shown on the bottom of checkbox
6- Copy email address and run `git config user.email <your-github-generated-hashed-email>` in the repository dir. (if you want to enable this feature globally you can add `--flag` to this command) 

This Github generated email make you known to Github and at the same time keep you hidden from the public view, in particular spammers.