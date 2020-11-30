# Render Environments for JavaScript Frameworks

When you select a JavaScript framework for your next project it matters which environments it can render in. Can it render in just one environment or multiple, on a server, in cloud functions, in a web browser, maybe even in a service worker? This document compares support of popular JavaScript frameworks for different render environments with links to help you get started.


## Render environments

- **Server-Side Rendering (SSR)**: dynamically render a page during runtime using a _Node.js(-like) server_.
- **Serverless SSR**: dynamically render a page during runtime using a _Node.js(-like) cloud function_.
- **Incremental SSR**: dynamically render and cache a page server-side during runtime. This is ideal for large sites as you can pre-render only the most important pages during build-time (SSG) and render and cache the rest during run-time (SSR).
- **Static Site Generation (SSG)**: pre-render pages during build-time, so they can be served as a static site.
- **Incremental SSG**: render and add new pages during build-time to a previously generated (cached) site.
- **Service Worker Rendering (SWR)**: dynamically render a page _in a service worker_ during runtime.
- **Client-Side Rendering (CSR)**: dynamically render a page _in the browser_ during runtime.


## Supported render environments

**Framework / Library** | **Server-Side Rendering (SSR)**  | **Serverless SSR** | **Incremental SSR** | **Static Site Generation (SSG)** | **Incremental SSG** | **Service Worker Rendering (SWR)** | **Client-Side Rendering (CSR)**
--- | --- | --- | --- | --- | --- | --- | ---
[**Next.js**](https://nextjs.org/) [![GitHub stars](https://img.shields.io/github/stars/vercel/next.js.svg?style=social&label=Star&maxAge=2592000)](https://github.com/vercel/next.js) (React) | ✅[`next start` or custom server](https://nextjs.org/docs/advanced-features/custom-server) | ✅[Vercel](https://vercel.com/solutions/nextjs) <br> ✅[Netlify](https://github.com/netlify/next-on-netlify) <br> ✅[AWS](https://github.com/serverless-nextjs/serverless-next.js) <br> ✅[Firebase](https://itnext.io/deploying-next-js-app-to-firebase-functions-eb473791d79e) <br> ❌[Cloudflare](https://github.com/vercel/next.js/issues/6282#issuecomment-502160549) | ✅[Vercel](https://nextjs.org/blog/next-9-5#stable-incremental-static-regeneration) <br> ❌[Netlify](https://github.com/netlify/next-on-netlify#fallbacks-for-pages-with-getstaticpaths) <br> ❌AWS | ✅[`next export`](https://nextjs.org/docs/advanced-features/static-html-export) | ❓ | ❓ |  ✅ universal SPA + routing
[**NuxtJS**](https://nuxtjs.org/) [![GitHub stars](https://img.shields.io/github/stars/nuxt/nuxt.js?style=social&label=Star&maxAge=2592000)](https://github.com/nuxt/nuxt.js) (Vue) | ✅[`nuxt start` or custom server](https://nuxtjs.org/guides/concepts/server-side-rendering/) | 🚧[Nuxt3 serverless support](https://nuxtjs.slides.com/atinux/state-of-nuxt-2020-november#/5/13/7) ✅[Vercel](https://nuxtjs.org/faq/now-deployment/) <br> ❌Netlify <br> ✅[AWS](https://logaretm.com/blog/2019-08-29-cost-effective-serverless-nuxt-js/) ([alt.](https://github.com/serverless/examples/tree/master/aws-node-vue-nuxt-ssr)) <br> ✅[Firebase](https://itnext.io/how-to-create-a-ssr-serverless-app-with-firebase-nuxt-js-in-an-hour-6e6e03d0b3b8) | ❓ |  ✅[`nuxt export` or `nuxt generate`](https://nuxtjs.org/blog/going-full-static/)| ❓ | ❓ |  ✅ universal SPA + routing
[**Sapper**](https://sapper.svelte.dev/) [![GitHub stars](https://img.shields.io/github/stars/sveltejs/sapper.svg?style=social&label=Star&maxAge=2592000)](https://github.com/sveltejs/sapper) (Svelte) | ✅[Express-style middleware](https://sapper.svelte.dev/docs#src_server_js) | ✅[Vercel](https://github.com/thgh/vercel-sapper) <br> ✅[Firebase](https://blog.logrocket.com/build-an-ssr-web-app-with-firebase-functions-hosting-and-svelte-sapper/) <br> ❓Netlify | ❓ | ✅ | ❓ | ❓ |  ✅ universal SPA + routing
[**Eleventy**](https://www.11ty.dev/) [![GitHub stars](https://img.shields.io/github/stars/11ty/eleventy.svg?style=social&label=Star&maxAge=2592000)](https://github.com/11ty/eleventy) (Nunjucks + 10 more) | ❌ | ❌ | ❌ | ✅ | 🚧[In progress](https://github.com/11ty/eleventy/issues/108) | ❌ | ❌ 
[**Gatsby**](https://www.gatsbyjs.com/) [![GitHub stars](https://img.shields.io/github/stars/gatsbyjs/gatsby.svg?style=social&label=Star&maxAge=2592000)](https://github.com/gatsbyjs/gatsby) (React) | ❌ | ❌ | ❌ | ✅ | ✅[Gatsby Cloud](https://www.gatsbyjs.com/blog/2020-04-22-announcing-incremental-builds/) <br> ✅[Netlify](https://www.netlify.com/blog/2020/04/23/enable-gatsby-incremental-builds-on-netlify/) | ❓ | ✅ universal SPA + routing
[**React Static**](https://github.com/react-static/react-static) [![GitHub stars](https://img.shields.io/github/stars/react-static/react-static.svg?style=social&label=Star&maxAge=2592000)](https://github.com/react-static/react-static) (React) | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ universal SPA + routing
[**Elder.js**](https://github.com/Elderjs/elderjs) [![GitHub stars](https://img.shields.io/github/stars/Elderjs/elderjs.svg?style=social&label=Star&maxAge=2592000)](https://github.com/Elderjs/elderjs) (Svelte) | ✅[Express-style middleware](https://github.com/Elderjs/template/blob/1dfb3b2/src/server.js#L27) | 🚧[Proof-of-concept](https://github.com/Elderjs/elderjs/issues/28) | ❓ | ✅ | ❓ | ❓ |  ✅ optional partial hydration (no routing)


## Contributing

- Got a framework or library you think should be in here? Feel free to submit a pull request to add it to the support table.
- Got a working render enviroment that's not in the support table? Proof me wrong with a link to code or an article of a working render environment. 
- Is a render enviroment not/no longer supported, but still in the support table? Please link to a relevant issue.

I've got GitHub notifications turned off, so if I don't reply right away, feel free to send me a reminder via [@jbmoelker on Twitter](https://twitter.com/jbmoelker).


## License

Licensed [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/).
