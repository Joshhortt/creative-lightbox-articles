---
title: "How Next.js 13's CSS modules & Loading State Feature Can Improve User Experience"
seoDescription: "Discover how CSS modules & loading state feature can enhance the UX of your website. Reduce load times create a smooth, polished user interface in Nextjs 13"
datePublished: Wed Apr 26 2023 13:24:47 GMT+0000 (Coordinated Universal Time)
cuid: clgxqa2ps000309m7d1d93e5l
slug: how-nextjs-13s-css-modules-loading-state-feature-can-improve-user-experience
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1682501049286/d46dcafa-436d-46ec-8e64-33cd67fc9b79.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1682515265839/10a4952e-f6cd-48e7-8fde-2df3c269ee35.png
tags: client-side-rendering, css-modules, server-side-rendering, nextjs, react-suspense

---

In this series, we’re continuing through the basics of learning the new features of the static site generator, [Next.js 13](https://nextjs.org/).

## Introduction

In the previous tutorials, we learned how we can construct pages and layouts in the new [Next.js 13](https://nextjs.org/) **app directory**, and we'll also looked at some basic **routing** and **Linking**.

Today we'll dig deeper and look at how CSS modules is applied with this starter project we've been using. We also have a quick look at Loading state using [Next.js 13](https://nextjs.org/).

![0](https://cdn.hashnode.com/res/hashnode/image/upload/v1680598308584/cc7b01eb-0670-4fda-be32-3f6e269d82af.png align="center")

### Prerequisites

If you intend to follow along with this tutorial on your system, please ensure you have the following:

* A basic understanding of working with the terminal.
    
* A Laptop or PC with Windows installed
    
* An Internet connection
    
* [Git](https://git-scm.com/) is installed on your local machine (optional). For more details on accomplishing this, review [Installing & Setting Up Git on Windows](https://creativelightbox.net/how-to-install-git-bash-for-windows-to-your-local-system).
    
* A [GitHub](https://github.com/) account. For more details on accomplishing this, review [How to get started with Git and GitHub](https://creativelightbox.net/how-to-get-started-with-git-and-github)
    
* The latest version of [Visual Studio Code](https://code.visualstudio.com/) is installed on your machine.
    
* Basic knowledge of [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML), [CSS](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/CSS_basics), [JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript), and [React](https://react.dev/).
    

> **Note:** This is a follow-up tutorial, it does require you to have created the second tutorial where we covered **Routing, Layouts & Links**, as covered in the article : [Take Your Next.js 13 App to the Next Level with New Routing Enhancements, Dynamic Layouts, and Efficient Links](https://creativelightbox.net/take-your-nextjs-13-app-to-the-next-level-with-new-routing-enhancements-dynamic-layouts-and-efficient-links) to make the most of it.

**Let’s get started!**

## Creating a Starter Project

You can see we've got [Visual Studio Code](https://code.visualstudio.com/) open, where our completed code for the previous part **nextjs-two** of this beginner series is, which is essentially the modified starter project we've been doing for the last two tutorials.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1682501147662/5d9ce3f8-bb38-430b-9d86-76c5409dd981.png align="left")

Let's get started by making a copy of **nextjs-two** and renaming the file to **nextjs-three** inside our **nextjs-series** directory.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1682501252656/2b39a791-82b9-4bb0-8d6b-9a1b80ead066.png align="left")

I'm going to open up this **nextjs-three** directory with [Visual Studio Code](https://code.visualstudio.com/) and we can see everything that was installed from **nextjs-two** is over here in the file tree, but we need to change some of the contents of the `package.json` file,

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1682501273244/4e1dab11-573c-4808-896b-3495cd429b05.png align="left")

and the `packages.lock.json` file as well.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1682501288271/543cc60c-2dfd-4784-8b9f-ed5dc3657a49.png align="left")

---

## Accessing the Development Site

So let's go ahead and open a terminal window once again, and I'm going to type in the following:

```bash
npm run dev
```

This will start our basic application. We can see it starting up, and we see all of this information here in the terminal, but here is the URL we can press **control** and then just **mouse click** to follow that click and **Voilá!** it's going to launch that in Chrome.

```bash
ready - started server on 0.0.0.0: 3000, url: http://localhost:3000
```

Once the development server is running, you will be able to browse to http://localhost:3000.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1682501311164/0899edb1-01ee-44c1-9c90-3bb66d2e5a53.png align="left")

Here is our page, visible in the browser.

![6](https://cdn.hashnode.com/res/hashnode/image/upload/v1680599225416/314bf70c-84bd-4767-9230-9774ce8c91c9.png align="left")

We have the full page that has started, and this was that `page.tsx` that we saw inside of the **app directory** —Now as cool as this looks, let's go ahead and make some more changes.

Let's just delete what's inside the `<main>` element down here:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1682501348777/e8aad4d9-9dce-4451-bda2-5b73f17fd83a.png align="left")

And replace that with the following:

```javascript
      <h1>Hello Welcome to Next.js 13</h1>
      <Link href="/about">Go to About Page</Link>
```

The page we just edited, `page.tsx` of the **app** directory will look like this:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1682501420759/23a06186-741d-459f-be35-ccda400ae1ce.png align="left")

If we can look at the application running on `http://localhost:3000` we can see that now we have a different **Homepage**:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1682512982254/67948aa6-3cf5-4a92-8da5-2dd1195892c7.png align="center")

> **Note:** Just underneath the **Hello Welcome to Next.js 13** -our link that says: **Go to About Page** is at the right, but we can go ahead and click that, then it takes us to the **about page** that has the site **Navbar,** it has the **About NavBar** it still has the **h1** that says **About** and **Link to Home page** so we can go back and forth now with links rather than using our back and forward buttons from the browser Tab.

---

## CSS modules

CSS modules in Next.js 13 allows developers to write modular and scoped CSS by automatically generating unique class names and localizing CSS styles. It enables developers to define CSS classes in a single file and import them into the components where they are needed. This way, the CSS styles are scoped to the components, eliminating global styles and reducing the risk of style conflicts. Additionally, Next.js 13 now supports CSS modules for both client-side and server-side rendering, providing a consistent UI experience throughout the application.

So continuing with our follow-up tutorial, I previously mentioned that CSS is the reason this **about link** is down there.

Let's change that and briefly look at how some CSS is currently applied in this modified starter project.

Right now this **class**`{styles.main}` that we see in `page.tsx` of the **app** directory is applying that beginning CSS.

We can go ahead and remove that without removing the `<main>` element of course.

```javascript
<main className={styles.main}>
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1682501535302/6485c590-2e99-40ee-9f78-4ee3b5126c04.png align="left")

After we save, that's definitely going to change what is applied in the home page but we can see what that starter project did and that is: `import styles from "./page.module.css"` so it made some Styles inside of this module -some CSS Styles specifically for this page.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1682501720703/fee980b5-9c56-4d10-be09-0ed723ac19d9.png align="left")

And then there are also the file `globals.css` that's applied to the entire site.

We could also create some styles that are applied just to the layout for a specific level or path in the directory tree like our about path.

Continuing with the **about directory**, let's create a new file called: `styles.module.css` -we're creating a CSS module.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1682501794547/0527e9bb-32a5-4950-8f7e-1ecb78873d9c.png align="left")

We're going to create a class called `.main` , and then inside of this main class we'll have the following styles:

```javascript
.main {
    min-height: 100vh;
    display: grid;
    place-content: center;
    background-color: #333;
}
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1682501887460/1eec4b1d-b9a7-4b69-85cb-b7a574219fab.png align="left")

Let's apply this to the `layout.tsx` inside the **about directory**.

So any page, any component in the about path, what I mean is the **about page** but also any **children** would receive these Styles and to do this, we need to import Styles at the top.

```javascript
import styles from "./styles.module.css";
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1682501962730/8f6a5a07-4d93-4401-936c-9f45dfa57c3f.png align="left")

And then after we've imported those we just need to apply those, and we can do that with this `<main>` element:

```javascript
<main className={styles.main}>
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1682501990961/d22ade21-2ae2-4f74-b266-6d8b743efa9f.png align="left")

The nice thing about these modules is you could have a main class with the same name inside of the `page.module.css` and then have essentially the same name at two levels, but they're not applied the same way because they're just applied to the component in that class, however, you would have to be careful if you were using globals and applied those.

Remember we removed the `<main>` element with a `className` just previously from the file `page.tsx` of the **app** directory.

Let's put it back again:

```javascript
<main className={styles.main}>
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1682502426796/c27da1c6-65d3-45cf-b0da-44d416d97ff6.png align="left")

Let's go ahead and see what was applied on our home page:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1682502581809/983a3647-53ef-4237-9e47-202738da32f0.png align="left")

We can see that we have applied our `<main>` element with a **class** that is entirely different as it was before.

Now after we click on **Go to About Page** it shows a darker color, it's centered, our header and our link are together unlike the other main class that was applied to the parent.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1682502630843/1f678cca-4a64-48b8-8302-a25dd87f5976.png align="left")

We can see how the module CSS works and applies only to that level or that page, so this is at the page level when we have `page.module.css` we import that and apply it just to that page, now we did this differently for the about -we applied it to the `layout.tsx`

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1682502862646/84d10f49-0467-40fe-8a51-bd7d8ce075cc.png align="left")

This would apply essentially to all `{children}`, because the children are nested inside of this `<main>` element that got the class.

Just so you understand the different levels we're talking about **page level** or we're talking about **layout path level** or of course, you go to the very top and you have also the **global level** that applies to all.

When we go back to the home page, the `app.tsx` and remove that **main class** -we can see the difference as well, now everything shifts to the top because those styles are no longer applied to our parent page.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1682502961404/0c351ec3-9628-41ec-a759-3fbf73f8be75.png align="left")

## Loading with React

A `loading.js` or `loading.tsx` file is a JavaScript file that is used to create **instant loading states** for web applications, built on top of the **React library's suspense** feature. The suspense feature in React allows developers to define components that can delay rendering until some data or resource is ready, which can help improve the user experience by showing loading indicators or placeholders while data is being fetched.

The `loading.tsx` file typically includes helper functions or components that can be easily used to create loading states for different parts of a web application. For example, it might include a component that shows a spinner animation while data is being fetched from a server, or a function that can be called to delay rendering a component until its data is ready.

By using the `loading.tsx` file, developers can easily implement efficient and user-friendly loading states in their web applications, without having to manually write complex code to manage asynchronous data fetching and rendering.

Now let's move on with **Loading**. We can add more files here that some you don't even see that weren't provided with the starter project but they can really help the project out and one of those is a **loading state**, so once again in the **about directory** let's create a new file and we just name it: `loading.tsx`.

Inside of this `loading.tsx` we'll type RFC and get our loading functional component. Once again make that a capital **L** for the name of the component and then we are returning a loading state, instead of what is currently being returned we're going to put a `<h1>` inside of this we just type the word **Loading with some dots**.

```javascript
export default function Loading() {
  return <h1>Loading...</h1>;
}
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1682503327622/f6597084-ff04-4248-af6c-ba21d57a753e.png align="center")

Another great thing is the [loading file can create instant loading states built on Suspense](https://beta.nextjs.org/docs/api-reference/file-conventions/loading), under the hood.

We will be able to briefly see this loading message when we navigate between those two pages.

First to see this in action we'll open up our **Dev tools** -when we are on the Home page, we just right click with our mouse and choose **,**.

Next under the **Network Tab** we have a option that says **Slow 3G**. We select that option to see the Loading state just changing more slowly.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1682582861082/xurDyI3rr.png?auto=format align="left")

Finally, we **minimize** the **Dev tools** then we'll go to the home page first and remember the home page doesn't have a loading state -go to the **about page** to see the loading message we did just briefly.

Click on **Go to About Page** and see it in action.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1682503043690/30b2caa8-57b3-4736-8574-930a957b88fd.png align="left")

## Conclusion

In this article, we learned how to use the CSS modules. We also saw how to apply react suspense and loading states.

The patterns and conventions we learned in this article are still experimental features that [Next.js 13](https://nextjs.org/) is implementing while moving forward, however, they are already very useful, and we can already start using them in our projects.

[Next.js 13](https://nextjs.org/) is constantly incrementing these new features and adding some new ones, so I'll try to cover those if they continue during this beginner series; however, I prefer to publish the new features rather than the previous ones, because this is the direction that [Next.js 13](https://nextjs.org/) is headed in the future.

## What's next?

During our upcoming part 4, we will delve into the topic of Error Boundaries. It is important to prioritize progress rather than perfection, as even small advancements made each day can lead to significant results.

**Thanks for the read! Now go practice & build something awesome!**