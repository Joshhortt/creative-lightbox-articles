# How to Install Apollo Server and GraphQL?

## What is GrapQL?

[GraphQL](https://graphql.org/) is a language for querying data. Unlike most query languages (such as SQL), you don’t use GraphQL to query a particular type of data store (such as a MySQL database). Instead, you use GraphQL to query data from any number of different sources.

## What is Apollo Server?

[Apollo Server](https://www.apollographql.com/docs/apollo-server/) is an open-source, spec-compliant GraphQL server that's compatible with any GraphQL client, including Apollo Client. It's the best way to build a production-ready, self-documenting GraphQL API that can use data from any source.

> ![Apollo Server](https://cdn.hashnode.com/res/hashnode/image/upload/v1667656663172/CfBd62fq1.png?auto=compress)
>
> ## Why use Apollo Server together with GraphQL?
>
> Building your GraphQL API with the [Apollo](https://www.apollographql.com/) platform gives teams and organizations access to modern tooling that helps them quickly uncover bugs, gain visibility into their API, and develop challenging features such as caching, and in general servers as a confidence booster.

### Introduction

We have an understanding of how GraphQL is a typed query language that allows client-side applications to request the data they want. With that said, how would one go about creating a GraphQL API? GraphQL is a specification, not a direct implementation. This means GraphQL can be implemented in multiple programming languages. 

### Prerequisites

**To complete this tutorial, you’ll need:**

*   To have a basic understanding of HTML, CSS, and JavaScript. 
*   Prior development experience working with a newer front-end technology (e.g. React) and Git/npm is preferable. 
*   Know how to create a minimal Node/Express server. 
*   Know how to Enable automatic reloading with Nodemon as a Development tool.
*   A local development environment for Node.js. Follow How to Install Node.js & Create a Local Development Environment.
*   Basic knowledge of GraphQL is a plus.<br>

*This tutorial was verified with Node v16.3.0, npm v8.7.0 apollo-server v2.31.1, graphql v15.4.0*

## Install Apollo Server & GraphQL

Install Apollo to create your API.
In particular, by using the Apollo Server package, which is the server package within the Apollo ecosystem. Apollo Server allows us to create a production-ready, self-documenting, GraphQL API in Node applications. It's really easy to get started with and incrementally adaptable.

**We'll install the Express variation of the popular Apollo Server library and the GraphQL JavaScript library.**

Apollo Server is one of the libraries within the Apollo framework and its responsibility is to help build a GraphQL API within Node applications. Apollo Server enables us to connect a GraphQL schema to a server and can be used to spin up a stand-alone server, be an add-on to an existing Node server, or even work within "serverless" environments. In this case, we'll go with the approach of adding Apollo Server to our existing Node/Express server.

### Install Apollo Server Express

To add Apollo Server to an existing Node/Express server project, we'll install the apollo-server-express library.

    $ npm install apollo-server-express

Note that [apollo-server-express](https://www.npmjs.com/package/apollo-server-express/) is a TypeScript project so we won't have to install an additional type declaration file for it.

### Install GraphQL to create your API

To use Apollo Server, you need to install another dependency into your app. You'll need to install the graphql JavaScript library. This is because the graphql library is a peer dependency of the Apollo Server package. In addition, the graphql library will also be used in our first attempt to build our schema.
First you install the graphql library as an application dependency.

    $ npm install graphql

Note that [graphql javascript library](https://graphql.org/code/#javascript/) doesn’t have its own type definitions, so you also need to install an additional type declaration file for it, to your application dev dependencies

    $ npm install -D @types/graphql

These are the only additional libraries you need to begin developing our GraphQL Schema!
To run our code with Nodemon, all we have to do now is type the npm run start command in our terminal:

    $ npm run start

When we now run the server and head to the location of our GraphQL Endpoint - https://localhost:9000/api, we’ll be presented with an IDE Sandbox to interact with your API!

> ![Apollo Server Sandbox](https://cdn.hashnode.com/res/hashnode/image/upload/v1667656720726/yLMQJURa1.png?auto=compress)

## Conclusion

In this short tutorial, we looked at how to install GraphQL server and Apollo Server and all aditional dependencies. We also saw how access A Apollo Graphql Sandbox by running your local nodemon server.

To know more about creating a GraphQL schema with the GraphQL JS Library follow up to read this article: **How to Create a GraphQL schema with the GraphQL JS Library.**