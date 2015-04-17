####AppleScripts & Mac related Goodies

+ Osx.txt is a terminal script for setting some useful defaults on a new mac


######To Do:
+ Add (create) some applescripts
+ Workflows
+ settings / options



######Commands

show hidden files:
<pre>defaults write com.apple.finder AppleShowAllFiles -bool true</pre>
hide hidden files:
<pre>defaults write com.apple.finder AppleShowAllFiles -bool false</pre>
Turn off sleep:
<pre>sudo pmset sleep 0</pre>
Prevent idle sleep:
<pre>pmset noidle</pre>
Quick access in iTunes.
<pre>
Cmd + 1 = Music
Cmd + 2 = Movies
Cmd + 3 = TV Shows
Cmd + 4 = Podcasts
Cmd + 5 = iTunes U
Cmd + 6 = Books
Cmd + 7 = Apps
</pre>

On OS X to start/stop MySQL from the command line:
<pre>
sudo /usr/local/mysql/support-files/mysql.server start
</pre>

<pre>
sudo /usr/local/mysql/support-files/mysql.server stop
</pre>


######Apache
to start it
<pre>
sudo apachectl start
</pre>
to stop it
<pre>
sudo apachectl stop
</pre>
to restart it
<pre>
sudo apachectl restart
</pre>
To find the Apache version
<pre>
httpd -v
</pre>
The version installed in Mountain Lion is Apache/2.2.22

######To Setup localhost pointing to a folder (e.g. github)
<pre>cd /etc/apache2/users</pre>
<pre>sudo nano username.conf</pre>
<pre><Directory "/Users/username/Github/">
Options Indexes MultiViews
AllowOverride All
Order allow,deny
Allow from all
</Directory>
</pre>
<pre>sudo chmod 644 username.conf</pre>
<pre>sudo apachectl restart</pre>
<pre>sudo nano /etc/apache2/httpd.conf</pre>
1. page down twice
2. in the file there are two spots where it asks for document root, 
3. copy `/Users/username/Github/` here
4. exit
5. confirm save with Y
6. return

<pre>sudo apachectl restart</pre>

after upgrading to Yosemite there was a problem with httpd.conf
see http://encore254.blogspot.co.uk/2014/07/apache-issue-after-installing-os-x.html
for solution

######Clear list of open with apps when duped.
1. paste this into terminal
2. relaunch finder

<pre>
/System/Library/Frameworks/CoreServices.framework/Versions/A/Frameworks/LaunchServices.framework/Versions/A/Support/lsregister -kill -r -domain local -domain system -domain user  
</pre>

###### reset the DNS cache (Yosemite):

    sudo discoveryutil mdnsflushcache
    sudo discoveryutil udnsflushcaches

######Disable in-line attachment previews in Mail.app

    defaults write com.apple.mail DisableInlineAttachmentViewing -bool yes


###### Use a linebreak in Excel on Mac

    Sometimes you need a linebreak in an Excel spreadsheet cell, but when you hit return or 
    enter it always jumps you to a new cell. On Windows, you can just hit alt-return 
    (or maybe alt-enter; if one doesn’t work, try the other). On Mac, you’ll need to hit `control-option-return`.
    Took me a while to figure this out, and I figured it could be useful for others. Enjoy!
