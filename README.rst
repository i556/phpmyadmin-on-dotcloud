phpMyAdmin on DotCloud
======================

To deploy `phpMyAdmin <http://www.phpmyadmin.net/>`_ on DotCloud::

    git clone git://github.com/dotcloud/phpmyadmin-on-dotcloud
    dotcloud push phpmyadmin phpmyadmin-on-dotcloud

At the end of the build you can visit the url displayed and login into
phpMyAdmin. You will need the password for the root user of the MySQL
database to login, find it out with::

    dotcloud info phpmyadmin.db

You can include this code into your application to add a phpMyAdmin
service to your stack. This service discovers the MySQL servers in your
application by reading the `Environment File <http://docs.dotcloud.com/guides/environment/>`_.
If you use multiple MySQL servers, phpMyAdmin will display a drop down
list that lets you select which server you want to log into.

You may want to use an `approot <http://docs.dotcloud.com/guides/build-file/#specifying-the-root-directory-of-a-service>`_
and add a git/hg sub-repository from your main repository to use this
service easily and without polluting the hierarchy of your application.
