slug = overview


# Overview of Orbiter

### Get Involved

* 	Official website: [viaorbiter.com](http://viaorbiter.com)
* 	On GitHub: [github.com/kasparsd/orbiter](https://github.com/kasparsd/orbiter)

### Basic Functionality

1. 	All requests are forwarded to `index.php` which loads all plugins from the `plugins` folder and parses `config.ini` for things like document location and template files.

2. 	Orbiter parses request URI such as `http://example.com/about` and tries to find a coresponding source document in the document folder.

3. 	Orbiter reads the source document and passes it through a markup converter (such as Markdown, Latex or none).

4. 	Parsed document is sent to the templating engine (Mustache, Smarty, plain PHP, etc.) which returns HTML that is sent to the visitor.


## Using _Front Matter_

Front matter is a simple concept of adding information to your documents that you don't want to be included in the rendered content. 

Take a look at this sample document:

	slug = about
	time = August 12, 2012
	
	# About Orbiter
	
	Orbiter is a sim­ple and extend­able PHP tool for pub­lish­ing 
	beau­ti­ful web­sites out of Mark­down documents…
	
Front matter is everything at the top of the document seperated with a blank line from the rest of the document:

	slug = about
	time = August 12, 2012

Key values pairs are usually separated by either `:` or `=`. While several static site generators support [Yaml](http://www.yaml.org/) syntax for the front matter, Orbiter chooses to use standard [INI](http://en.wikipedia.org/wiki/INI_file) syntax by default (because it doesn't require any external libraries and is supported by PHP out of the box). 

The default front matter support is added by the *meta* plugin which can be removed or replaced to use Yaml syntax instead.




## Document Syncing


### How to Use Orbiter with Dropbox

[Dropbox](http://dropbox.com) offers a simple and easy to use file storage that is accessible from almost any device. This is probably why you're already using it for storing all your writing. With Dropbox you are able to publish and edit content of your Orbiter site from any location or device.

1. 	Install [Dropbox Linux client](https://www.dropbox.com/downloading?os=lnx) on your server. It doesn't matter where you store the files on the server, as long as they are readable by PHP.
	
	We are going to assume that the location of your Dropbox folder is located at `/home/kaspars/Dropbox` and your documents are located at `/home/kaspars/Dropbox/example.com`.

2. 	Modify `config.ini` to use `/home/kaspars/Dropbox/example.com` as the document folder:

		; Location of your documents
		docs = /home/kaspars/Dropbox/example.com
		
3. 	You can use Dropbox also for storing template files which are being passed through a rendering engine of your choice when Orbiter spits out the HTML. Edit `config.ini` to use `/home/kaspars/Dropbox/example.com/template` as the template folder:

		; Location of template files
		template = /home/kaspars/Dropbox/example.com/template
		
**Note**: you can can use relative or absolute folder path with or without trailing slashes for any of the configuration options, because Orbiter will take care of that automatically.



### How to Use Orbiter with Git
