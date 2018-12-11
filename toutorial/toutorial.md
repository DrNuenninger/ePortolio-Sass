# Sass tutorial

This tutorial should teach you the basics of the Sass syntax scss.
This tutorial assumes you have Sass installed, if you haven't install the command line option here: https://sass-lang.com/install

# 1. Basics

To compile your index.scss file into an index.css file use the following command in your command line:

    sass index.scss index.css

The syntax of this command is sass <source> <target> and you can choose any folder and file to compile from/to

Now you can start writing your code into the scss file. 
You can copy all you css code into the scss code if you want to start using sass in an exisiting projekt, 
the css syntax is an accepted syntax of sass!

For all features visit https://sass-lang.com/guide . The next section will cover the tasks given in the presentation.

# 2. Examples

## 2.1 Nesting

In the html file you want to style add the following code
	
	<h1> This is a normal headline </h1>
	
	<div class="container">
		<h1> This is a container specific headline </h1>
	</div>
	
We have a normal headline on the page and a container that could for example be some kind of widget.
This widget could be expanded with more basic html elements that all should look different than there counterparts on the rest of the website
We can use nesting to write all these special style rules inside of the div without repeating ourselfs constantly.

To give the headline inside the container a different color add this to your style.scss file:

	.container {
		h1 {
			color: #008000;
		}
	}

This code will result in the following css code:

	.container h1 {
		color: #008000;
	}	

## 2.2 Mixin for rotation

You can use Mixins to reuse a whole block of style rules multiple times and with different parameters , saving a lot of code.

in your html file add the following code:

	<p id="rotate1"> I am rotated by 90 degrees </p>
	<p id="rotate2"> I am rotated by 180 degrees </p>
	
in you style.scss add the following code:

	@mixin rotation($degrees) {
		-webkit-transform: $degrees;
		-ms-transform: $degrees;
		transform: $degrees;
	}
	
	#rotate1 {
		@include rotation(90deg);
	}
	
	#rotate2 {
		@include rotation(180deg);
	}
	
This code will result in the following css:

	#rotate1 {
		-webkit-transform: 90deg;
		-ms-transform: 90deg;
		transform: 90deg;
	}
	
	#rotate2	{
		-webkit-transform: 180deg;
		-ms-transform: 180deg;
		transform: 180deg;
	}
	