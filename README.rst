face.com Python API client
==========================

.. image:: https://img.shields.io/badge/status-public%20archive-lightgrey.svg
   :alt: Public archive
   :target: https://github.com/chris-piekarski/python-face-client

.. image:: https://img.shields.io/badge/python-2.x-blue.svg
   :alt: Python 2.x
   :target: https://github.com/chris-piekarski/python-face-client

.. image:: https://img.shields.io/badge/release-1.2.3-informational.svg
   :alt: Release 1.2.3
   :target: https://github.com/chris-piekarski/python-face-client/blob/master/CHANGES

.. image:: https://img.shields.io/badge/license-BSD%203--Clause-blue.svg
   :alt: BSD 3-Clause license
   :target: https://github.com/chris-piekarski/python-face-client/blob/master/LICENSE

.. image:: https://img.shields.io/badge/service-face.com-retired-red.svg
   :alt: face.com retired
   :target: https://github.com/chris-piekarski/python-face-client/blob/master/README.rst#historical-references

.. code-block:: text

              .-"""""""-.
            .'  _   _    `.
           /   (o) (o)     \
          |       ^         |====.      POST /faces/detect
          |      '-'        | [] ||==>  POST /faces/recognize
          |   .-.___.-.     |====''     POST /faces/train
           \  \       /    /            POST /tags/save
            `. `-----'  .'              {image} -> {tags}
              `-.___.-'                 /api

**Archived project.** This repository is now a read-only snapshot of a Python client for the face.com API. It is preserved for historical reference and old integrations, not for active development.

The library wraps face.com endpoints such as ``faces_detect``, ``faces_recognize``, ``faces_train``, ``tags_save``, ``tags_get``, and account/auth helpers. The last documented release in ``CHANGES`` is **1.2.3**.

Why keep it around?
-------------------

* It preserves a complete Python wrapper for the old face.com REST API.
* It shows how the client handled signed requests, multipart uploads, and OAuth credentials.
* It includes a longer walkthrough in `EXAMPLE.rst <EXAMPLE.rst>`_.

Installation
------------

This project targets a Python 2-era environment and depends on ``poster >= 0.4``.

.. code-block:: bash

    pip install poster
    python setup.py install

Quick example
-------------

.. code-block:: python

    import face_client

    client = face_client.FaceClient('API_KEY', 'API_SECRET')
    response = client.faces_detect(urls='http://example.com/photo.jpg')

    print response

If you need user-scoped API calls, the client also supports Facebook and Twitter OAuth credentials:

.. code-block:: python

    client.set_facebook_oauth_credentials('FACEBOOK_USER_ID', 'FACEBOOK_OAUTH_TOKEN')
    client.set_twitter_oauth_credentials('OAUTH_USER', 'OAUTH_SECRET', 'OAUTH_TOKEN')

Historical references
---------------------

* `EXAMPLE.rst <EXAMPLE.rst>`_ has a longer walkthrough.
* `CHANGES <CHANGES>`_ contains release notes through version 1.2.3.
* Archived face.com references:

  * `API overview (Wayback) <https://web.archive.org/web/*/http://developers.face.com/docs/api/>`_
  * `Account page (Wayback) <https://web.archive.org/web/*/http://developers.face.com/account/>`_
  * `Recognition how-to (Wayback) <https://web.archive.org/web/*/http://developers.face.com/docs/recognition-howto/>`_

License
-------

BSD 3-Clause. See `LICENSE <LICENSE>`_.
