# Generic Release Script for NPM
Release script needed to release the PODs to NPM. Make sure to only release the `/lib` folder to NPM!

## Requirements to the REPO
* develop as main branch and master as released branch
* user with admin rights to develop and master must execute the script
* deployment should always be inside @axa-ch npm org
* user have to have publish rights into the repo

## Step by step guide
* Create your awesome new repository and run `npm install @axa-ch/generic-release --save-dev`
* Create a new branch called `develop`. ⚡
* Edit git settings and make `develop` the default branch ⚡ (https://help.github.com/articles/setting-the-default-branch/).
* Protect `master` and `develop` from direct push if needed.
* In your `.npmignore` make sure to add all development folders like `src` or `stack`. Remember, npm publish will ignore the `.gitignore` if a `.npmignore` file is in the root directory ⚡
* Make sure that in your package.json the correct org is set like so: `@axa-ch/your-awesome-project` ⚡
* When starting your development, make sure to set the version `0.0.0` if you start in BETA. ⚡ This setting also have to be applied into the package.json
* Make sure that you have a npm account in the `axa-ch` npm org
* Log in into npm in your cli simply by `npm login`
* Now we are ready to release the first version to NPM! Only for very most first time, run `npm publish --access public`
* Now the release script will work for you. It will add tags in github and increase the BETA counter. More instructions will be found when running the script itself (guided release)
* You can run the release script simply by running `node_modules/.bin/generic-release` in your cli in the root directory of your project. Of course you can also create a npm job for it like so:
```
"scripts": {
  "release": "generic-release"
}
```

Have fun in releasing!

Config example of the axa-ch-pod:

```
{
  "name": "@axa-ch/axa-ch-pod",
  "version": "0.0.0",
  "description": "AXA CH pod",
  "scripts": {
    "release": "generic-release"
  },
  "repository": {
    "type": "git",
    "url": "git+https://github.com/axa-ch/axa-ch-pod.git"
  },
  "author": "Luca Mele",
  "license": "SEE LICENSE IN README.md",
  "bugs": {
    "url": "https://github.com/axa-ch/axa-ch-pod/issues"
  },
  "homepage": "https://github.com/axa-ch/axa-ch-pod#readme",
  "devDependencies": {
    "@axa-ch/generic-release": "^1.0.1"
  },
  "dependencies": {}
}
```


#### License: AXA Versicherungen AG. All rights reserved
