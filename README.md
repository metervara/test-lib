# Test Lib

This repo is just an emptyy library to test how to set up a vite project for building a lib, and adding workflows for publsihing an example and the library itself. 

## Test locally 
Build and run the project usinhg the following commands

```bash
npm run build
npx serve .
```

Then visit the example page here (Port might differ): http://localhost:3000/example/

## Creating a new release
To create a new release, bump the version (e.g. 0.1.0 → 0.1.1) in your package.json and push the changes. Github actions will then add a tag to that commit, push it and dreate a github release.