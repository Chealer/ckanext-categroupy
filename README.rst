=============
ckanext-categroupy
=============

.. Plugin to rename dataset groups

This plugin works around CKAN issue `Calling dataset groups "groups" (rather than e.g. "categories") is unclear/confusing (terminology) <https://github.com/ckan/ckan/issues/5331>`_.

So far, this only allows renaming to "categories".

------------
Requirements
------------

Supports CKAN 2.8.
Renaming was only done for French so far.


------------
Installation
------------

.. Add any additional install steps to the list below.
   For example installing any non-Python dependencies or adding any required
   config settings.

To install ckanext-categroupy:

1. Activate your CKAN virtual environment, for example::

     . /usr/lib/ckan/default/bin/activate

2. Install the ckanext-categroupy Python package into your virtual environment::

     pip install ckanext-categroupy

3. Add ``categroupy`` to the ``ckan.plugins`` setting in your CKAN
   config file (by default the config file is located at
   ``/etc/ckan/default/production.ini``).

4. Restart CKAN. For example if you've deployed CKAN with Apache on Ubuntu::

     sudo service apache2 reload


------------------------
Development
------------------------
TODO: Finish this section

To add a new language, use something like
   $ python setup.py init_catalog --locale YOUR_LANGUAGE
Replace YOUR_LANGUAGE with the two-letter ISO language code (e.g. es, de).
Then edit the generated i18n/YOUR_LANGUAGE/LC_MESSAGES/ckanext-categroupy.po. You may copy existing translations from your language's ckan.po.

To keep up with new CKAN releases, you could do something like:
   $ python setup.py update_catalog --locale fr -i ckanext/categroupy/i18n/ckan.pot -o ckanext/categroupy/i18n/fr/LC_MESSAGES/ckanext-categroupy.po

But please do not remove strings found in older CKAN versions as long as this plugin supports these versions.


Once a .po file is completed, compile the .mo file using:
   $ python setup.py compile_catalog

https://docs.ckan.org/en/2.8/contributing/i18n.html#create-a-po-file-for-your-language

------------------------
Development Installation
------------------------

To install ckanext-categroupy for development, activate your CKAN virtualenv and
do::

    git clone https://github.com/chealer/ckanext-categroupy.git
    cd ckanext-categroupy
    python setup.py develop
    pip install -r dev-requirements.txt
