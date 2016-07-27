# centos6-curl-upgrade
this will let you upgrade your curl installation for centos6 so that curl error #35 is resolved.

First of all, the standard CentOS 6 version of curl/libcurl is recent enough that you won't need the old compat packages (libcurl7155 etc.).

install the repo

``rpm -Uvh http://www.city-fan.org/ftp/contrib/yum-repo/city-fan.org-release-1-13.rhel6.noarch.rpm``

and then edit the file 

`/etc/yum.repos.d/city-fan.org.repo`

to change the line `enabled=1` to `enabled=0` to prevent pulling in anything from there when you're not expecting it.

You can then see what would happen if you updated curl from my repo by doing: 

`yum --enablerepo=city-fan.org update curl`

At this point you can see what would be installed/removed (I'd expect it to install/update a few libraries as well as curl and libcurl, and not remove anything), and say "yes" or "no" to the update. The updated version of curl should work fine with everything in CentOS 6.

I did exactly this and after restarting Apache I'm pleased t
