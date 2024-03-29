## What we’ll do

In about 10 minutes, we'll set up a workflow that makes static sites dead simple.

You'll get the following:

- Free https
- Free or cheap hosting
- Build sites quickly
- Edit with live reload
- Edit when you’ve forgotten everything in 6 months

## Start: signups

We can get all this by using Netlify (really simple static hosting) along with AnyMod (100s of website sections).

- [Netlify signup](https://app.netlify.com/signup?utm_source=css-tricks&utm_campaign=sep-2019)
- [AnyMod signup](https://anymod.com/login?utm_source=css-tricks&utm_campaign=sep-19)

## Set up deploy pipeline

We’ll create a basic HTML file, track it with GitHub, and then auto-deploy with Netlify.

(If you prefer a manual setup, you can skip this step and instead deploy to Netlify by dragging/dropping into the Netlify folder.)

1. Create an empty repo in GitHub [here](https://github.com/new).

Name it `netlify-anymod`:

![GitHub setup](https://res.cloudinary.com/component/image/upload/v1567551219/permanent/css-tricks-01.png)

2. Connect Netlify to your repo [here](https://app.netlify.com/start).

![Netlify setup](https://res.cloudinary.com/component/image/upload/v1567551534/permanent/css-tricks-02.png)

3. Create a folder on your computer and add a file named index.html. You can run the following in your terminal to do this:

```
mkdir netlify-anymod
cd netlify-anymod
touch index.html
```

Now edit the index.html file to add some basic HTML structure:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <title>Netlify & AnyMod | CSS Tricks</title>
  </head>

  <body>
    Hello, World!
  </body>
</html>
```

4. Track it with git and deploy to GitHub

```
git init
git remote add origin https://github.com/tyrw/netlify-anymod.git
git add -A
git commit -m "Initial commit"
git push --set-upstream origin master
```

(Note: use your own repo URL for `git remote add origin`)

Check your Netlify URL after a minute or so, and your site should be live!

![Live site](https://res.cloudinary.com/component/image/upload/v1567575330/permanent/css-tricks-03.png.png)

## Add section "mods"

Now that we have our deploy setup, we can build the page itself. We'll do this with ready-to-use modules ("mods") on AnyMod.

There are a lot to choose from, but we'll use mods from the [Editorial theme](https://anymod.com/html-theme-templates/editorial):

#### Navigation [[link](https://anymod.com/mod/professional-side-nav-mlrnbm)]

![Navigation](https://res.cloudinary.com/component/image/upload/w_400/v1564793728/sidenav_mjin2w.gif)

#### Intro / Hero unit [[link](https://anymod.com/mod/intro-section-ormard)]

![Hero unit](https://res.cloudinary.com/component/image/upload/w_400/v1567577537/permanent/css-tricks-04.png)

#### Form [[link](https://anymod.com/mod/contact-form-ralmam)]

![Form](https://res.cloudinary.com/component/image/upload/w_400/v1567577533/permanent/css-tricks-05.png)

#### Image gallery [[link](https://anymod.com/mod/card-section-balmaa)]

![Gallery](https://res.cloudinary.com/component/image/upload/w_400/v1567577534/permanent/css-tricks-06.png)

## Clone and add mods

Add these mods by clicking "Clone" for each one and then scroll down and copy/paste the installation code into the index.html file.  Also copy and paste your project script at the top.  

Your index.html should now look something like this:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <title>Netlify & AnyMod | CSS Tricks</title>

    <!-- AnyMod -->
    <script id="AnyMod-script">
      (function (m,o,d,u,l,a,r,i,z,e) {
        u[m]={Project:o,rq:[],Opts:r,ready:function(j){u[m].rq.push(j)}};function j(s){return encodeURIComponent(btoa(s))};z=l.getElementById(m+'-'+a);r=u.location;
        e=[d+'/page/'+o+'/'+j(r.pathname)+'/'+j(r.host)+'?t='+Date.now(),d];e.map(function(w){i=l.createElement(a);i.defer=1;i.src=w;z.parentNode.insertBefore(i,z);});
      })('AnyMod','82PEPN','https://cdn.anymod.com/v2',window,document,'script',{ toolkit: true, tips: true, priority: 3 });
    </script>
    <!-- /AnyMod -->
  </head>
  <body>
    <!-- Professional side nav -->
    <div id="anymod-mlrnbm"></div>

    <!-- Intro section -->
    <div id="anymod-ormard"></div>

    <!-- Contact form -->
    <div id="anymod-ralmam"></div>

    <!-- Card section -->
    <div id="anymod-balmaa"></div>
  </body>
</html>
```

And the page is ready to go. 

Now save and push to GitHub to deploy the site:

```
git add -A
git commit -m "Added mods"
git push origin
```

Wait a minute, and your site should be ready to use. Here is the demo page: 

https://css-tricks-demo.netlify.com/

## Editing content

Now you can live edit the content and code for each mod. When viewing your own page (while also logged into AnyMod), you see a pencil on the right side:

![AnyMod pencil](https://res.cloudinary.com/component/image/upload/v1567579140/permanent/css-tricks-07.png)

Click the pencil and choose a mod. Now try making some edits to the content (or code) and notice that it updates on the page automatically in realtime.

![AnyMod live edit](https://res.cloudinary.com/component/image/upload/v1567579649/permanent/css-tricks-live-edit.gif)

You can use this method to make edits now or in 6 months when you've forgotten how the project is set up.

## Form

The form also works automatically.  Try submitting a message on your own page; the response will be emailed to you right away.

## Conclusion

You now have a great way to build fast, reliable, secure static sites. 

Remember: with great power comes great responsibility.
