# oTranscribe+ Desktop Application

This is the oTranscribe+ desktop application version.

This version of oTranscribe+ is the code based on Electron.js which builds the desktop application. It uses a customized variation of the oTranscribe+ web application. On this, models and URLs are adapted for being consumed locally. 

## Build

### Dependencies

The current version has been made using Node version 18.6.0 and npm version 8.13.2. To install required libraries do:

```
npm install
```

### Update oTranscribe+ code

To build the Desktop application you need the oTranscribe+ code adapted for it. This code is included in this repository as it is an essential part of the application, but as long as oTranscribe+ evolves the code inside this repository must also be updated.

oTranscribe+ code is included in the `otranscribe` folder. It keeps a `version` file which indicates the day and commit identifier that was used for the current state. You can build those required files from the oTranscribe+ project using the command `make build_app`, then copy result files from its `dist` folder into the `otranscribe` folder of this project.

### Commands

Next commands build the oTranscribe+ desktop application:

- `npm start` runs the application for development purposes.
- `npm run package` creates the application files. Result application will appear on the `out` directory.
- `npm run make` creates the application redistributable files. Result files will appear on the `out/make` directory.
