# Welcome

This project is to create a branded responsive website theme for Canopy products, with the requirement to be easily customizable for a customer.

This project uses less to make rebranding of the template easier. Less is a pre-compiler for the CSS styling sheet; this allows CSS to be used with greater flexability and can allow editing to be easier. This is done by compiling a Less file into CSS, which is then linked in the ```html <head>``` of the html pages.

This template builds on Twitter Bootstrap; a framework that allows for easier creation of responsive websites. A good guide on how to use twitter bootstrap and the included classes is [here](http://getbootstrap.com/css/ "bootstrap"). Using this allows us to change only what we need to rather than creating a full CSS file from scratch.


## Included Files

The **lessout-v2.css** file changes twitter bootstrap to match the Canopy theme and should be used in addition to the normal twitter bootstrap files; these are being recovered remotely for this project but should be included in the local directory.
This file has been compiled from the .less file.

**preview.html**  shows the customized elements in this template including the header, footer, buttons and tables.
login.html shows a simple fully html canopy branded login page.

Key sections have been templated ready for content.
These include:
*	main.html - a minimal header/footer template
*	contact.html - a simple template for a company contact information
*	contact-test.html - main+contact
*	header.html - header template only
*	footer.html - footer template only


## Rebranding

**All edits for the CSS should be done in the _canopycss.less_ file and it is recommended that you rename the file to suit the project you are on. E.G. cip.less**

To customize this for your site, follow the instructions below. All CSS edits should follow CSS convention, a good reference guide can be found [here](http://www.w3schools.com/cssref/default.asp "W3Schools")

Your first edit should be the color scheme. For bootstrap there is a set of classes that are used for aspects of the webpage: e.g. Buttons. These colors can allow for easier distinction of areas such as warnings and successes without having to change each class. The colors can be presented as Hex (#0066a2), rgb (0, 102, 162) or rgba (0, 102, 162, 1.0); in order to control opacity you will need to use rgba otherwise all colors will be fully opaque.

The colors we have used for this template are as follows;

* page-background: #f6f5f5;
* info: #7a42b3;
* warning: #ff683b;
* danger: #ff0000;
* success: #3fb618;
* primary: #0066a2;
* default: #ffffff;
* disabled: #000000;
* info-hover: #583081;
* warning-hover: #E65E35;
* danger-hover: #CC0000;
* success-hover: #2f8912;
* primary-hover: #0066a2;
* default-hover: transparent;

To rebrand this template for a customer you will need to edit the canopycss.less file.

The sections for rebranding are commented in the .less file, there should be no need to edit anything but the '@' classes at the beginning.

'@' classes can refer to each other (known as nesting), as shown in the original Canopycss.less file. Any nested '@' can be changed for direct css.
An example from the original file:

Here our table text will render as the same colour as the main text: #0066a2 (blue)

	@main-text: #0066a2;
	@table-text: @main-text;

However, I may want our table text to be a shade of red:

	@table-text: #CC0000;

This has now removed the connection between @table-text and the @main-text; making our table text red whilst keeping the main text blue. 


Nesting classes can make changing a color much quicker.

The example below shows several classes all with the same values:

	@inverse-text: #FFFFFF;
	@navbar-bg: #FFFFFF;
	@navbar-border: #ffffff #ffffff #0066a2 #ffffff;
	@footer-bg: #FFFFFF;

Further edits can be made easier my nesting these classes to make this:

	@inverse-text: #FFFFFF;
	@navbar-bg: @inverse-text;
	@navbar-border: @inverse-text @inverse-text #0066a2 @inverse-text;
	@footer-bg: @inverse-text;

This renders the navbar background, 3 sides of its border and the footer background the same color as the inverse text; changing the inverse-text color, changes all of these as well.

## Compiling

Once any edits have been completed, the less file needs to be converted into css. This can be done by manually compiling the less file into css, then linking to the css file; or automatically by relying on the host server to convert the file. 
Manually is recommended as this allows your website to load quicker and makes it more secure (this is because it doesn't have to access a remote folder and run a script which will slow the load time of your website); the programs mentioned below will also tell you if there are any errors in your less code.

For a more complete guide to less visit the official website [here](http://lesscss.org/ "lesscss.org")

#### WINDOWS: 
*	Download winless from [Winless](winless.org) and install.
*	Click 'Add folder' and add the folder that contains your less file
*	Your less file should be shown on the right hand side.
*	Ensure that your less file is checked.
*	The 'Minify' checkbox is optional.
*	Click 'Compile', this may take a couple of minutes.
*	The output css file, by default, will be called the same as the input less file and will be in the same folder.

#### MAC:
*	Download Simpless from [wearekiss](wearekiss.com/simpless) and install.
*	Drag and drop the folder that contains your less file into the program window
*	Click the compile button that is to the right of the file name, this may taker a couple of minutes.
*	The output css file, by default, will be called the same as the input less file and will be in the same folder.

This will create a css file which should be linked within the ```<head>``` of your webpage like:
	```html
	<link rel="stylesheet" href="file.css">
	```

This will work if your file structure looks like this:
```
page.html
file.css
```

Or if it's in a subfolder:
	```html
	<link rel="stylesheet" href="folder/file.css">
	```
This will work if your file structure looks like this:
```
page.html
folder/file.css
```

Should you want to rely on the server to convert your less file into css you need to link your less file in the ```<head>``` of your file.
```html
<link rel="stylesheet/less" type="text/css" href="file.less">
```
You will need to download the latest version of less [here](https://raw.github.com/less/less.js/v2.5.1/dist/less.min.js "less.js").
Create the link to the javascript file **__underneath__** the link to the less file.
```html
<script src="less.js" type="text/javascript"></script>
```

##Using Bootstrap

Being CSS bootstrap is called in the html using the classes.
	``` html
	<div class=".btn .btn-danger">
	</div>
	```
The example above would create a danger button on the page by calling the bootstrap CSS and replacing the colors with those we've specified in our custom file. A list of what each class does is available [here](http://getbootstrap.com/css/ "bootstrap").

#### Custom Classes

There are 2 custom classes: __.footer__ and __.footer-text__ that are not from bootstrap; these are still customizable, the same as the bootstrapped css. These classes can also be mixed with the bootstrap classes.