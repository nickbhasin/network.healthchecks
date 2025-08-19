=============================================
Network Health Check Collection Release Notes
=============================================

.. contents:: Topics

v2.0.0
======

Release Summary
---------------

With this release, the minimum required version of `ansible.netcommon` for this collection is `>=8.1.0`. The last version known to be compatible with `ansible-core<=2.18.x` is ansible.netcommon `v8.0.1` and network.healthchecks `v1.0.0`.

Major Changes
-------------

- Bumping `dependencies` of ansible.netcommon to `>=8.1.0`, since previous versions of the dependency had compatibility issues with `ansible-core>=2.19`.

Minor Changes
-------------

- Add a new role to check IP reachability and ensure proper tests for the same.

v1.0.0
======

Bugfixes
--------

- Adds the changelog fragments.
- Fixes the lint and sanity errors.
- Moves the templates to the same directory as tasks and other files.

New Plugins
-----------

Filter
~~~~~~

- filesystem_health_check_view - Generate the filtered filesystem health check dict based on the provided target.
- health_check_view - Generate the filtered health check dict based on the provided target.
- interfaces_health_check_view - Generate the filtered health check dict based on the provided target.
- ospf_health_check_view - Generate the filtered health check dict based on the provided target.
