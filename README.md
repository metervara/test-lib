# Test Lib

This repo is just an emptyy library to test how to set up a vite project for building a lib, and adding workflows for publsihing an example and the library itself. 

## Test locally 
Build and run the project usinhg the following commands

```bash
npm run build
npx serve .
```

Then visit the example page here (Port might differ): http://localhost:3000/example/

## Creating a new release and deploying to github pages
There are workflows for new releases in the repo.

Before running any workflows you need to set up a Repository secret, with a personal access token so the workflows can authenticate. Find or generate a personal token (check 1Password). Then in the repo under ```https://github.com/metervara/test-lib/settings/secrets/actions``` create a new repository secret, name it ```GH_PAT```and paste the value for your personal access token in there.

To create a new release, bump the version (e.g. 0.1.0 → 0.1.1) in your package.json and push the changes. Github actions will then add a tag to that commit, push it and dreate a github release.

The command ```npm run build``` copies the deploy to a folder ```docs``` taht is then deployed by github. To enable deployment of github pages, go to ```https://github.com/metervara/test-lib/settings/pages``` and set source to ```Deploy from branch```, branch to  ```main``` + ```/docs```. 

To make a new deploy, you make any changes relevant, then run build and push the changes
```bash
npm run build
git add .
git commit -m "Update docs for GitHub Pages"
git push
```