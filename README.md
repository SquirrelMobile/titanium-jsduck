titanium-jsduck
===============

NPM Package for initializing JSDuck Documentation for Appcelerator Titanium Mobile Application Projects

#### Description
Documentation of your software projects is a critical phase of the software delivery process.  This package allows you to include JSDuck commenting in your .js files of an Alloy Project.  Everytime the project is compiled, your documentation will be updated.  

The project includes two commands currently.  The first is to automate the installation of the post:compile hook and source files for the documentation.  The second command allows a quick method to preview the documentation within a web browser.

## Requirements

It is a requirement to have **jsduck** installed already.  If you do not have it installed, you can do so via the following:

	$ gem install jsduck
	
For more documentation about JSDuck, please visit the project: https://github.com/senchalabs/jsduck

## Installing the NPM package

From NPM: 

	$ npm install titanium-jsduck -g
	
From Git:
	
	$ npm install git://github.com/jamilhassanspain/titanium-jsduck.git

From source:
		
	$ git clone git://github.com/jamilhassanspain/titanium-jsduck.git
	$ cd titanium-jsduck
	$ npm install -g
## Activating Documentation for your project

In order to use this NPM package, you must first be in the root of your Titanium Mobile Project. Either open a terminal window or use the Terminal inside Titanium Studio and run the following command:


	titanium-jsduck install
	
This will install the following items in your Titanium Mobile Project:

* a docs/ folder in the root of your project
* alloy.jmk inside your app/ folder

If an alloy.jmk already exists, it will back it up to be alloy.jmk.txt and install a fresh alloy.jmk with the post:compile command to run.  If your docs folder already exists in the remote chance you are trying to reinstall titanium-jsduck in a mobile project, the docs folder will not be automatically overwritten.  To force the docs folder to be overwritten, please use this command.

	titanium-jsduck install force

## Viewing the Documentation

After your project has been compiled, you can now view the updated documentation. Instead of manually browsing to your Titanium Project in the finder, use this command:

	$ titanium-jsduck open
	
This will open your documentation within the system default Web Browser. The following **open** command will also accept browser name as optional parameter.  

	$ titanium-jsduck open firefox
	$ titanium-jsduck open chrome
	$ titanium-jsduck open opera
	
If you have a browser preference other than Safari, you can open it via Google Chrome, Firefox or Opera. This command will detect if these apps exist within the /Applications folder first.  If they do not exist, it will default to Safari since that is sure to be available on everyone's Mac OS X install.  

## Generating Documentation 
There may be an instance where you want to generate documentation without actually re-compiling the Titanium Project.  For this corner case, the following command is available as well:
	
	$ titanium-jsduck run

## Documenting Files
First time using JSDuck for documentation? Here is a quick preview on how to document your controller.  This just tips the iceberg for the real capabilities of what you can do.

	/**
	* this is the main index.js file
	* @class Index
	*/
	
	/**
	* This is the doClick Method
	* @method doClick
	* 
	*/
	function doClick(e) {
    alert($.label.text);
	};

	$.index.open();
	

	
	
I truly recommend browsing the Senchalabs Wiki for JSDuck at the following link:  https://github.com/senchalabs/jsduck/wiki/Guide. for more information.


## Changelog

| Version | Notes |
| ------- | -----:|
| 1.0.0      | First release with basic functionality  |
| 1.1.0      | Minor updates  |
| 1.2.3		 | Added support to detect if jsduck is already installed, restricted operation of titanium-jsduck to be only for mac operating system |
| 1.2.5		 | Fixed issue to make documentation open with default browser + allowing user to force a browser to use, if docs directory exists, we will not forceDelete ( instead use the titanium-jsduck install force command to forceDelete of the docs directory on reinstall into a mobile project), improved detection for proper installation of jsduck ruby project |
| 1.2.6      | Adding support for Opera Browser  |
 

## License

Copyright 2013 Jamil Hassan Spain

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License. You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.