Description
===========

Installs and configures Graphite http://graphite.wikidot.com/

Requirements
============

* Ubuntu 10.04 / Ubuntu 12.04
* Debian
* RHEL and derivatives (Centos, Amazon Linux, Oracle Linux, Scientific Linux)
* Fedora

Attributes
==========

* `node['graphite']['version']` - version of graphite to install (defaults to 0.9.10)
* `node['graphite']['password']` - password for graphite root user(default to `change_me` and is only used if encrypted databag isn't)
* `node['graphite']['url']` - url of the graphite server (defaults to graphite)
* `node['graphite']['url_aliases']` - array of url aliases (defaults to nil)
* `node['graphite']['listen_port']` - port to listen on (defaults to 80)
* `node['graphite']['base_dir']` = "/opt/graphite"
* `node['graphite']['doc_root']` = "/opt/graphite/webapp"
* `node['graphite']['storage_dir']` = "/opt/graphite/storage"
* `node['graphite']['django_root']` = "@DJANGO_ROOT@" - configurable path to your django installation
* `node['graphite']['timezone']` - Set the timezone for the graphite web interface, defaults to America/Los_Angeles

* `node['graphite']['whisper']['uri']` - download url for whisper
* `node['graphite']['whisper']['checksum']` - checksum of the whisper download

* `node['graphite']['graphite_web']['uri']` - download url for the graphite web ui
* `node['graphite']['graphite_web']['checksum']` - checksum for the graphite web ui download

* `node['graphite']['carbon']['uri']` - download url for carbon
* `node['graphite']['carbon']['checksum']` - checksum for the carbon download
* `node['graphite']['carbon']['line_receiver_interface']` - line interface IP (defaults to 0.0.0.0)
* `node['graphite']['carbon']['line_receiver_port']` - line interface port (defaults to 2003)
* `node['graphite']['carbon']['pickle_receiver_interface']` - pickle receiver IP (defaults to 0.0.0.0)
* `node['graphite']['carbon']['pickle_receiver_port']` - pickle receiver port (defaults to 2004)
* `node['graphite']['carbon']['cache_query_interface']` - cache query IP (defaults to 0.0.0.0)
* `node['graphite']['carbon']['cache_query_port']` - cache query port (defaults to 7002)
* `node['graphite']['carbon']['max_cache_size']` - max size of the carbon cache (defaults to "inf")
* `node['graphite']['carbon']['max_creates_per_second']` - max number of new metrics to create per second (defaults to "inf")
* `node['graphite']['carbon']['max_updates_per_second']` - max updates to carbon per second (defaults to "1000")
* `node['graphite']['carbon']['service_type']` - init service to use for carbon (defaults to runit)
* `node['graphite']['carbon']['log_whisper_updates']` - log updates to whisper (defaults to false)

* `node['graphite']['encrypted_data_bag']['name']` - The name of the encrypted data bag containing the default password for
the graphite "root" user.  If this attribute is set it will not use `node['graphite']['password']`.


Data Bags
=========

This cookbook optionally uses an encrypted data bag to store the graphite password.
If this data bag is not present the cookbook will use `node['graphite']['password']`
instead.  To use the encrypted data bag set `node['graphite']['encrypted_data_bag']['name']`
with the name of the data bag you wish to use.


Usage
=====

`recipe[graphite]` should build a stand-alone Graphite installation.

`recipe[graphite::ganglia]` integrates with Ganglia. You'll want at
least one monitor node (i.e. recipe[ganglia]) node to be running
to use it.
