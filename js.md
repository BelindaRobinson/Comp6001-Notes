## Week Two

Defining our constant, these do not change 
```javascript
const {app, BrowserWindow} = require('electron')
const path = require('path')
const url = require('url')
```

Defining other variables, to be able to access variables in muiltple code blocks , we need to define them outside thse code blocks. 
```javascript
let win
```

Defining out functions, the line below defines a function and this function creates a window. we define this as a separate function, becuase we need to call it more than once. 
When the `frame: false` is used we still need to move the window around this is done in the css with the `-webkit-` code
`__dirname` is a set variable that represents the base directory of the project you are in.
```javascript
function createWindow () {
  win = new BrowserWindow({frame: false, titleBarStyle:'hidden', width: 600, height: 600, minWidth: 400, minHeight: 400})
  win.loadURL(url.format({
    pathname: path.join(__dirname, 'index.html'),
    protocol: 'file:',
    slashes: true
  }))
```

Next we need to unload the variables content when the window is closed. This does not quit the application, but allows for the window to be reloaded
`() =>` is an easy way of writing `function()`
```javascript 
  win.on('closed', () => {
    win = null
  })
}
```

The `.on()` is a way for node to set a method. Now that we have broken down the first function lets combine the `app` constant with its function
```javascript 
app.on('ready', createWindow)

app.on('window-all-closed', () => {
  if (process.platform !== 'darwin') {
    app.quit()
  }
})

app.on('activate', () => {
  if (win === null) {
    createWindow()
  }
})


