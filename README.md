# Gravatar Look Up Tool

<img src="./public/favicon.png" alt="Gravatar Lookup Tool Logo" width="200"/>

### Available here: [gravatarlookup.vercel.app](https://gravatarlookup.vercel.app)

Looks up [Gravatar](https://en.gravatar.com/) profile pictures via an email, good for easily grabbing and downloading your own avatar if you don't have access to it anymore

This app uses [Svelte](https://svelte.dev/), as well as the beautiful [Sakura](https://github.com/oxalorg/sakura/) and was mainly made so I can get my hands dirty and build _something_ with Svelte. Deployment and Getting started instructions 
are below.

## Get started

Install the dependencies...

```bash
cd svelte-app
npm install
```

...then start [Rollup](https://rollupjs.org):

```bash
npm run dev
```

Navigate to [localhost:5000](http://localhost:5000). You should see your app running. Edit a component file in `src`, save it, and reload the page to see your changes.

By default, the server will only respond to requests from localhost. To allow connections from other computers, edit the `sirv` commands in package.json to include the option `--host 0.0.0.0`.

If you're using [Visual Studio Code](https://code.visualstudio.com/) we recommend installing the official extension [Svelte for VS Code](https://marketplace.visualstudio.com/items?itemName=svelte.svelte-vscode). If you are using other editors you may need to install a plugin in order to get syntax highlighting and intellisense.

## Building and running in production mode

To create an optimised version of the app:

```bash
npm run build
```

## Deploying to the web

### With [Vercel](https://vercel.com)

Install `vercel` if you haven't already:

```bash
npm install -g vercel
```

Then, from within your project folder:

```bash
cd public
vercel deploy --name my-project
```
