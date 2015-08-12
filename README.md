# Welcome

This project is to create a branded bootstrap theme for Canopy products, with the requirement to be easily customizable for a customer.

This project uses less to make rebranding of the template easier. Less is a pre-compiler for the CSS styling sheet; this allows CSS to be used with greater flexability. This is done by compiling a Less file into CSS, which is then linked in the <head> of the html pages.

This template builds on Twitter Bootstrap; a framework that allows for easier creation of responsive websites.

## Included Files

The **lessout-v2.css** file changes twitter bootstrap to match the Canopy theme and should be used in addition to the normal twitter bootstrap files; these are being recovered remotely for this project.

**example html.html**  shows the customized elements in this template including the header, footer, buttons and tables.
login.html shows a simple fully html canopy branded login page.

Key sections have been templated ready for content.
These include:
*	main.html - a minimal header/footer template
*	contact.html - a simple template for a company contact information
*	contact-test.html - main+contact
*	header.html - header template only
*	footer.html - footer template only


## Rebranding

To customize this for your site, follow the instructions below. The initial.css file should not be linked to in any html.

Your first edit should be the color scheme.
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


There are 2 custom classes: .footer and .footer-text that are not from bootstrap; these are still customizable, the same as the bootstrapped css. 

## Compiling

Once any edits have been completed, the less file needs to be converted into css. This can be done manually or automatically. 
Manually is recommended as this allows your website to load quicker and makes it more secure; the programs mentioned below will also tell you if there are any errors in your less code.

WINDOWS: 
	Download winless from winless.org
	Click 'Add folder', your less file should be shown on the right hand side.
	Ensure that your less file is checked.
	The 'Minify' checkbox is optional.
	Click 'Compile', this may take a couple of minutes.
	The output css file, by default, will be called the same as the input less file and will be in the same folder.

MAC:
	Download Simpless from wearekiss.com/simpless
	Drag and drop the containing folder into the program window
	Click the compile button that is to the right of the file name, this may taker a couple of minutes.
	The output css file, by default, will be called the same as the input less file and will be in the same folder.

This will create a css file which should be linked to your webpage like:
	<link rel="stylesheet" href="file.css">
Or if it's in a subfolder:
	<link rel="stylesheet" href="folder/file.css">

## Using Bootstrap

A good guide on how to use twitter bootstrap and the included classes is here: http://getbootstrap.com/css/

Original style taken from: https://bootswatch.com/cosmo/ and used as a template.