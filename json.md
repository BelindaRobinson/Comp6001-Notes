## Week Two:

package.json to avoid WARNS when running npm in git, this also links to the main.js file

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