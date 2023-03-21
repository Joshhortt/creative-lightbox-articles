---
title: "A Step-by-Step Guide to Installing Pre-Configured Cloudcannon Themes for Your Jamstack Project"
seoDescription: "This guide will walk through the steps required to get your Next.js pre-built Cloudcannon site ready to configure and deploy to Cloudcannon."
datePublished: Tue Mar 21 2023 09:56:43 GMT+0000 (Coordinated Universal Time)
cuid: clfi2zu2r000309jvfpm3e7rl
slug: a-step-by-step-guide-to-installing-pre-configured-cloudcannon-themes-for-your-jamstack-project
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1679392111767/8e140341-5d28-4c83-b5fa-0911e4780e62.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1679392564636/2fe26281-9147-445e-acc4-b6385c43d1bf.png
tags: templates, nextjs, static-site-generation, jamstack, cloudcannon

---

As a website developer, you are always on the lookout for ways to create beautiful, functional websites quickly and efficiently. One way to do this is by using pre-configured Cloudcannon themes.

## **Intro**

This guide will walk through the steps required to get your Next.js pre-built Cloudcannon site ready to configure and deploy to Cloudcannon.

### **Prerequisites**

If you intend to run this lab on your system, please ensure you have the following:

* A basic understanding of working with the terminal.
    
* A Laptop or PC with Windows installed
    
* A Internet connection
    
* [Git](https://git-scm.com/) installed on your local machine (optional). For more details on accomplishing this, review [Installing & Setting Up Git on Windows](https://creativelightbox.net/how-to-install-git-bash-for-windows-to-your-local-system).
    
* A [GitHub](https://github.com/) account. For more details on accomplishing this, review [How to get started with Git and GitHub](https://creativelightbox.net/how-to-get-started-with-git-and-github)
    
* The latest version of [Visual Studio Code](https://code.visualstudio.com/) is installed on your machine.
    

## **What this Guide Covers:**

* Benefits of using pre-configured Cloudcannon themes
    
* Cloning a pre-built Website Template repository from GitHub
    
* Setting up your Jamstack project using the Terminal
    
* Instructions for running the project
    
* Accessing the development site
    
* The folder structure of the template
    
* Editing the components and the overall theme
    
* Deploying the project on Cloudcannon (external resource)
    

## **Benefits of using pre-configured Cloudcannon themes**

Cloudcannon themes are pre-built [website templates](https://cloudcannon.com/templates/) that come with all the necessary files and plugins to create a complete website. This means that you don't have to start from scratch every time you create a website. Instead, you can use a pre-configured Cloudcannon theme as a starting point.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1679390315721/82b3f547-88bd-4c39-8887-20a8db1b0da4.png align="center")

**Here are some benefits of using pre-configured Cloudcannon themes:**

### **Saves Time and Effort**

One of the biggest benefits of using pre-configured Cloudcannon themes is that it saves you time and effort. With a pre-built theme, you don't have to spend hours designing and coding a website from scratch. Instead, you can simply customize the theme to suit your needs.

### **Professional Design**

Cloudcannon themes are designed by professional web designers, which means they are visually appealing and user-friendly. These themes are designed using best practices and are optimized for performance, which means your website will look great and load quickly.

### **Mobile-Friendly**

More and more people are using mobile devices to browse the internet, which means your website needs to be mobile-friendly. Cloudcannon themes are designed to be responsive, which means they will look great on any device.

### **Easy to Customize**

Another benefit of using pre-configured Cloudcannon themes is that they are easy to customize. You can customize the theme to match your branding, add your own content, and make any necessary changes.

### **Affordable**

Creating a website from scratch can be expensive, especially if you hire a web designer or developer. Using a pre-configured Cloudcannon theme is much more affordable since the cost of the theme is much lower than hiring someone to create a website from scratch.

## **The pre-built Website Template "Justice"**

The pre-built website template **Justice** provides an easy starting point for building a Law firm themed business template for Next.js. Browse through a [live demo](https://mysterious-shelter.cloudvent.net/). Increase the web presence of a law firm or business with this configurable theme. You can also check out the live demo of this template.

## **Features**

* Contact form
    
* Pre-built pages
    
* Pre-styled components
    
* Blog
    
* Post category pages
    
* Disqus comments for posts
    
* Staff and author system
    
* Configurable footer
    
* Optimised for editing in CloudCannon
    
* RSS/Atom feed
    
* SEO tags
    
* Google Analytics
    

## **Getting Started**

**Effort**: 10 mins

To create a new project, we'll use the justice-nextjs-template from Cloudcannon's Github repository.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1679390415641/7d7f4e17-4c9e-445e-a6b9-e45620066904.png align="center")

**1 -** Access Cloudcannon's justice-nextjs-template Github repository.

**2 -** Click Use this Template, then

**3 -** Click Create New Repository

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1679390449199/e5580769-07ab-4b91-9a57-cf08edf1419d.png align="center")

> A new Window will open.

**4 -** Enter a repository name. For example **law-firm**. Optionally, add a description of your repository & choose the Owner. That should be you!

Then click **Create Repository from template**.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1679390519977/8a9da47d-5e8a-46df-bb8d-e9897f5c0666.png align="center")

> This will generate a Repository on your Github account. You just become the owner of this template.

## **Clone the repository**

A clone is a local copy of a remote repository. Before you can clone the repository, you first need its HTTPS URL, which provides secure access to it.

To clone the repository, complete the following steps:

**1 -** Click the button **Code** on the repository's main page.

**2 -** Click the clipboard icon to copy the URL. Make sure the HTTPS tab is active.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1679390633573/fe8d1d86-1775-4c9a-ab1a-4f7b55e7526f.png align="center")

**3 -** Open the terminal in your IDE environment by using the menu in the editor: Terminal &gt; New Terminal.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1679390660369/cbbef7dd-99c4-4323-b0bd-1e7126b77586.png align="center")

**4 -** Head over your Projects Directory in your Terminal

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1679390677452/3e40bf85-ead3-4e15-a3fb-33d1cddbf31d.png align="center")

**5 -** Paste the following command with the HTTPS URL you copied earlier:

```bash
 git clone <your repository HTTPS URL>
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1679390722811/02b34ed2-5985-4664-a8c6-e48c2fe1cee3.png align="center")

**For example:** Click the clipboard icon to copy the code, but change the **repository User.**

```bash
 git clone https://github.com/Joshhortt/demo-website-starter.git
```

**6 -** Hit **ENTER**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1679390999646/00a6e392-ac77-43cf-a1da-5e4b3a50a950.png align="center")

**7 -** Now change `cd` into that directory and open up your project directory by typing the following commands:

```bash
cd law-firm
code .
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1679391067174/ee078af7-5507-4704-9056-b19adb9c9182.png align="center")

## **Running the Project**

Running the project in development is very straightforward. To run the project, head over to the ‘website’ folder and run the following commands:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1679391086942/f286487d-e8b0-445d-ad10-02984cba9154.png align="center")

**1 -** In your terminal, run `yarn install` or `npm install` which is going to install the dependencies.

```bash
npm install
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1679391226612/67fca594-cd3e-49de-9e37-8eaa5e96946e.png align="center")

**2 -** After that, run `yarn dev` or `npm run dev` which is going to start up a local development server, which you can open up in a new tab.

```bash
npm run dev
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1679391264174/cc86d479-c058-4d1e-878d-f3df3ccf257d.png align="center")

## **Accessing the Development Site**

Once the development server is running, you will be able to browse to [http://localhost:3000](http://localhost:3000) or maybe [http://localhost:3333](http://localhost:3333)

**1 -** Click on **Follow Link** which you can open up in a new tab. (url: [localhost:3333](http://localhost:3333)).

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1679391291897/930ed41c-560a-47ac-b4a6-778602471f37.png align="center")

**2 -** Once it's loaded, Voilá! you can see your new website, where you have a complete website with a home page, an about page, a services page, a contact page a blog page with some blog posts that you can edit and configure the way you want.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1679392034824/72902af5-8f33-470a-a26b-2ab6c0a9ad1e.png align="center")

> Now I am not going to dig too much into the code, but if you have a look at the Folder structure of this Ready Website you can see that this looks like a pretty awesome Business Website ready to use.

## **Folder Structure (Website)**

This section provides you with a better understanding of the folder structure.

```bash
law-firm
|
|-- .cloudcannon
|   |-- initial-site-settings.json
|-- components
|   |-- layouts
|   |   |-- default.jsx
|   |   |-- page.jsx
|   |   |-- post.jsx
|   |-- icon.jsx
|   |-- staff-member.jsx
|   |-- post-summary.jsx 
|   |-- post-summary-details.jsx
|-- content
|   |-- pages
|   |   |-- about.md
|   |   |-- blog.md
|   |   |-- contact-success.md
|   |   |-- contact.md
|   |   |-- index.md
|   |   |-- services.md
|   |   |-- terms.md
|   |-- posts
|   |   |-- business-mergers.md
|   |   |-- real-estate-flipping.md
|   |-- staff-members
|   |   |-- jane-doe.md
|   |   |-- john-doe.md
|   |   |-- _defaults.md  
|-- data
|   |-- company.json
|   |-- footer.json
|   |-- seo.json
|   |-- site.json
|-- lib
|   |-- data.js
|   |-- rss.js
|-- pages
|   |-- blog
|   |   |-- [slug].jsx
|   |   |-- index.jsx
|   |-- 404.jsx
|   |-- [slug].jsx
|   |-- about.jsx
|   |-- contact.jsx
|   |-- index.jsx
|   |-- _app.jsx
|   |-- _document.jsx
|-- public
|   |-- uploads
|   |   |-- building.jpg
|   |-- apple-touch-icon.png
|   |-- favicon.png
|   |-- touch-icon.png
|-- styles
|   |-- forms.scss
|   |-- _layout.scss
|   |-- _typography.scss
|   |-- cloudcannon.scss
|   |-- main.scss
|-- .eslintrc.json
|-- .gitignore
|-- LICENSE
|-- README.md
|-- _screenshot.png
|-- cloudcannon.config.cjs
|-- next-sitemap.config.js
|-- next.config.js
|-- package-lock.json
|-- package.json
|-- siteicon.png
```

## **Folders & Files**

**.cloudcannon** Initial config file

**components** This folder includes another folder called **layouts** and four files:

* layouts
    
* icon.jsx
    
* staff-member.jsx
    
* post-summary.jsx
    
* post-summary-details.jsx
    

**components/layouts** - Within layouts, are three files. Where you can update the *Call to action description, Navbar names, Footer links, Add the privacy policy link to your footer, update the posts author title* and much more..

* default.jsx
    
* page.jsx
    
* post.jsx
    

**content** - Within content, are three folders with markdown files.

* **pages**
    
* **posts**
    
* **staff-members**
    

**content/pages** - These are all the Template pages.

* [about.md](http://about.md)
    
* [blog.md](http://blog.md)
    
* [contact-success.md](http://contact-success.md)
    
* [contact.md](http://contact.md)
    
* [index.md](http://index.md)
    
* [services.md](http://services.md)
    
* [terms.md](http://terms.md)
    

**content/posts** These are the template Blog Posts.

* [business-mergers.md](http://business-mergers.md)
    
* [real-estate-flipping.md](http://real-estate-flipping.md)
    

**content/staff-members** - These are the posts authors, But you can make them your Company team members If you prefer.

* \_[defaults.md](http://defaults.md)
    
* [jane-doe.md](http://jane-doe.md)
    
* [john-doe.md](http://john-doe.md)
    

**data** - Within data, are four JSON files.

* company.json - Where the company's details are.
    
* footer.json - Where the Footers' pages links & social icons are.
    
* seo.json - Where the site and author details are.
    
* site.json - Where you can add your Google Analytics and Disqus.
    

**lib** - Within lib, are two files. Normally You don´t need to change anything on these files.

* data.js
    
* rss.js
    

**pages** Within pages, are one folder and seven files.

* **blog**
    
* 404.jsx
    
* \[slug\].jsx
    
* \_app.jsx
    
* \_document.jsx
    
* about.jsx
    
* contact.jsx
    
* index.jsx
    

**pages/blog** - Within blog, are two files.

* slug\].jsx
    
* index.jsx
    

**public** - Within public, are one folder called uploads and three PNG files.

* **uploads**
    
* apple-touch-icon.png
    
* favicon.png
    
* touch-icon.png
    

**public/uploads**

* building.jpg - This is the Home page Banner Image.
    

**styles** - Within styles, are five SCSS files.

* forms.scss
    
* \_layout.scss
    
* \_typography.scss
    
* cloudcannon.scss
    
* main.scss
    

**root directory** - The other project file are:

* .eslintrc.json
    
* .gitignore
    
* LICENSE
    
* [README.md](http://README.md)
    
* \_screenshot.png
    
* cloudcannon.config.cjs - **Important** [Global configuration file](https://cloudcannon.com/documentation/articles/setting-global-configuration/)
    
* next-sitemap.config.js
    
* next.config.js
    
* package-lock.json
    
* package.json
    
* siteicon.png
    

## **Initial Setup**

* Add your site and author details in `content/data/seo.json`.
    
* Add your Google Analytics and Disqus keys to `content/data/site.json`.
    
* Get a workflow going to see your site's output (with CloudCannon or Next.js locally).
    

## **Editing the Template**

**Justice** is already optimised for adding, updating and removing pages, staff, posts, company details and footer elements in [CloudCannon](https://app.cloudcannon.com/).

### **Posts**

* Add, update or remove a post in the Posts collection.
    
* The **Staff Author** field links to members in the **Staff collection**.
    
* Change the defaults when new posts are created in `content/posts/_defaults.md`
    

### **Contact Form**

* Preconfigured to work with [CloudCannon](https://app.cloudcannon.com/).
    
* Sends email to the address listed in company details.
    

### **Staff**

* Reused around the site to save multiple editing locations.
    

### **Footer**

* Exposed as a data file to give clients better access.
    
* Set in the **Data / Footer section**.
    

### **Company details**

Reused around the site to save multiple editing locations. Set in the **Data / Company section**.

If you want to read my latest article explaining **How to configure and Edit Jamstack sites on cloud cannon** please [click here](https://creativelightbox.net/how-to-configure-cloudcannon-collections-to-enable-post-page-content-editing).

## **Deploying the project to Cloudcannon**

If you want to deploy this template or your own edited Website to cloudcannon, I'll explain in detail how you can achieve this step. Please read this article [How to deploy Jamstack sites to cloudcannon](https://creativelightbox.net/how-to-deploy-jamstack-sites-to-cloudcannon)

### **Need further assistance?**

Ask the [Cloudcannon team](https://cloudcannon.com/support/) or leave a comment. I' 'll try to get back to you as soon as I can.

## **Conclusion**

Using pre-configured Cloudcannon themes can save you time and effort, provide you with a professional design, ensure your website is mobile-friendly, and be easily customized to suit your needs – all while keeping your budget in check. So the next time you need to create a website, consider using a pre-configured Cloudcannon theme as a starting point.

## **What's Next?**

If you want to follow along with more advanced stuff in the next article. I'll talk about **How to add a new site to enable branching workflows on cloudcannon?**

**Thanks for the read! Now go practice & build something awesome!**