# bashx
Tools to fulfill small gaps that are encountered in everyday computing

##xsymlink

Xsymlink creates a symbolic link with an absolute path to any given file path with a relative or absolute path. The benefit of an absolute path while creating a symbolic link is that the link file can be moved to any location and it still maintains the correct path.

###Basic syntax:

A symbolic link will be created with the original file name.	

	xsymlink /etc/apache.conf .
This will create a symbolic link with an absolute path 
	
	./apache.conf  -> /etc/apache.conf

If the linked file points to another file, the link will be resolved before being linked again, i.e., if /etc/apache.conf points to /etc/apache/apache.conf, then the link will point as follows:

	./apache.conf -> /etc/apache/apache.conf
	

##downloader

Downloader is a bash script that uses curl to download a file with support to resume partial downloads automatically.

It is useful in Mac that does not have wget, but curl, which is a little complex to use.

###Basic syntax:
	
	downloader http://www.example.com/somefile.dmg
This will create a file *somefile.dmg* at the present directory.

An output file name can be provided as simply as this :

	downloader http://www.example.com/somefile.dmg somefile_x.dmg
Or :

	downloader http://www.example.com/somefile.dmg ~/Downloads/somefile_x.dmg

All the tools have been tested on Mac 10.10, but should work on all unix platforms.