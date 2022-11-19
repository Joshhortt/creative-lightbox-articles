---
title: How to Keep Project Dependencies Up-To-Date

subtitle: If you are looking for a quick way to update your project dependencies to the latest versions, you are in the right place. 

slug: how-to-keep-project-dependencies-up-to-date

tags: dependencies, npm, packages, versions

cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1668860508035/dxfVYNuCX.png?auto=compress

domain: creativelightbox.net
---

Due to bug patches, new features, and other changes, dependencies may eventually become out-of-date. 

It becomes increasingly difficult to stay current with these upgrades the more project dependencies you have.

Packages that are out of date might compromise security and degrade performance. Vulnerabilities are prevented with updated packages. 

This implies that regular dependency updates and checks are crucial.

You will discover how to accomplish it in only three or five optional steps in this article! 


## How to Check for Outdated Dependencies

It's vital to know that dependency package updates, even if it's a major versions, may bring about breaking changes to your project.

Of course, upgrading dependencies is a blunt instrument. As you indicated, if the project is empty and nothing can break, it's okay.

On the other hand, if you're working on a more advanced project, you probably want to make sure that your dependencies haven't undergone any breaking changes before you upgrade.

For a quick overview of the number of dependency updates, you need to first use **npm outdated**.

### 1. Check for Outdated Dependencies

The first step is to go to your project's directory and run:

```
$ npm outdated
```

Every installed dependency will be examined by this command, and the current version will be compared to the most recent version in the npm registry. 

It prints out as a table detailing all of the new available versions.

![npm oudated example](https://cdn.hashnode.com/res/hashnode/image/upload/v1668852265512/IF2mwqa7G.png?auto=compress)


There are **no additional packages** that need to be downloaded because it is built within npm. 

For **Yarn, specific solution**, refer to this [StackOverflow answer](https://stackoverflow.com/questions/62650640/yarn-how-do-i-update-each-dependency-in-package-json-to-the-latest-version/62650754#62650754).

## How to Update Project Dependencies

Let's imagine you wish to update some dependencies in a project that has a few out-of-date ones. 

Or maybe you ...

Consider that you wish to revisit a project of yours that has a little bit fallen by the wayside.

Regardless of the situation, you could question yourself:

* **How should I update them?**

* **Should I update them all at once or one at a time?**

* **Which tools or commands should I employ?**

The **' npm-check-updates** package, which brings your project dependencies up to date, is the solution.

You have two options for using the package: either install it **globally** or use **npx**. 

### 2. Update the dependencies with NPX

The second step is to go to your project's directory and run:

```
$ npx npm-check-updates
```

The above command displays all the outdated dependencies from your project.

![npx npm-check-updates example](https://cdn.hashnode.com/res/hashnode/image/upload/v1668283005987/-Zr9Tp8ph.jpg?auto=compress)

The image illustrates an example output. The output shows the current versions and the latest versions.

I'd suggest npm-check-updates for an additional sophisticated and adaptable upgrading experience. 

This package offers some extra customization options in addition to all that npm obsolete and npm upgrades can accomplish. 

However, a package installation might be necessary.

Install the npm-check-updates package globally to get going:

### 3. Update the dependencies Globally

The third step (optional) is to go to your project's directory and run:

```
$ npm-check-updates -u
```

The command doesn't automatically install the new versions. It just overwrites your `package.json` file with the latest versions. 

![npx npm-check-updates -u example](https://cdn.hashnode.com/res/hashnode/image/upload/v1668284419013/4BoB7gn7O.png?auto=compress) 

That means you have to install them yourself, which takes us to the fourth step and fifth steps.

## How to Install New Dependency Versions
### 4. Install-Package Globally

The fourth step (optional) is to go to your project's directory and run:

```
npm install -g npm-check-updates
```
### 5. Install the new versions

The last step is to install the new versions by running:

```
$ npm install

// or

$ yarn install
```

After this, you are done! The project will use the latest versions.

### Learn more
To learn more about npm as a product, upcoming new features, and interesting uses of npm be sure to vist: [npm docs](https://docs.npmjs.com/) or follow [@npmjs on Twitter](https://twitter.com/npmjs).

For mentoring, tutorials, and learning, visit [node school](https://nodeschool.io/). Consider attending or hosting a nodeschool event (usually free!) at a site near you, or use the self-help tools you can find on the site.

## Conclusion

Consistently updating your dependencies will improve the efficiency and security of your apps.

Useful tools to check for packages that need a version upgrade are **npm outdated** and **npm-check-updates**.

I advise testing them both to determine which offers a better developer experience.

I'm hoping that these techniques will be useful as you update your project dependencies!