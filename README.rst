Jenkins-lxd-pipeline
====================

This plugin is an attempt at making a simple step block for running things
inside a pristine LXD container instead of directly on the building node.

I wouldn't recommend depending on it, but it may work. This was just a
weekend experiment.

It launches the container, mounts the workspace dir, runs command and destroys
the container. As such, if you are checking UIDs may not be matching for 
the workspace folder. Also, it does require you to set LXD manually.


How do I use it?
----------------

Build, install and create a pipeline like

::
    node {
        lxd("ubuntu:xenial") {
            sh "hostname"
            sh "sudo apt install stuff"
            sh "do more stuff"
        }
    }


Isn't there already docker support?
-----------------------------------

Yes, and it probably works, but sometimes your app doesn't fit that model
because 
