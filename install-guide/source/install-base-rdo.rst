.. _install_rdo:

Install and configure for Red Hat Enterprise Linux and CentOS
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

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

1. Install the packages:

   .. code-block:: console

      # yum install
        openstack-ceilometer-collector openstack-ceilometer-notification \
        openstack-ceilometer-central python-ceilometerclient

.. include:: install-base-config-common.rst

Finalize installation
---------------------

#. Start the Telemetry services and configure them to start when the
   system boots:

   .. code-block:: console

      # systemctl enable openstack-ceilometer-notification.service \
        openstack-ceilometer-central.service \
        openstack-ceilometer-collector.service
      # systemctl start openstack-ceilometer-notification.service \
        openstack-ceilometer-central.service \
        openstack-ceilometer-collector.service
