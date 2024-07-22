# Portfolio Website

## Scaffolding provided by Vite

This template should help get you started developing with Vue 3 and TypeScript in Vite. The template uses Vue 3 `<script setup>` SFCs, check out the [script setup docs](https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup) to learn more.

## Recommended Setup

- [VS Code](https://code.visualstudio.com/) + [Vue - Official](https://marketplace.visualstudio.com/items?itemName=Vue.volar) (previously Volar) and disable Vetur

- Use [vue-tsc](https://github.com/vuejs/language-tools/tree/master/packages/tsc) for performing the same type checking from the command line, or for generating d.ts files for SFCs.

## Deployed to github.io

I've chosen to deploy to github.io so the portfolio is connected to my github account where the projects are hosted. I had a preexisting github pages project, the base branch just needed updating.

## Deploy to github.io

```bash
npm run build
cd dist
git init
git add .
git commit -m "Deploy Vue.js site"
git remote add origin <https://github.com/USERNAME/USERNAME.github.io.git>
git push -f origin master
```

## Updating

1. Ensure gh-pages is Installed

If you haven't already installed gh-pages, install it:

```bash
npm install --save-dev gh-pages
```

1. Update package.json Scripts
   Add the following scripts to your package.json:

   ```json
   "scripts": {
   "build": "vite build",
   "predeploy": "npm run build",
   "deploy": "gh-pages -d dist -r https://github.com/USERNAME/USERNAME.github.io.git -b master"  // Change to "main" if your default branch is main
   }
   ```

1. Further updates will be published when the 'npm run deploy' script is used.
