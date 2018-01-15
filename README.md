# README #

This README is about how to build a electron program of revopos project.

### Environment ###

* Electron needed  ```npm install -g electron```
* Electron-builder needed  ```npm install -g electron-builder --save-dev```

### Build steps ###

* Put electron configuration files into your porject(main.ts).
+ Check your package.json.
	* package.json must contain "version" "name" "author" "main":"(your main.ts path)"
	* if you want to use your own icon , add it like this
	```
	"build": {
    	"win": {
    		"icon": "www/assets/icon/revopos"
    	}
    },

	```
	\*icon must be a ico image format , at least 1024*1024\*
* ```ionic build --prod```
+ Check if your project is using jQuery dependency in your index.html.
	*If you do have jQuery in your project, add this command after the import of jQuery
	```html
	<script>window.jQuery = window.$ = module.exports</script>
	```
* You can check your project before you build electron if you like by using this commmand ```electron .```
* Build your electron program ```electron-builder --win --x64```

### Revopos program uploading ###

* Find your program in your project/dist.
* Rename the 'Win unpacked' file to 'build' and compress it into zip.
* Creat a new dictionary named by version add upload build.zip in it.

### Precautions ###

* Always remember to check your index.html after ```ionic build```
* Check your program first before you upload it.
