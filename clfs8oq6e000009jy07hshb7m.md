---
title: "Getting Started with Next.js: A Comprehensive Guide to Building Your First Application"
seoDescription: "Learn how to get Next.js 13 set up and installed for the rest of the Beginner tutorial series."
datePublished: Tue Mar 28 2023 12:33:44 GMT+0000 (Coordinated Universal Time)
cuid: clfs8oq6e000009jy07hshb7m
slug: getting-started-with-nextjs-a-comprehensive-guide-to-building-your-first-application
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1680001023828/ae75f093-be47-4519-81fc-2a04fed5b4f4.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1680006686522/71703e79-032a-435d-af57-d8795bb0a275.png
tags: cdn, server-side-rendering, nextjs, static-site-generation, hot-module-replacement

---

In this series, we’re going through the basics of learning the static site generator, [Next.js](https://nextjs.org/).

## Getting Set Up in Next.js

We’ll go through installing Next.js 13, create a few pages, and a blog, and finally take a look at the data files. Everything we do will be built from scratch, so, no previous Next.js knowledge is necessary only the basics of HTML, CSS, JavaScript, and React. By the end of this series, we’ll have the skills and knowledge to build our own Next.js projects from scratch.

### Prerequisites

If you intend to follow along with this tutorial on your system, please ensure you have the following:

* A basic understanding of working with the terminal.
    
* A Laptop or PC with Windows installed
    
* An Internet connection
    
* [Git](https://git-scm.com/) is installed on your local machine (optional). For more details on accomplishing this, review [Installing & Setting Up Git on Windows](https://creativelightbox.net/how-to-install-git-bash-for-windows-to-your-local-system).
    
* A [GitHub](https://github.com/) account. For more details on accomplishing this, review [How to get started with Git and GitHub](https://creativelightbox.net/how-to-get-started-with-git-and-github)
    
* The latest version of [Visual Studio Code](https://code.visualstudio.com/) is installed on your machine.
    
* Basic knowledge of [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML), [CSS](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/CSS_basics), [JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript), and [React](https://react.dev/).
    

**Let’s get started!**

## Why use Next.js?

Next.js is a popular open-source framework for building server-side rendered react applications. It offers a range of benefits that can make developments faster, more efficient, and more scalable.

### Some key benefits of using Next.js are:

**1 - Easy setup:** Next.js provides a simple and easy setup process, with many features pre-configured for a variety of use cases.

**2 - Wide community:** Next.js has a large and active developer community, with many resources available for learning and troubleshooting.

**3 - Server-Side Rendering:** Next.js provides server-side rendering (SSR) out of the box, allowing for faster page loads and better search engine optimization (SEO). SSR also provides better accessibility for users with slower internet connections or limited device capabilities.

**4 - Automatic Code Splitting:** Next.js automatically code-splits pages, optimizing them for performance and minimizing the amount of JavaScript required to load each page.

**5 - Built-in API Routes:** Next.js includes API routes, allowing developers to easily create and manage server-side APIs without additional configuration.

**6 - SEO optimization:** With its server-side rendering capabilities, Next.js can improve SEO rankings and visibility.

**7 - Static site generation:** Next.js has a built-in static site generation feature, so we can generate static files that can be served from a CDN for faster loading times and improved SEO.

**8 - Greater developer experience:** Next.js has excellent developer experience, with features for hot reloading and building, debugging, and testing.

**9 - TypeScript Support:** Next.js has excellent TypeScript support, making it easier for developers to write safe and maintainable code.

**10 - Extensible:** Next.js provides a robust API that allows developers to extend its functionality, making it a versatile option for a wide range of projects.

**11 - Hot Module Replacement (HMR):** Next.js allows for HMR, which speeds up development time by allowing us to see code changes immediately without having to refresh the page.

**12 - Automatic code splitting:** By default, Next.js automatically splits up code chunks and only sends the code the user needs, which can improve website loading time.

**14 - Automatic Image Optimization:** Next.js optimizes images automatically to improve page performance and reduce load times.

**15 - Customizable Server APIs:** Next.js provides options to customize server-side APIs, which can be used to build more complex applications.

**Overall** Next.js can help improve website performance, streamline development, and offer a better experience for both developers and end users.

![1](https://cdn.hashnode.com/res/hashnode/image/upload/v1680001411505/d8b2fb75-121f-45ec-8e3b-ffcd1f8e63cd.png align="center")

### What is Pre-Rendering?

By default, Next.js pre-renders every page. This means that Next.js generates HTML for each page in advance, instead of having it all done by client-side JavaScript, which is what React does.

React sends down this huge bundle of JavaScript, and then everything is rendered in the client, which is the browser. That's on the client side. Pre-rendering can result in better performance and SEO.

Each generated HTML page is associated with minimal JavaScript code (instead of a large bundle) code necessary for that page.

**Hydration** is the name given to the process in JavaScript frameworks to initialize the page in the browser after it has previously been server-rendered. While the server can produce the initial HTML we need to augment this output with event handlers and initialize our application state in a way that it can be interactive in the browser.

### What is Static Site Generation (SSG)?

Next.js has two forms of pre-rendering: **Static Generation** and **Server-side Rendering**. The difference is in when it generates the HTML for a page.

* **Static Generation:** The HTML is generated at build time and will be reused on each request, this is what's recommended it's the most efficient it's built on the server and then it can be sent out and we're going to talk about CDN’s as well which is a Content Delivery Network and that's where the static generation becomes very useful.
    

### What is Server side-rendering

* **Server-side Rendering**: The HTML is generated on each request. Server-side rendering is also very useful but it's not as recommended as the static site generation, here the HTML is generated on each request it's still generated from the server not on the client side however both of these can be combined with client-side data fetching as well which lets us create a Hybrid Next.js app and we can kind of have the best of both worlds when that happens.
    

> So why is this static generation so important? Let's look at what a CDN is.

### What is a Content Delivery Network (CDN)?

A content delivery network (CDN) is a geographically distributed group of servers that caches content close to end users. A CDN allows the quick transfer of assets needed for loading Internet content, including HTML pages, JavaScript files, stylesheets, images, and videos.

### How does a Content Delivery Network (CDN) work?

![2](https://cdn.hashnode.com/res/hashnode/image/upload/v1680001470568/8a9727f8-3cde-4dc6-af15-2cd7ddc41194.png align="center")

Now on [Cloudflare](https://www.cloudflare.com/learning/cdn/what-is-a-cdn/) how does a CDN work?

Again a Content delivery network is a network of servers linked together to deliver content as quickly cheaply reliably and securely as possible to improve speed and connectivity a CDN will place servers at exchange points between different networks so if we have generated our site statically our site can be cached at these different servers and ready to serve faster.

![3](https://cdn.hashnode.com/res/hashnode/image/upload/v1679594225564/9z8mnDxHo.png?auto=compress align="left")

If we have a look at this map which tells us what's happening here, we have this **origin server** right there in **orange** color, but there are all of these **CDN servers** that is **blue** that we see there and the user just has to go to this CDN server. So if we've cached our site out at these other servers they don't have to go all the way here and get more performance, essentially faster load times.

Now that we've completed a quick discussion of the benefits of Next.js and really what separates it from a traditional React application because this React framework has many benefits for us.

### Looking at Next.js 13 Documentation

If we look at the documentation, we can see it has a link that says: [see the new beta docs](https://beta.nextjs.org/docs). Now, this is an important note because Next.js 13 was recently released and there are some major changes, so any previous Next.js tutorials before Next.js 13 have changed things quite a bit, I must say.

![4](https://cdn.hashnode.com/res/hashnode/image/upload/v1680002375941/BGqF3fL7l.png?auto=compress align="left")

One thing I like about **Beta Docs** is their dark mode.

![5](https://cdn.hashnode.com/res/hashnode/image/upload/v1680001693667/sAuEBxQWq.png?auto=compress align="left")

## Installing Node

The first thing that we need to have is [node.js](https://nodejs.org/en), and it's not that we have to know node.js already, but we do need it installed on our system. We can see that it says node.js 16.8 or later.

![6](https://cdn.hashnode.com/res/hashnode/image/upload/v1680002417894/t8Iq9ErLF.png?auto=compress align="left")

When we visit the [node.js](https://nodejs.org/en) website, currently they're on **version 18.14.0 LTS**, which means for long-term support, so we could download and install that if we don't have it already because we're going to need at least **node.js version 16.8 or later** like we saw on the [Next.js Beta Docs Page](https://beta.nextjs.org/docs), we can see there is **support for Mac OS Windows and Linux** as well, so we should be fine there. Just make sure we have node.js up to date.

## Creating a Next.js 13 project

![7](https://cdn.hashnode.com/res/hashnode/image/upload/v1680002457891/kF30RfBKz.png?auto=compress align="left")

If we scroll down to the **Beta Docs** page on the Installation tab, we see **Automatic Installation**. It has the `--experimental-app` at the end, but that's just because we're still in **beta** and the app directory and everything new about it is still considered experimental, however, they are moving forward with that, which is why we want to go ahead and copy this `npx create-next-app@latest --experimental-app`.

Click the following clipboard icon (or copy that with Ctrl C) to copy the code:

```javascript
npx create-next-app@latest --experimental-app
```

**1 -** Let's open the terminal in our IDE environment (Visual Studio Code) by using the menu in the editor: Terminal &gt; New Terminal.

**2 -** I'm going to open a project directory, for **nextjs-series** in the terminal window.

![8](https://cdn.hashnode.com/res/hashnode/image/upload/v1680002510650/97Bi_EwHS.png?auto=compress align="left")

I'm going to just **PASTE** that code we copied before in.

```bash
npx create-next-app@latest --experimental-app
```

**3 -** Now press **ENTER** and this will install Next.js, but it's going to ask us a few questions, that we have to answer.

**4 -** First, I'm just going to refer to this **nextjs-one** as the tutorial lesson for our Next.js series.

**5 -** After that, it asks if we would like to use typescript, and we choose —**YES** (in the beta docs even the examples are in typescript) - just press —**ENTER**.

**6 -** The next question is about **ESLint** I'll go ahead and say —**YES** for that also.

**7 -** Another question is, if we would like to use the source directory —**No I don't**, because I want to use the new **app directory** we'll just say —**NO** to the question.

**8 -** The last question is about the import Alias we would like to configure. We just keep it that way, then we just going to press —**ENTER** and go with the **DEFAULT**.

**9 -** Now it's going to install the application.

![9](https://cdn.hashnode.com/res/hashnode/image/upload/v1680002555875/O4TisV2Ik.png?auto=compress align="left")

Here is what these steps would look like:

* Ok to proceed? (y) YES
    

> **Note:** We could probably just do the **y** or **Yes** it works as well.

* What is your project named? ... nextjs-one
    
* Would you like to use TypeScript with this project? ... No / **YES**
    
* Would you like to use ESLint with this project? ... No / **YES**
    
* Would you like to use `src/` directory with this project? ... **NO** / Yes
    
* What import alias would you like configured? ... @/\* ...Just hit **ENTER**
    
* Installation starts...
    

![10](https://cdn.hashnode.com/res/hashnode/image/upload/v1680002629410/wAWFPSjk-.png?auto=compress align="left")

**10 -** I'm going to drag this over so we have Visual Studio code in the full screen and go ahead and show that file tree once again because we'll want to look at all of the new files that we get, and now that we've created our application and we have the directory here, what I want to do is change directory `cd` into this here, but I'm just going to close this terminal.

![11](https://cdn.hashnode.com/res/hashnode/image/upload/v1680002655703/2j-lZdsPu.png?auto=compress align="left")

**11 -** I'm going to go to the file menu, and I'm going to open that folder, which would be **Ctrl + K + Ctrl + O**.

![12](https://cdn.hashnode.com/res/hashnode/image/upload/v1680002676755/dhn-I_5P0f.png?auto=compress align="left")

**12 -** I'm going to open up this **nextjs-series** and there's our **nextjs-one**, we open that, and now we can see everything that was installed over here in the file tree.

![13](https://cdn.hashnode.com/res/hashnode/image/upload/v1680002912367/Mw_27-gJL.png?auto=compress align="left")

### Looking at Files and Folders

Let's quickly discuss what files and folders we have here.

There is a `README.md` file, a file with just some directions, like `npm run dev` to go ahead and start our application, it's going to be on [http://localhost:3000](http://localhost:3000) and you have more directions below as well.

![14](https://cdn.hashnode.com/res/hashnode/image/upload/v1680002957881/hhyItnzMH.png?auto=compress align="left")

We have a `package.json` file —notice we have some scripts. We're interested mostly in the `"dev": "next dev",` script, so we would type `npm run dev` when we want to start our development environment. The `"build": "next build"` and `"start": "next start"` scripts, are things that would be done on the server. There's also something for `"lint": "next lint"` as well, so we're only going to be using `"dev": "next dev"` for the purpose of this tutorial.

![15](https://cdn.hashnode.com/res/hashnode/image/upload/v1680002977295/XOCpwy2N3.png?auto=compress align="left")

We can see the **dependencies** that were automatically added for us here, such as `"typescript": "5.0.2"` and `"next": "13.2.4"` and `eslint": "8.36.0"` and other dependencies:

```json
 "dependencies": {
    "@types/node": "18.15.7",
    "@types/react": "18.0.29",
    "@types/react-dom": "18.0.11",
    "eslint": "8.36.0",
    "eslint-config-next": "13.2.4",
    "next": "13.2.4",
    "react": "18.2.0",
    "react-dom": "18.2.0",
    "typescript": "5.0.2"
 }
```

Let's see another file: the `package-lock.json` —that's something we have probably seen before in other React projects as well.

![16](https://cdn.hashnode.com/res/hashnode/image/upload/v1680003068576/kJrnbLDlS.png?auto=compress align="left")

Then there is a `next.config` file —I'll explain more about the file later on.

![17](https://cdn.hashnode.com/res/hashnode/image/upload/v1680003092149/E23FBaF1x.png?auto=compress align="left")

There is also a `.eslintrc.json` —a config file for a tool named ESLINT. ESLint is a tool for identifying and reporting on patterns found in [ECMAScript/JavaScript](https://tc39.es/ecma262/) code, with the goal of making code more consistent and avoiding bugs.

![18](https://cdn.hashnode.com/res/hashnode/image/upload/v1680003124926/-OdlJvd5L.png?auto=compress align="left")

There's the `tsconfig.json` —that's something we have probably seen before if we've used [typescript](https://www.typescriptlang.org/) so really nothing new there.

![19](https://cdn.hashnode.com/res/hashnode/image/upload/v1680003154816/_sUwnWMbw.png?auto=compress align="left")

We also have the `.gitignore` file, and that's, of course, related to [Git](https://git-scm.com/) and any file that we want to ignore when pushing to [Github](https://github.com/) or any other version control option.

![20](https://cdn.hashnode.com/res/hashnode/image/upload/v1680003197851/Uv4bkqLci.png?auto=compress align="left")

Finally, there's a **grayed out** file: `next.env.t.ts` and that's a file that we should not change, and it says:

```html
// NOTE: This file should not be edited
// see https://nextjs.org/docs/basic-features/typescript for more information.
```

![21](https://cdn.hashnode.com/res/hashnode/image/upload/v1680003219584/-43CYu7CE.png?auto=compress align="left")

> **Note**: This file should not be edited, we'll just leave it like that.

Let's talk about the **public** directory —this is where some images, some **svgs**, and an **icon** file are. This is where we would put any static resources that we would want, and images are a good example of that.

![22](https://cdn.hashnode.com/res/hashnode/image/upload/v1680003986383/c-5ePDM-u.png?auto=compress align="left")

Then we have the **node\_modules** folder, which we should be familiar with.

We can think of the node\_modules folder as a cache for the external modules that our project depends on. When we `npm install` them, they are downloaded from the web and copied into the node\_modules folder, and **Node.js** is trained to look for them there when we import them (without a specific path).

Because the node\_modules folder can always be completely recreated from scratch by simply reinstalling all the dependent modules, I refer to it as a cache. (That should be listed in our project folders.)

> **Important Note:** The `node_modules` folder contains generated code. This is not code we've written, and we should never make any updates to the files inside `node_modules` because there's a pretty good chance they'll get overwritten the next time we install some modules.

![23](https://cdn.hashnode.com/res/hashnode/image/upload/v1680004016456/nR6p3ppLn.png?auto=compress align="left")

Then the new **app** directory appears, and this is where we see our basic pages.

![24](https://cdn.hashnode.com/res/hashnode/image/upload/v1680004043929/MHSN6PKeo.png?auto=compress align="left")

Here is where we have the basic `page.tsx` not an `index.tsx` and that's what we're using here for **typescript 'tsx' files** —Like I said this is the basic `page.tsx` that we'll see once we start our application.

![25](https://cdn.hashnode.com/res/hashnode/image/upload/v1680004074868/TQq5oMy5h.png?auto=compress align="left")

Then there are some styling files, like here in a module `page.module.css`.

![26](https://cdn.hashnode.com/res/hashnode/image/upload/v1680004097890/123T4TXDG.png?auto=compress align="left")

There are also some styles in the file `globals.css` that we have right here:

![27](https://cdn.hashnode.com/res/hashnode/image/upload/v1680004121635/ssNlSyoYT.png?auto=compress align="left")

There is also a `layout.tsx`

![28](https://cdn.hashnode.com/res/hashnode/image/upload/v1680004154664/b3wItRMhQ.png?auto=compress align="left")

> **Important Note**: **Next.js** supports routing. With the **react-app** maybe we've used **react-router** before; we won't have to do that with **Next.js**, it's already built-in.

## Accessing the Development Site

So let's go ahead and open a terminal window once again, and I'm going to type in the following:

```bash
npm run dev
```

This will start our basic application. We can see it starting up and we see all of this information here in the terminal but here is the URL we can press **control** and then just **mouse click** to follow that click and it's going to launch that in Chrome.

```bash
ready - started server on 0.0.0.0: 3000, url: http://localhost:3000
```

Once the development server is running, you will be able to browse to http://localhost:3000. or maybe http://localhost:3333.

![29](https://cdn.hashnode.com/res/hashnode/image/upload/v1680004175215/RZPEgkI2B.png?auto=compress align="left")

Here is our basic page, visible in the browser.

![30](https://cdn.hashnode.com/res/hashnode/image/upload/v1680004196363/UiGiQ8WeS.png?auto=compress align="left")

We have the full page that has started, and this was that `page.tsx` that we saw inside of the **app directory** —Now as cool as this looks, let's go ahead and make some changes.

Let's just copy one of these headers down here:

```html
<h2 className={inter.className}>
  Docs <span>-&gt;</span>
</h2>
```

Then remove `Docs <span>-&gt;</span>` because we won't need this arrow.

Paste this code twice somewhere in Line 34 and Line 36:

```html
<h1 className={inter.className}>Hello</h1>

<h2 className={inter.className}>Welcome to...</h2>
```

![31](https://cdn.hashnode.com/res/hashnode/image/upload/v1680004227714/ARFKiHwxb.png?auto=compress align="left")

When we save this file, we should see that our development environment reloads the page quickly. Everything updates immediately, and now we have our **Hello!** and **Welcome to...** Next.js 13 page instead of what we previously had, and it happens that fast.

![32](https://cdn.hashnode.com/res/hashnode/image/upload/v1680004249086/58Vu7PUfB.png?auto=compress align="left")

## Conclusion

We've learned more about what Next.js is and why companies are using it and we've learned how to start the basic Next.js development environment and get our first app going.

## What's next?

In our next lesson, we’ll create our first page and set up a layout.

Remember to keep striving for progress over perfection, and a little progress every day will go a very long way.