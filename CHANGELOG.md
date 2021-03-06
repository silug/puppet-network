# 2016-09-27 Release 0.6.1

  * Modulesync with latest Vox Pupuli defaults
  * Make fact confinement ruby 1.8 compatible
  * Fix name of filemapper dependency


# 2016-09-15 Release 0.6.0

  * Drop support for Ruby 1.8.7
  * (#69) debian default route should now be named 'default', same as redhat (backwards incompatible change)
  * Cleanup of README.md
  * Soft fail on missing ipaddress gem
  * Modulesync with latest Vox Pupuli defaults
  * Don't write absent to redhat route files and test for this
  * Routes: add ability to parse IPv6 addresses
  * Add spec tests for redhat and debian ipv6 routes
  * fix "absent" options
  * Fix a typo in the HEADER of generated files
  * Completely rewritten vlan logic
  * Add a `network` class to install dependencies
  * Fix `with_env` support, and trust in PATH being correct
  * Support for MTU on bonds


# 2016-03-14 Release 0.5.0

  * add bonding support through network::bond
  * add camptocamp/kmod as a dependency
  * add puppetlabs/stdlib as a dependency
  * reorganize modulefile deps
  * correct Debian package name to ifenslave-2.6
  * (#29) add of refactored network_namespaced facts
  * (#34) Update ifenslave package in specs
  * added comments to express what the facts should provide
  * Network module responds poorly to ifcfg-NNN.bak files
  * (#36) Better validation around ifcfg script names
  * switch to patched version of rspec-puppet
  * fix file expansion problem with PE
  * allow the network_config redhat provider to parse ifcfg-ethX.X format files
  * add mtu parameter to network_config type
  * convert vlan_range_regex to constant
  * ensure that network_config redhat provider flushed files have a consistent file mode
  * add link to debian package ifupdown-extra
  * improve error messages for debian routes provider
  * (#54) Allow ip address netmasks for network_route
  * prevent restarting the network every time puppet runs b/c of default netmask
  * omit lacp_rate for non 802.3ad mode
  * remove network_public_ip fact
  * indent sub-entries to the in interfaces
  * do not print properies if they are absent
  * add mode property to network_config
  * add vlan mode property support
  * use ifcfg script name in case DEVICE parameter is not specified on redhat network_config provider
  * set default iface mode to :raw on Debian
  * generate Debian auto/allow-hotplug only if not empty
  * (#104) fix a typo in the redhat provider for network_route
  * (#116) fix a vlan matching bug
  * allow an empty hash for options
  * ignore new Debian Jessie's features
  * (#115) guard againt :absent provider.options in redhat
  * (#143) make :absent attributes not get written to redhat files
  * fix network facts on gentoo

Thanks for their contributions to this release go to:

  * Adrien Thebo
  * Ahmed Elsabbahy
  * Daniele Sluijters
  * David Schmitt
  * Davide Ferrari
  * Derek Higgins
  * Drew Blessing
  * Eric Sakowski
  * Ewoud Kohl van Wijngaarden
  * Felix Frank
  * Felix Gilcher
  * Igor Galić
  * Jasper Lievisse Adriaanse
  * Jon Skarpeteig
  * Jordi Clariana
  * Joseph Yaworski
  * Joshua Hoblitt
  * Julian
  * Nan Liu
  * Robin H. Johnson
  * Romanos Skiadas
  * Spencer Krum
  * Stefano Zilli
  * Steffen Zieger
  * Vlastimil Holer
  * Wolf Noble

Special thanks to Adrien Thebo for donating this module to the Puppet Community.

2013-05-21

This is a backwards compatible feature and bugfix release

  * New defined type: network::bond, with Debian and Redhat backends
  * New facts for current network configuration:
    * network_public_ip
    * network_nexthop_ip
    * network_primary_interface
    * network_primary_ip
  * (network-#36) More strict selection of redhat network interface scripts

Thanks to Eric Sakowski, Wolf Noble, Vlastimil Holer, and Dan Fruehauf for
their contributions to this release.

v0.4.1
-----

2013-08-17

This is a backwards compatible bugfix release

  * Update Modulefile dependency for adrien/boolean to >= 1.0.0

v0.4.0
-----

2013-03-22

This is a backwards compatible feature release

  * New provider for network_route: redhat
  * Module built with sane umask (0022); permissions should just work

Thanks to Eric Sakowski for implementing the redhat network_route provider

v0.3.0
-----

2013-01-23

This is a backwards compatible bugfix and maintenance release.

  * New type: network_route
  * Debian provider for network_route
  * Better behavior of boolean properties in network_config
  * (network-#18) Support multiple options for debian network_config

Build status is now available at https://travis-ci.org/adrienthebo/puppet-network

Thanks:

  * Patrick Otto for the network_route type and Debian provider
  * Robert Starmer for testing, debugging, and documentation
  * Wolf Noble for insight and encouragement all along the way

v0.2.0
-----

2012-12-30

This is a backwards compatible bugfix and maintenance release.

  * (network-#15) Add hotpluggable feature for redhat
  * (network-#13) normalize boolean values
  * (network-#13) patch inet flapping behavior in redhat
  * (network-#1) Add :reconfigurable parameter
  * (network-#2) Add :provider_options feature

v0.1.1
-----

2012-12-06

This is a backwards compatible metadata fix and maintenance update.

  * (network-#14) Fix specs for Ruby 1.9.3
  * Add Gemfile
  * (maint) DRY up specs
  * Restrict filemapper dependency to 1.0.x. 1.1.x will go into RC shortly
  and the puppet module tool will install prereleases so for the sake of
  safety I'm restricting the dependency here.

v0.1.0
-----

2012-12-04

This is a backwards incompatible bugfix and feature release. It might work
work with un-updated code but no guarantees are made.

  * Added a `hotplug` feature to the network_config type
  * Implemented the `hotplug` feature for osfamily => Debian
  * Added an alias from none to static for redhat users

v0.0.4
-----

This is a backwards compatible maintenance release.

  * Munge onboot and method parameters for redhat provider.
  * Automatically quote and unquote redhat values as needed

v0.0.3
-----

This is a backwards compatible maintenance release.

  * Use non-greedy regex when matching redhat keys
  * Update redhat provider to respect current API implementation of filemapper
  * Add test coverage to redhat provider

v0.0.2
-----

This is a backwards compatible maintenance release.

  * Remove bugs from interfaces provider stemming from old isomorphism behavior.

v0.0.1
-----

Initial release.
