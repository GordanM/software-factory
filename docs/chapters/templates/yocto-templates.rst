Yocto Project integration
=========================

This section describe how to include a shared library or platform service in the target image using the `Yocto Project`_. A key part of this is an open source build system, based around the OpenEmbedded architecture, that enables developers to create their own Linux distribution specific to their environment. BitBake_ is the build tool used in this setup:

    BitBake executes tasks according to provided metadata that builds up the tasks. Metadata is stored in recipe (.bb) and related recipe "append" (.bbappend) files, configuration (.conf) and underlying include (.inc) files, and in class (.bbclass) files. The metadata provides BitBake with instructions on what tasks to run and the dependencies between those tasks.

The developed software components are added to the project through a BitBake recipe file that, as mentioned above, stores the component metadata. Guidelines on how to write BitBake recipes can be found in the `Yocto reference manual`_ and the reference structure is described in the `OpenEmbedded style guide`_.

Template recipes
----------------

TBD

Target image integration
------------------------

To include the template service in the target image, the following line has to be added to the target image BitBake recipe:

.. code-block:: bash

    IMAGE_INSTALL += "template-service"

Observe that there is no need to add the template library explicitly. The template library will be included implicitly because the template service depends on it.

.. _Yocto Project: https://www.yoctoproject.org/
.. _BitBake: https://www.yoctoproject.org/docs/current/bitbake-user-manual/bitbake-user-manual.html
.. _Yocto reference manual: http://www.yoctoproject.org/docs/current/ref-manual/ref-manual.html
.. _OpenEmbedded style guide: http://www.openembedded.org/wiki/Styleguide
