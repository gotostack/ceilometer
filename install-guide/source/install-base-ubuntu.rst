.. _install_ubuntu:

Install and configure for Ubuntu
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

This section describes how to install and configure the
Telemetry service, code-named ceilometer, on the controller node.

This section assumes that you already have a working OpenStack
environment with at least the following components installed:
Compute, Image Service, Identity.

Prerequisites
-------------

Before you install and configure the Telemetry service, you must
configure a target to send metering data to. The recommended endpoint
is Gnocchi_. To enable Gnocchi, please see its install guide.

.. _Gnocchi: http://gnocchi.xyz
.. include:: install-base-prereq-common.rst

Install and configure components
--------------------------------

#. Install the packages:

   .. code-block:: console

      # apt-get install ceilometer-collector \
        ceilometer-agent-central ceilometer-agent-notification \
        python-ceilometerclient

.. include:: install-base-config-common.rst

Finalize installation
---------------------

#. Restart the Telemetry services:

   .. code-block:: console

      # service ceilometer-agent-central restart
      # service ceilometer-agent-notification restart
      # service ceilometer-collector restart
