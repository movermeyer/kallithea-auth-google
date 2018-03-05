kallithea-auth-google
=====================

Google auth plugin for Kallithea source code management system.

.. image:: https://api.travis-ci.org/paylogic/kallithea-auth-google.png
   :target: https://travis-ci.org/paylogic/kallithea-auth-google

.. image:: https://img.shields.io/pypi/v/kallithea-auth-google.svg
   :target: https://crate.io/packages/kallithea-auth-google/

.. image:: https://coveralls.io/repos/paylogic/kallithea-auth-google/badge.png?branch=master
   :target: https://coveralls.io/r/paylogic/kallithea-auth-google

.. image:: https://readthedocs.org/projects/kallithea-auth-google/badge/?version=latest
    :alt: Documentation Status
    :scale: 100%
    :target: https://readthedocs.org/projects/kallithea-auth-google/

Installation
============

::

    pip install kallithea-auth-google

In the Kallithea ``Authentication`` settings, add ``kallithea_auth_google.auth_google``, save, then set the settings.

In your config (``my.ini``):

::

    [pipeline:main]
    pipeline =
        google-auth
        kallithea

    ## google auth middleware
    [filter:google-auth]
    use = egg:kallithea-auth-google#google-auth

    [app:kallithea]
    use = egg:kallithea#main
    ## enable google auth middleware
    filter-with = google-auth

Note that after this change, for all kallithea paster commands you'll need to pass the section name explicitly:

::

    paster <command> my.ini --name=kallithea [options]

Contact
-------

If you have questions, bug reports, suggestions, etc. please create an issue on
the `GitHub project page <http://github.com/paylogic/kallithea-auth-google>`_.

License
-------

This software is licensed under the `MIT license <http://en.wikipedia.org/wiki/MIT_License>`_

See `License file <https://github.com/paylogic/kallithea-auth-google/blob/master/LICENSE.txt>`_


© 2015 Anatoly Bubenkov, Paylogic International and others.
