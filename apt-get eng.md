Title: How to use apt-get
Date: 2013-07-01 11:12

#How to use apt-get

apt-get's commands are very easy and intuitive.

Its commands follow this structure:
<pre>
 # apt-get [options] command
 # apt-get [options] install package [package ...]
</pre>
The command line may be a variation of the following basic types:

apt-get update

Updates apt-get's local database with server's pkglist's files.
apt-get check

verifies system's integrity using apt
apt-get install some-package

installs some new package, automatically resolving and downloading dependent packages
apt-get upgrade

checks for outdated packages in the system and automatically upgrades them
apt-get dist-upgrade

    same as apt-get upgrade, but installs all base packages and tries to upgrade everything, installing new packages if needed
apt-get remove some-package

    removes the some-package package and all other packages that depends on it
apt-get clean

    removes the downloaded packages from the cache directory (/var/cache/apt/archives/), freeing some disk space at your system ;-)

#2. What is apt?

apt is a Debian tool used to manage packages in such a way that when the user asks for a package to be installed the system also installs (or upgrades) all the necessary packages to make the package work.

The apt we're documenting here is the version that works with rpm files.

To use apt-get and its friends, you'll have to install the package apt. If your GNU/Linux vendor supports apt, you'll find it at his FTP site.



Installing and configuring your system for apt

To use apt you'll have to do the following procedure:

    become root user

    install the apt package with either rpm -ihv or rpm -Uhv. This package can be obtained from your vendor's site (if he supports apt or maybe even from your distribution CD).

    run apt-get update to download the package's database from the default server[1]

    run apt-get check, so that apt can verify if your box is OK and all package's dependencies are correctly satisfied

        Note: If your system isn't seriously broken, you'll be able to fix it with apt-get -f install. If its broken, you'll have to fix these dependencies by hand (I mean, using the rpm command) before start using apt.

    If everything goes fine, you'll be able to use apt-get's and other apt's commands listed later in this document.

Notes
[1] 	

You'll see how to change this server for others later on this document

#3. How to use apt-cache

Besides apt-get there's also apt-cache.

apt-cache is a command to manipulate and obtain information from the packages at apt's cache.

This command is not to be used by common users. You'll like it if you're developing something to be used with apt.

apt-cache add

    Adds a package file to the source cache.
apt-cache gencaches

    Builds both the package and source cache
apt-cache showpkg

    Show some general information for a single package
apt-cache stats

    Show some basic statistics
apt-cache dump

    Show the entire file in a terse form
apt-cache dumpavail

    Print an available file to stdout
apt-cache unmet

    Show unmet dependencies
apt-cache check

    Check the cache a bit
apt-cache search

    Search the package list for a regex pattern
apt-cache show

    Show a readable record for the package
apt-cache depends

    Show raw dependency information for a package
apt-cache pkgnames

    List the names of all packages
apt-cache dotty

    Generate package graphs for GraphVis



#4. Using apt-cdrom and apt-config

apt-cdrom is a simple command to add CDROMs to apt's sources.list file. Its syntax is a variation on this basic command line:

    # apt-cdrom add

apt-cdrom uses information from your /etc/fstab if you don't specify where's the CDROM drive.

apt-config is a tool to read apt's apt.conf file and is very useful to dump it to screen. Its syntax is a variation of these basic options:

apt-config [options] shell

    Shell mode
apt-config [options] dump

    Show the configuration options in the screen



#5. Creating a repository

To setup an apt-get repository, you'll need to have an HTTP or FTP server with the standard distribution package tree and its base directory. The top of the directory tree must be in /etc/apt/sources.list.

    Note: Other methods besides HTTP and FTP are still untested.

You'll have to make sure that the files available at this server can be accessed. You can use any browser or web tool and try downloading a file for testing purposes. Doing this test will eliminate server's misconfiguration problems now.

You'll need the following directory structure:

main directory

    it will contain license files, directories with source packages, directories with binary packages, etc. Its exactly like the root directory on a CD.

    vendor directory

        this is a holder for other directories that will have the binary packages.

        repositories

            these are the directories that, inside the vendor directory, will contain the packages. Its name must start with RPMS., i.e., the word RPMS in upper case followed by a dot. After the dot you'll put the name that you want to associate with these files. One example is beta or official for, respectively, the beta and official versions of your distribution.
        a base directory

            this directory will have the pkglist files with packages names and dependencies.

With all these directories you'll be able to configure your sources.list file to access the repositories you've created.

Example 1. /etc/apt/sources.list

    rpm http://joes.box.com/stuff 5.1/conectiva cds security

With configuration shown at Example 1, the repository tree needs to be something like what's described at Example 2.

Example 2. Server tree

    /home/httpd/stuff
    /home/httpd/stuff/5.1
    (1)
    /home/httpd/stuff/5.1/lots-of-README-and-LICENSE-files
    (2)
    /home/httpd/stuff/5.1/SRPMS
    /home/httpd/stuff/5.1/conectiva
    /home/httpd/stuff/5.1/conectiva/base
    /home/httpd/stuff/5.1/conectiva/base/hdlist.cds
    /home/httpd/stuff/5.1/conectiva/base/hdlist.security
    /home/httpd/stuff/5.1/conectiva/base/pkglist.cds.bz2
    /home/httpd/stuff/5.1/conectiva/base/pkglist.security.bz2
    (3)
    /home/httpd/stuff/5.1/conectiva/RPMS.cds/
    (4)
    /home/httpd/stuff/5.1/conectiva/RPMS.security/
    (5)
    /home/httpd/stuff/5.1/conectiva/etc-etc
- (1)
    This is the top of the repository tree
- (2)
    This is the top for a specific version, 5.1 here.
- (3)
    We've generated this control file...
- (4)
    And also this one.
- (5)
    This includes the packages available at Conectiva's CDs
- (6)
    This includes the packages that have security fixes

<p>Note: The names cds and security are arbitrary. In practice you can call them the way you want. The only restriction is that they need to be a logical or physical division of the repository tree.</p>

#6. genbasedir

Every repository needs to have a package index file which will contain the list of every package available, their descriptions and dependencies. This file is named pkglist and is bzip2 compressed.

To generate the pkglist files you need to go to the base directory in the repository and run genbasedir. It will create the bzip2 compressed files.

Example 3. genbasedir's syntax

    
    # genbasedir [-s | --sign] [--topdir=dir] distribution component [component ...]

Where, for each element of Example 3 we have:

-s or -- --sign

<p>using this parameter you'll be able to sign your pkglist files. This will prompt you for your gpg passphrase and will create a file named hashfile.gpg at the same directory.
-- --topdir</p>
<p>
this parameter specifies the top directory where your repository is found. It's the corresponding directory to the URL specified at your sources.list file.
distribution
</p>
   <p> is the name of your GNU/Linux distribution. It's usually your vendor's name with some version or other identifier appended to it. It's also at your sources.list file.
component(s)
</p>
   <p> this (or these) are the places where your rpm files are located. You'll have to put here the same suffix you've used before or things won't work...
</p>
Then, for Example 2 we'd have:

    
    # genbasedir --topdir=/home/httpd/stuff 5.1/conectiva cds 
    # genbasedir --topdir=/home/httpd/stuff 5.1/conectiva security



#7. apt files

###7.1. sources.list

The sources.list file, found at /etc/apt directory, describes the sources that apt will use to know where to search for package information.

This file's syntax is as follow:

    TYPE URI ARGS

Currently TYPE may be deb or rpm. We'll describe just the rpm type.
#7.2. The rpm type

The rpm type is a typical RPM distribution with its set of packages. As there is the possibility of having more than one line pointing to apt repositories, one might want to put the fastest repository as the first line.

    rpm uri distribution component [component ...]

The uri points to the apt repository server.

distribution can specify an exact path. If you use this option, you'll need to ommit the component part and make it end in a slash.

apt will sort uri for its internal use, but it's very important that these lines are in order from your most preferred to least preferred package source (e.g. from the fastest to the lowest).

#7.3. uri specification

You can use several sources for a uri.
Warning

Just remember that HTTP and FTP are the only tested methods and for safety, I'll just be documenting those here. As more methods become supported, they'll be documented here as well.

ftp

    This method specifies an FTP connection to the repository server.

        ftp://ftp.conectiva.com/repository

http

    This method specifies that you'll do a HTTP connection to the repository server.

        http://www.conectiva.com/repository



#8. Maintaining your apt repository
<p>
After you've setup your repository, you'll want to make it useful for your users. What am I talking about??? Maintenance! You'll have to keep your files updated and you'll have to keep the indices updated.
</p>
<p>An apt repository maintenance is very very very simple. You just update the packages in there and then regenerate the indices with the genpkglist command.
</p>
<p>
<strong>Tip</strong>: First test your new packages before making them publicly available; copy them to the specific directory where they belong to and then remove the old package. From now on, until you regenerate your pkglist file, you and your users won't be able to use this package. Upgrade the indices as soon as possible to get things back to work.
</p>
    I was thinking but I don't really know what's better: copy everything to the directory they belong to, regenerate indices, remove the old packages, regenerate indices; or the copy, delete, (no file to download) regenerate indices approach (everything back to normal)... I thinks that's up to you and to how used is your apt repository.




#9. Using GPG signatures

apt has gpg support, so you may want to use this to make sure that you're getting genuine packages (or, if you're a GNU/Linux vendor, you want to provide this benefit to your users) from your vendor.

apt has no support for PGP, so don't waste your time trying to use it.

The sources.list syntax has to be changed for this to work.

    rpm [gpg-id] uri distribution component [component ...]

The gpg-id[1] is the one used by the vendor to sign its packages. In fact it is a pointer to the last part of the vendor's key fingerprint available at the vendors.list file.

Example 4. vendors.list

    # Trusted Package Provider List
    #
    # This file contains the list of package providers (vendors or individuals)
    # from whom packages you trust. 
    #  
    cncbr   E368DDD099807190 "Conectiva S.A. <security@conectiva.com.br>"

After doing this change, I mean, introducing the [gpg-id] field, you'll have to make sure that you have your vendor's public key in your gpg keyring.

Example 5. Importing gpg keys

    
    # gpg --import file-with-key

At Example 5, file-with-key is (you'll never guess that) a file with your vendor's public gpg key.

This command will import your vendor's key at the root keyring (since only root can install, removes or manipulate packages, it would make no sense to import this key on any other user's keyring).

Notes
[1] 	<strong>The brackets at the source.list file must be there.</strong>


#10. How does the archives directory works?

Once you request apt to install some package or do an upgrade (either upgrade or dist-upgrade), it will download the necessary packages to the /var/cache/apt/archives/partial/ and, after verifying its MD5 hash and size, it will them move these packages to /var/cache/apt/archives/.

You can assume that every file in the archives/ directory has been verified. This isn't true for archives/partial/ files.

