# React Native Packages

A monorepo to manage Gradle configuration changes required to integrate third-party React Native packages into `WordPress-Android`.

## Prerequisites

-   Node.js
    This project is a JavaScript project and requires [Node.js](https://nodejs.org/). The project is built using Node.js v14, and npm v6. See the [LTS release schedule](https://github.com/nodejs/Release#release-schedule) for details.

    We recommend using the [Node Version Manager](https://github.com/nvm-sh/nvm) (nvm) since it is the easiest way to install and manage node for macOS, Linux, and Windows 10 using WSL2. See the Nodejs site for additional installation instructions.

-   Git
    This project is using git for source control. Make sure you have an updated version of git installed on your computer, as well as a GitHub account.

## Getting Started

```bash
$ git clone https://github.com/YOUR_GITHUB_USERNAME/react-native-packages.git
$ cd react-native-packages
$ git remote add upstream https://github.com/wordPress-mobile/react-native-packages.git
$ npm install
$ npm run bootstrap
```

## Generating Package Patches

This project utilizes [`patch-package`](https://github.com/ds300/patch-package) to apply modifications to the React Native packages dependencies. The modifications are captured in a `patches` directory within each package. The general process for capturing modifications for a package are as follows.

1. Modify the relevant third-party package within `node_modules`, e.g. `./packages/react-native-masked-view/node_modules/@react-native-community/masked-view`.
1. Run `patch-packages` to generate the patch file.
    ```bash
    $ cd ./packages/react-native-masked-view
    $ npm run patch-package @react-native-community/masked-view
    ```
1. Commit the patch files.
