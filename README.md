# oTranscribe+ Desktop Application

This is the oTranscribe+ desktop application. The code of this version is based on Electron.js which builds the desktop application for different platforms. It uses a customized variation of the oTranscribe+ web application. On this, models and URLs are adapted for being consumed locally. 

## Getting started

### Dependencies

The current version has been made using Node version 18.6.0 and npm version 8.13.2. To install required libraries do:

```
npm install
```

### Update oTranscribe+ code

To build the Desktop application you need the oTranscribe+ code already adapted for it. This code is included in the current repository as it is an essential part of the application, but as long as oTranscribe+ evolves the code inside this repository must also be updated.

oTranscribe+ code files are included in the `otranscribe` folder. It keeps a `version` file which indicates the day and commit identifier that was used for the current state. You can build those required files from the oTranscribe+ project using the command `make build_app`, then copy result files from its `dist` folder into the `otranscribe` folder of this project.

### Commands

Next commands build the oTranscribe+ desktop application:

- `npm start` runs the application for development purposes.
- `npm run package` creates the application files. Result application will appear on the `out` directory.

## Build

For building redistributable packages it is used the `electron-forge` tool. 

### Commands

- `npm run make` creates the application redistributable files for the current platform. Result files will appear on the `out/make` directory.
- `npm run make-linux` creates the application redistributable files for Linux platforms.
- `npm run make-win` creates the application redistributable files for the Windows platform.
- `npm run make-mac`creates the application redistributable files for the MacOS platform.

### Requisites for building for Windows on Linux

If you want to build for Windows from Linux you will need to install `Mono` and `Wine`. This is the command for doing it on Ubuntu:

```
sudo apt install mono-complete wine
```

For signing the windows executable follow instructions steps on https://www.electronforge.io/guides/code-signing/code-signing-windows#using-electron-forge .

If you add your certificate to `assets/win` you will just need to add these lines in the configuration of :

```json
"certificateFile": "./assets/win/cert.pfx",
"certificatePassword": "this-is-a-secret"
```

