# Setup the Monorepo

packages folder
- x folders what you need
- each contains  a package.json, best with a prefix  @shortcut/ like @mr/

Add private flag & workspaces to package.json

## Server + TS

Lets start the TS setup with the server.

Create index.ts

Compile ts to js:
./node_modules/.bin/tsc packages/server/src/index.ts 

See the JS file index.js

Run the JS:
node packages/server/src/index.js 

Add tsconfig.json to server
./node_modules/.bin/tsc --project packages/server/

JS still running:
node packages/server/src/index.js 

## Workspace commands

Lets play around and put that scripts into 
packages/server/package.json:

"scripts": {
    "compile": "tsc --project tsconfig.json",
    "start": "node src/index.js"
    "play": "yarn compile && yarn start",
},

Add script to package.json:

"scripts": {
    "play": "yarn workspace @mr/server play"
},

Voila, Up and Running.
