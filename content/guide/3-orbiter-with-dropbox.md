slug = with-dropbox


# How to Use Orbiter with Dropbox

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
