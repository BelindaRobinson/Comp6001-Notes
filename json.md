## Week One:

const {app, BrowserWindow} = require('electron') - This lets you create and control browser depending on what you want to do
const path = require('path') - used with Node
const url = require('url') - used with Node

## Week Two:

package.json to avoid WARNS when running npm in git 

```json 
{
    "name": "ApplicationName",
    "version" : "0.0.1",
    "main" : "main.js",
    "scripts" : {
        "start" : "electron ."
    },
    "description" : "Describe what your app is about",
    "repository" : "https://github.com/your_repository",
    "license" : "Type of license"
}
```