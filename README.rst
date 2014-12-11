Image Service API
+++++++++++++++++

This repository is now frozen-in-time and will not accept new patches.
To update Image API information, please submit patches to
http://git.openstack.org/cgit/openstack/glance-specs for a new API feature
and to http://git.openstack.org/cgit/openstack/api-site for implemented API
information.

It was the original holder for API information for the OpenStack
Image Service, also known as Glance. The Glance project provides
services for discovering, registering, and retrieving virtual machine
images. The Image Service provides a RESTful API that allows querying of VM
image metadata as well as retrieval of the actual image.

VM images made available through Glance can be stored in a variety of
locations from simple filesystems to object-storage systems like the
OpenStack Swift project.

Prerequisites
=============
`Apache Maven <http://maven.apache.org/>`_ must be installed to build the
documentation.

To install Maven 3 for Ubuntu 12.04 and later, and Debian wheezy and later::

    apt-get install maven

On Fedora 15 and later::

    yum install maven3

Building
========

The API is in the ``openstack-image-service-api`` directory.

To build a specific guide, look for a ``pom.xml`` file within a subdirectory,
then run the ``mvn`` command in that directory. For example::

    cd doc/image-api-v1
    mvn clean generate-sources

The generated PDF documentation file is::

    doc/image-api-v1/target/docbkx/webhelp/api/openstack-image-service/1.1/os-image-service-devguide-1.1.pdf

The root of the generated HTML documentation is::

    doc/image-api-v1/target/docbkx/webhelp/api/openstack-image-service/1.1/content/index.html


Testing of changes and building of the manual
=============================================

Install the python tox package and run ``tox`` from the top-level
directory to use the same tests that are done as part of our Jenkins
gating jobs.

If you like to run individual tests, run:

 * ``tox -e checkniceness`` - to run the niceness tests
 * ``tox -e checksyntax`` - to run syntax checks
 * ``tox -e checkdeletions`` - to check that no deleted files are referenced
 * ``tox -e checkbuild`` - to actually build the manual

tox will use the `openstack-doc-tools package
<https://github.com/openstack/openstack-doc-tools>`_ for execution of
these tests. openstack-doc-tools has a requirement on maven for the
build check.

Contributing
============

Our community welcomes all people interested in open source cloud
computing, and there are no formal membership requirements. The best
way to join the community is to talk with others online or at a meet up
and offer contributions through the code review process, the OpenStack
wiki, or blogs. We welcome all types of contributions, from blueprint
designs to documentation to testing to deployment scripts.

Installing
==========

Refer to http://docs.openstack.org/developer/glance/ to learn more
about installing an OpenStack Image Service server that can respond to
these API commands.
