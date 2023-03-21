---
title: "How to deploy Jamstack sites to cloudcannon?"
seoDescription: "This hands-on lab will walk through the steps required to get your Next.js site built, and deployed on CloudCannon."
datePublished: Sat Mar 04 2023 15:07:53 GMT+0000 (Coordinated Universal Time)
cuid: cleu3midd00040alae17n5m6c
slug: how-to-deploy-jamstack-sites-to-cloudcannon
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1677938294912/133f4bef-67ec-4b2b-8848-6534c6f8d84a.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1677942312945/a7df07f5-a56b-4106-b481-f2238a058483.png
tags: github, nextjs, jamstack, cloud-hosting, cloudcannon

---

## Intro

We're going to learn how we can easily deploy a Jamstack app and manage git-based Markdown content with cloudcannon. Cloudcannon gives you and your team awesome collaborative features with a great UX developer experience that generally allows you to deploy sites that are going to be performant for your user experience. If you want to learn more about all the awesome features cloudcannon provides on top of what we're going to work through, make sure you head over to [cloudcannon](https://cloudcannon.com/) where you can sign up for your account for a free trial...

## Hands-on Lab:

**Effort** : 30 mins

### Objectives

After completing this reading, you will be able to:

1. Clone project files from a remote repository using the command line.
    
2. Install Dependencies.
    
3. Create a new Repository on Github.
    
4. Signup for Cloudcannon.
    
5. Add a new site synced to a remote repository on Github.
    
6. Commit and push changes to a remote repository.
    
7. Deploy new site to cloudcannon.
    

### Prerequisites

If you intend to run this lab on your system, please ensure you have the following:

* A basic understanding of working with the terminal.
    
* A Laptop or PC with Windows installed
    
* A Internet connection
    
* [Git](https://git-scm.com/) installed on your local machine. For more details on accomplishing this, review [Installing & Setting Up Git on Windows](https://creativelightbox.net/how-to-get-started-with-branches-using-git-commands-on-a-local-repository#heading-installing-git-on-windows).
    
* A [GitHub](https://github.com/) account.
    
* The latest version of [Visual Studio Code](https://code.visualstudio.com/) is installed on your machine.
    

## Tools & Frameworks

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677938516632/6113ff81-ffef-4d76-9596-45c9f9744c79.png align="center")

If you're not familiar with the [Jamstack](https://creativelightbox.net/why-the-jamstack-is-the-future-of-web-development), it's traditionally based on being able to provide users static sites where that first load isn't going to have to do any kind of rendering on the server, instead, we use our static site generator or framework of choice, which pulls in all of our content at compile time, where we then can publish that site basically wherever we want, such as an awesome provider like cloudcannon.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677938633483/de466161-4ea9-4711-a930-765502149c73.png align="center")

To see how this works, we're going to use the [REACT framework](https://reactjs.org/) and [Nextjs](https://nextjs.org/) which give us a ton of features out of the box, including routing and data fetching, and it just helps us get super productive with our apps.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677938687254/bbc01479-c328-47f9-8218-312cf9fe9be9.png align="center")

Now if you're already familiar with [Nextjs](https://nextjs.org/) maybe you're wondering, doesn't it need a server? And while we do this at compile time, we can use tools like [get static props](https://nextjs.org/docs/basic-features/data-fetching/get-static-props) and then statically export our site, which we'll see how we can do that, and then deliver a pure static HTML site with all the assets included.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677938718945/3c73cc2e-fcc6-4986-b6e4-443cc7593a77.png align="center")

## Create a new app from a demo website starter

Now, particularly, we're going to use this [demo website starter](https://github.com/Joshhortt/demo-website-starter) that I put together, which is just going to give us a simple blog website out of the box with some markdown capabilities that are generating the content for the site.

If you want to follow along, you can find the link to this starter right [here](https://github.com/Joshhortt/demo-website-starter)

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677938805359/429d8f6a-af6e-4ff3-92b7-1dc2a4a082d3.png align="center")

**1 -** So to get started, I'm going to go ahead and copy the following command:

```bash
 $ git clone https://github.com/Joshhortt/demo-website-starter.git
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677938907684/518731a3-8c8c-4738-b743-4630000126e3.png align="center")

**2 -** I'm going to go ahead and paste that code into my terminal.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677938998423/f9d9ccbe-0f3d-4b85-b0fe-da7e22effc29.png align="center")

**3 -** I'm going to type `cloudcannon-app` after that URL because I want my app to have a nicer name.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677938950208/70bc348d-beae-4a3f-a981-91c44219429b.png align="left")

> It's going to clone down that project from GitHub to your chosen Local Directory

**4 -** I can now change `cd` into that directory.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677939060851/302ecdd7-4c88-4e57-bcb9-2d1dc1766593.png align="center")

I'm going to run `yarn install` or `npm install` which is going to install the dependencies.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677939081495/729c1c07-072b-47f5-b078-3848c8b9eaa7.png align="center")

**4 -** After that, I'm going to run `yarn dev` or `npm run dev` which is going to start up a local development server, which I can open up in a new tab. (url: http://localhost:3000)

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677939103761/7bf0d065-f5be-4853-8a2d-1addc3a06e6e.png align="center")

**5 -** Once it's loaded, we can see our new website, where we just have some blog posts on our main page, an about page, and a newsletter page, and it's just some sample content that we have in there to get started with our new website.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677939133536/28db6ed9-7c2b-4013-baea-5c770c9d8b99.png align="center")

Now we're not going to dig too much into the code, but if we go to pages and go to **index.js** we can see that for the most part, this looks like a pretty basic react application, but if we scroll down to the bottom, we see we have this function that we talked about earlier called `get static props` which is going to allow us to do, is get our data at compile time, meaning before we upload it and deploy it, that way we can save all that hard work for the network request for when it's getting built and we can grab all that post data and pass it in as props into our application and not make our user pay for that actual networking time but ultimately get this application up and deployed over to cloudcannon.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677939206183/d2d94421-2322-4973-98e6-a198f6370e68.png align="center")

## Set up a new site on CloudCannon

So let's see how we can do that now if this is our first time logging into cloudcannon

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677939227705/55852e35-1ed3-40b5-9042-ee723ccecbd8.png align="center")

We'll see that we're going to start on our account summary and we don't have any sites yet so we want to click **return to sites**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677939272240/d1e1e70f-96ce-4ee7-802b-04b7e6c94784.png align="center")

It is going to show us this UI

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677939371276/dabe449e-c257-49e2-9337-ce37dbe4a26d.png align="center")

Now we can hit **add your first site**

A new page opens up. We have a few options but we're going to choose to **connect our own files**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677939421003/419c7635-ecda-4205-935d-83907c777ae2.png align="center")

We can say whatever our site name is going to be. Let's call it **cloudcannon-app** or whatever you want your site to be called.

We can then choose our source, and in particular, we're going to use [github](https://github.com/) for this walkthrough.

> Note: We also have support for [gitlab](https://about.gitlab.com/) and [bitbucket](https://bitbucket.org/) or even uploading a folder from our computer if we'd like to.

* Click on **Authenticate**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677939488564/6d2318dd-29b3-48e6-b371-add46d7c30bd.png align="center")

After selecting github and authenticating, this webpage opens up for us to give cloudcannon permission to access our github repository.

* Just click **Authorize Cloudcannon**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677939518548/570b963d-2885-410a-9ee8-e1bf060e1cbd.png align="center")

Then we're going to need to select our repository, this means we're going to need to get our site up to a github before we can move forward.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677939552929/ea93e6cb-d926-4bc8-a472-ef28f57d3568.png align="center")

I'm going to go ahead and first create a new repository over on github.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677939575413/21818ff0-285a-43d7-8a8a-0014154daa13.png align="center")

I'm going to call that **cloudcannon-app** just like I did locally, and I'm also going to click **New repository**.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677939657835/1c36dcf1-3425-4162-a9dd-ebb687ee612e.png align="center")

Now we have a few instructions on how we can get our local project up and running now because of the way that NEXTjs already initialized git for us, and it already has a **main branch**

A new window will pop up with some git instructions, which we should type into our terminal.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677939740583/153a9af0-5cb8-456d-b955-688980011387.png align="center")

All we need to do is these last two steps.

```bash
$ git remote add origin https://github.com/YOUR-USER-NAME/cloudcannon-app.git
$ git push -u origin main
```

> Note: Just in case `git` wasn't initialized follow all these commands below

```bash
$ git init
$ git add .
$ git commit -m "first commit"
$ git branch -M main
$ git remote add origin https://github.com/YOUR-USER-NAME/cloudcannon-app.git
$ git push -u origin main
```

Now after we finish pushing all files to our newly created github remote repository, if I refresh the page, we can see that I have my new github repository with all those files.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677939843088/0b0638a1-510a-4b46-a2ac-b478374f9c07.png align="center")

Going back over cloudcannon, I'm going to refresh the page and then reselect my github repository file source, that way inside of this search for your repository once it collects all my repositories I can search for my **cloudcannon-app**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677939871401/62ba4dc2-999d-4efa-b412-147e39fa4dc5.png align="center")

We can see that it will pop up right here, and we can see that I have an option for either using my existing branch or creating a new branch. Now, because I only have a main branch at this point, I'm just going to use that and select **main** as that'll be the default production branch.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677939894911/b46fbad9-b438-4f8e-8b75-b529e9a5d1c8.png align="center")

Next, click **sync files** to keep moving this process forward.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677939914481/f8f01368-f395-4be9-8e67-46a68e5863ff.png align="center")

Now we can see that cloudcannon has actually detected what kind of site we have, particularly in NEXTjs, but we can also see that we have the ability to define our build options where we have our preserved paths, ours is going to be **node modules**. That makes a lot of sense. Note that we don't have any **environment variables** at this time, but if you do, this would be the place to add them.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677939937329/51c5d561-94bd-4396-9826-3104f88b80ab.png align="center")

When we go further down to our **install options**, like our **command line options**, this has `npm install` by default. Because I'm using `yarn` locally, I'm just going to go ahead and use `yarn install` but you can keep `npm install` if you decide to use `npx` and `npm` for your project, and then also for the build command: `yarn build` or leave `npm build`.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677939970587/da11faf5-3c8b-4d80-87d2-7369c31174f5.png align="center")

Now the tricky thing for the build command is that when we're using NEXTjs, we want to make sure that we're statically compiling this, and we'll see in a second that what we want to do is not only `yarn build` this, but we also want to do something called `next export` which we don't currently have an option for in our project.

So we're going to leave this as `yarn build` for now, and we're going to set the output path to `out` because that's where the folder is going to get compiled to, but then we can scroll down and we can see that we have two other options where we have to **use the beta integration version** of the cloudcannon reader, which we're going to select to check because we want cloudcannon to try to read the information of our repository, and then finally we can just leave the include get folder off as we don't need that part of our system.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677940007214/b908fe0b-b6b1-492d-a2c0-06c3f794c922.png align="center")

Finally, as I said, we can click **build site** and that's going to go through and run all the commands and try to deploy our site once cloudcannon gets through all those steps,

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677940031746/f7470550-d0b8-41fe-9628-463b8a7279c2.png align="center")

We can see that mine was deployed to the random name of **green-cassowary**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677940049310/3de89a08-a06e-4089-b560-5fc5d56d137e.png align="center")

If I open that up in a new tab we can see that it's **Page Not Found**.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677940071888/96a611d1-3a48-4709-8663-f154754d7013.png align="center")

If we click over to the status tab inside cloudcannon and I look inside, I can see all the build logs. I'm going to particularly select NEXTjs, and if I look through, it says that it cannot find that **out** directory as it doesn't exist, and that's because we're only currently building our NEXTjs site and now we also need to export it, as I said a while back.

## Statically export the NEXT.js app

Inside the project, I'm going to open up my `package.json` file, and we can see under `scripts` that we already have a few options, and particularly, we see our `build script` going on, where all it's doing is running `next build` and that's great, but we want to also export it, so I'm going to tack on two `&&` (and) signs and I'm going to add also next export right after `next build` which is going to export it to static files for us, so we can even test locally.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677940093658/dc79a68d-e510-44d2-93d1-3efb6a5e696d.png align="center")

Inside the terminal, run `yarn build` or `npm run build`, where we can already see that it ran `next build && next export` and we can see that as it goes through, it's going to first build the site, just as we'd expect, and then we can see how it's going to work when we try to export it.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677940114024/b4be030a-c32b-47b7-9458-569f70723188.png align="center")

We can see after it goes through the build process that we had a **successful export**.

And we can even look inside our project under the out directory, where we see all those HTML files, which are exactly what's going to get deployed out to cloudcannon.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677940136333/d315f3ea-6efb-421d-b9cc-2e9a7bcc1196.png align="center")

I'm going to run the following commands to commit my changes:

```bash
$ git add .
```

```bash
$ git commit -m "updating build script"
```

```bash
$ git push
```

What's going to happen is that as soon as we push that out, we can see that cloudcannon is already **building** that new site with that new commit automatically without us having to trigger a `new build`. That way, we can always make sure that we're keeping our production branch nice and up-to-date.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677940233033/127bcdfe-4d2e-46cc-a188-0028fc7e2178.png align="center")

Once it's complete, we can open up that URL again, and we can now see that our new site is deployed to cloudcannon.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677940160251/389dc6ba-56e2-4d95-8864-e93a5e2ef695.png align="center")

## Summary

Cloudcannon gives us a great way to deploy our projects to the web.

Are you a fan of the Jamstack? Let me know in the comments what's your favorite part of the building with the Jamstack is.

## **What's Next?**

If you want to follow along with more advanced stuff in the next article I'll talk about [How to Configure cloudcannon collections to enable Post & Page content editing?](https://creativelightbox.net/how-to-configure-cloudcannon-collections-to-enable-post-page-content-editing).

**Thanks for the read! Now go practice & build something awesome!**