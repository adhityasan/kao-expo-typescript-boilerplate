# Kao Expo Typescript Template

This template was initialized with `expo-cli` and i choose `yarn` as package manager for faster installing cached packages. This template includes some default configuration like:

- `prettier` - **Code Formatter** that configured by `.prettierrc` file
- vscode shareable settings file - `.vscode/settings.json`

## Available Scripts

In the project directory, you can run:

### `yarn start`

Runs `expo start` command.

### commands and steps i used to setup this template

Before initializing this template, i'm using:

- `nodejs` version `v16.15.0`
- `yarn` version `1.22.17`
- `npm` version `8.10.0`
- `expo-cli` version `5.4.11`

Commands and steps are:

- run expo init command
  ```sh
  expo init kao-expo-typescript-template --typescript --yarn
  ```
- setup prettier config file `.prettierrc`
- setup vscode config file `.vscode/settings.json`
- install testing framework `jest` by `expo-cli`.
  **It's important** for using `expo install` and not `yarn add` to install the compatible version of jest-expo for the project
  ```sh
  expo install jest jest-expo
  yarn add @types/jest
  ```
- setup `jest` configuration in `package.json`
  ```json
  {
    "scripts": {
      // other scripts...
      "test": "jest"
    },
    "jest": {
      "preset": "jest-expo",
      "moduleFileExtensions": ["ts", "tsx", "js", "json", "jsx", "node"]
    }
  }
  ```
- install `react-test-renderer` so i can render app / component in the testing files.
  **It's important** to install the same version of `react-test-renderer` with `react` version
  ```sh
  yarn add react-test-renderer@17.0.2 @types/react-test-renderer@17.0.2
  ```
- create a single test file `App.test.tsx`
