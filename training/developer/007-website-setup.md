# Setting up a website

You're not much of a sovereign individual if you don't have a personal website, amiright? Fortunately if you can manage the basics of using the command line, Git and have GitHub setup it has never been easier to get a website setup where you can post your name/pseudonym, PGP key, contact details and most importantly Bitcoin addresses and Lightning node info. 

We are going to use the easiest and quickest way to get a website up. Of course there are many options here but remember simplicity!

The instructions for getting a GitHub Pages site up are [here](https://pages.github.com/).

You have to create a repository named `username.github.io` where `username` is your GitHub username.

Clone the new repository as we learnt in the [Git section](https://github.com/portofbitcoin/docs/blob/master/training/developer/005-git.md):

`git clone git@github.com:username/username.github.io.git`

Now `cd` into this newly created directory:

`cd username.github.io`

Create an `index.html` file in this directory:

`touch index.html`

Open this file and type whatever you like, it is traditional to write "Hello World!":

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

Open up a browser, go to the `https://username.github.io` site and you should see your "Hello World!" message. You now have a site up!

Perform similar steps to add your PGP key, Bitcoin address etc.

If you want a website domain that is a little catchier than `https://username.github.io` you can go to [namecheap.com](https://www.namecheap.com/) or any other domain name registrar and purchase one. Let's assume you purchase `myfirstwebsite.com`. At the time of writing this costs a few thousand in fiat currency so you may want to purchase one a little cheaper!  

Then you can link your `https://username.github.io` site to your newly purchased website domain. You need to create a CNAME record for your domain by following these instructions on the [Namecheap site](https://www.namecheap.com/support/knowledgebase/article.aspx/9646/2237/how-to-create-a-cname-record-for-your-domain/) and these instructions on [GitHub](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site). The Host of your CNAME Record that you enter into Namecheap  will be `www` and the CNAME Value will be `username.github.io`. Save all changes by pressing the green tick on Namechea. You will have to wait up to 30 minutes for the host records to be accepted. Make sure you tick the `Enforce HTTPS` box on the GitHub setup page so that browsers later recognize it as a secure website with a HTTPS certificate. 

After 30 minutes you can confirm your DNS record configured correctly from the command line by using the `dig` command (of course replacing `www.myfirstwebsite.com` with your purchased website domain).

`dig www.myfirstwebsite.com +nostats +nocomments +nocmd`

You should be able to see that `www.myfirstwebsite.com` now has a CNAME record of `username.github.io`. And if you enter `www.myfirstwebsite.com` into a web browser (e.g. Safari, Chrome, Firefox etc) you should be able to now see your `Hello World!` and whatever else you added to your site.


  
