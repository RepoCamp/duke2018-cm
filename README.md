Build scripts for UCLA's Hyrax 2 installation
=====================================================
### About ###
This is an ansible build script optimized for Ubuntu Linux 16.04 LTS (long term support). It will install:
* Hyrax pre-requisites
* solr on port 8983
* fedora on port 8080
* ffmpeg for video transcoding of video derivatives
* imagemagick, ghostscript, and other image libraries for creating image derivatives
* nrpe

### How to Build a Server ###

## To build a single box server

1. Make a new EC2 instance. There is an AMI already with ubuntu-16.04 and a separate
volume mounted for /opt (re-size this as necessary)

2. Add the hostname to the `hosts` file. Then:
  ```
  ansible-playbook single_box_build.yml --ask-vault-pass --extra-vars "host=YOUR_HOSTNAME"

  ```
