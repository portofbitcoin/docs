# Setting up a website

You're not much of a sovereign individual if you don't have a personal website, amiright? Fortunately if you can manage the basics of using the command line, Git and have GitHub setup it has never been easier to get a website setup where you can post your name/pseudonym, PGP key, contact details and most importantly Bitcoin addresses and Lightning node info. 

We are going to use the easiest and quickest way to get a website up. Of course there are many options here but remember simplicity!

The instructions for getting a GitHub Pages site up are [here](https://pages.github.com/).

You have to create a repository named `username.github.io` where `username` is your GitHub username.

Clone the new repository as we learnt in the Git section (ADD LINK):

`git clone git@github.com:username/username.github.io.git`

Now `cd` into this newly created directory:

`cd username.github.io`

Create an `index.html` file in this directory:

`touch index.html`

Open this file and type whatever you like, it is traditional to write "Hello World":

`vim index.html`

Press `i` for insert

Type `Hello World!`

Press `:x` to save and exit

Now `git add`, `git commit` and `git push`:

```
git add index.html
git commit -m "Initial commit"
git push origin master
```

Open up a browser, go to the https://username.github.io site and you should see your "Hello World!" message. You now have a site up!

Perform similar steps to add your PGP key, Bitcoin address etc.

If you want a website domain that is a little catchier than https://username.github.io you can go to namecheap.com or any other domain name registrar and buy one.

ADD INSTRUCTIONS for mapping GitHub pages site to custom domain


  
