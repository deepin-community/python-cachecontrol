..
  SPDX-FileCopyrightText: SPDX-FileCopyrightText: 2015 Eric Larson

  SPDX-License-Identifier: Apache-2.0

==============
 CacheControl
==============

.. image:: https://img.shields.io/pypi/v/cachecontrol.svg
    :target: https://pypi.python.org/pypi/cachecontrol
    :alt: Latest Version

.. image:: https://github.com/psf/cachecontrol/actions/workflows/tests.yml/badge.svg
  :target: https://github.com/psf/cachecontrol/actions/workflows/tests.yml

CacheControl is a port of the caching algorithms in httplib2_ for use with
requests_ session object.

It was written because httplib2's better support for caching is often
mitigated by its lack of thread safety. The same is true of requests in
terms of caching.


Quickstart
==========

.. code-block:: python

  import requests

  from cachecontrol import CacheControl


  sess = requests.session()
  cached_sess = CacheControl(sess)

  response = cached_sess.get('http://google.com')

If the URL contains any caching based headers, it will cache the
result in a simple dictionary.

For more info, check out the docs_

.. _docs: http://cachecontrol.readthedocs.org/en/latest/
.. _httplib2: https://github.com/httplib2/httplib2
.. _requests: http://docs.python-requests.org/
