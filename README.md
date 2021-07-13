# Ansible role for provisioning a LexFloatServer instance

An Ansible Role that installs [LexFloatServer](https://docs.cryptlex.com/floating-licenses/on-premise-floating-licenses/lexfloatserver) on a systemd based linux distribution.

## Role Variables

Available variables are listed below, along with default values:

    lexactivator_licence_key: SET_ME

The licence key to activate LexFloatServer

    lexactivator_product_dat: SET_ME

The contents of the product.dat file

    lexfloatserver_cryptlex_host: SET_ME

The cryptlex host to connect to

    lexfloatserver_api_key: unset

The api key to use for accessing the REST API of the server

    lexfloatserver_admins: unset

Map of users with access to the web admin interface: check the [LexFloatServer](https://docs.cryptlex.com/floating-licenses/on-premise-floating-licenses/lexfloatserver) documentation for information

    lexfloatserver_version: 4.6.1

Version of LexFloatServer to use

    lexfloatserver_root_directory: /srv/LexFloatServer

Where the server is installed

    lexfloatserver_configuration_directory: /etc/LexFloatServer

Where configuration files are stored

    lexfloatserver_port: 5000

The port LexFloatServer will listen to

    lexfloatserver_leaseduration: 900

Determines how long a license lease should last. The time is in seconds.
15 minutes (900 seconds) is recommended. 30 seconds is minimum allowed time.

    lexfloatserver_loglevel: 3

The amount of information to be logged in the file. These are the possible levels:

-   "0" - No log
-   "1" - Only Errors
-   "2" - Errors and Warnings
-   "3" - Errors, Warnings and other info regarding when leases are created, removed, expired etc.

    lexfloatserver_allowedclockoffset: 60

Allows for a time lag (in secs) between LexFloatServer and client machines.

    lexfloatserver_blockedips:

Blocked IP addresses

    lexfloatserver_distribution_source_url: "https://dl.cryptlex.com/downloads/lexfloatserver/v{{ lexfloatserver_version }}/LexFloatServer-Linux.zip"

The url from where to fetch the LexFloatServer-Linux.zip file

## Dependencies

This role has no other dependencies

## Example Playbook

Please note: the values below are not valid.

    - hosts: all
      gather_facts: true
      roles:
        - lexfloatserver
      vars:
        lexfloatserver_cryptlex_host: https://license-api.server
        lexactivator_licence_key: 904434-6A392F-4012B6-4163ED-1C7AFF-1F5712
        lexactivator_product_dat: >
          Mzk3MTBBODQ0NDIzMjdGMThDNTMzNDNGMTYxQUVEQjc=.Y6lKPotL8HJh8dkhrOY4ENMLAvAC10
          jfF9YfXRcXaKiqCpIUmAcXXTtCxSDgn6tuVyjuJUR+WlmIadspgv21HjJpbiRdhI6FfJdLTelL9
          9ZOn2wuFBSLDzxeOjTY9ka9Vtp3CH09vYA1HhfShg6pn+E1WtnSnLXFg9JJdDD9LbOOnKQLylTv
          RNIbMM/OsacfbHZkN3sSE3ckop290234d+Y07KPoM6lYXD8xnqJ1XkgDYgAgrG8qceoSdL7K+QJ
          8pyzX7oKRbhdLdmQlOTPL36wksNVwSPARl3ZfpYB6DlQkoN0NwRBXx/vUG5nsWw2lPPFTH4oiRR
          NsLoHnHL8HX+5FKsZzWte4A9/knwO40BJgjXs869R4GLGQ7asLFKGH4y6tmp6Tl23U1GD9Xr/Zc
          WDP74FQK0ITjTsiBEbIMJ3GEVpibM5vIh4zD66JwV2H1u1s+LBzzD20pPWOS+Go9ufntcYTxK3i
          9dlYiFFGDkff0qNY0Y428ltAHLyc0cYiXInADzElDoRFDnNOxFGu9S2IDGcGgNtlrIfTwAMU1cz
          BXmXZOeed9Tjh7muFzFbbgl5rOyjvpQSJKQAQZLlWRhgVx1xGSJWgdkwcGuj2ncJDTZjftN6lFB
          v1LD9qr0ZulYEKbP9lB6Kzz9LcM7iztyM2aGtdL/FLA5YMEKhJcIZ550Xn++O4/T2W+lsrozDVb
          4iZlOVSIPdGPVNeStRFk3vOmZR5yuMPGSzVKr/9zb0=
        lexfloatserver_api_key: 019u7492hjfdifuhqo98fhq3loifuh
        

## Checking that the server works

Open these pages

-   http://servername:5000/api/server/stats?apiKey=xxx
-   http://servername:5000/api/floating-licenses?apiKey=xxx

See also the [https://docs.cryptlex.com/floating-licenses/on-premise-floating-licenses/lexfloatserver](Cryptlex documentation on LexFloatServer)

## License

MIT / BSD

## Author Information

This role was created in 2019 by Claudio Bantaloukas
