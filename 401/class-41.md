# React 4

## Explain the concept of dynamic routes in Next.js and how they differ from static routes.

Dynamic routes in Next.js allow us to create pages that can dynamically generate content based on the URL paths. 
With Dynamic routes, a single page component can render multiple pages with different content based on the URL 
parameters. 

Static Routes, are pages that are pre-generated during the build time on the client side, while dynamic routes 
generate pages on the server-side at runtime. 


## Describe the process of deploying a Next.js application. What are the key steps involved, and what are some 
deployment platforms you can use?

The general process of deploying a Next.js application to Vercel are: 

1. Create a Vercel account: To deploy your Next.js application to Vercel, you will need to create an account on the 
Vercel website.

2. Connect your GitHub or GitLab repository: Vercel allows you to deploy your application from your Git repository. 
Connect your repository with your Vercel account to deploy your app.

3. Create a new Next.js project in Vercel: Click on the "New Project" button on the Vercel dashboard and select the 
option to deploy a Next.js application.

4. Configure the deployment settings: Configure the deployment settings for your Next.js app by selecting the build 
command and output directory for your app.

5. Deploy your app: Once you have configured the deployment settings, you can deploy your app by clicking on the 
"Deploy" button in Vercel.

6. Verify the deployment: Once the deployment is complete, Vercel will provide you with a URL where you can access 
your deployed Next.js application. Verify that your app is working correctly.

Some other platforms that can be used for deploying a Next.js app are Heroku, AWS, Netlify and Google Cloud. 

## How does Next.js handle static file serving? Discuss the default folder structure for storing static assets and 
explain how to reference them in a Next.js application.

In Next.js, static files such as images, videos, and other assets are served using a folder named public by default. This folder is located in the root directory of the Next.js application and can be used to store any static assets that need to be served to users. 

To reference these static assets in a Next.js application, you can use the special public directory path, followed by the name of the file or asset. For example, if you have an image called my-image.png in the public folder, you can reference it in your code using the path "/my-image.png"


>References
> 
> [Next.js - Dynamic Routes](https://nextjs.org/learn/basics/dynamic-routes)
> 
> [Next.js - Deployment](https://nextjs.org/learn/basics/deploying-nextjs-app)
> 
> [Next.js 10 is here](https://www.youtube.com/watch?v=JWCS5IdECVI)
> 
> [Next.js - Static File Serving](https://nextjs.org/docs/basic-features/static-file-serving)