Setting up a vagrant box
------------------------

To configure a local development virtual machine, you will need to have virtualbox and vagrant installed.

Note: You may need to change the IP configuration in the VagrantFile to a valid ip on the local network

For a local vagrant based production deploy, you will need to install ansible and then::

    $ vagrant up production

The basic box will be downloaded automatically and will be provisioned with GeoNode via ansible::

To ssh to the vagrant host::

    $ vagrant ssh production

You will need to do the following once after the first provisioning::

    $ vagrant ssh production
    $ source venvs/geonode/bin/activate
    $ django-admin.py createsuperuser --settings=geonode.settings
    Enter username and password

Visit this URL on your host machine, unless you changed the port forwarding in the Vagrant file::

    http://localhost:8080/geoserver/web

