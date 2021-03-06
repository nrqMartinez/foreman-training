!SLIDE smbullets small
# Requirements - Operating System

* Red Hat Enterprise Linux 7
 * EPEL repository
 * Optional and RHSCL Channel
 * optionally: Puppetlabs Repository
* CentOS, Scientific Linux, Oracle Linux 7
 * EPEL repository
 * SCLorg SIG repository
 * optionally: Puppetlabs Repository
* Fedora (not recommended) 
* Debian 8
 * optionally: Puppetlabs Repository
* Ubuntu 14.04 & 16.04
 * optionally: Puppetlabs Repository

~~~SECTION:handouts~~~

****

~~~PAGEBREAK~~~

On the mentioned operating systems packages are provided by the project, a installation from source
is not recommended. On all platforms all updates should be applied before installation. Using the
Puppetlabs Repository providing an up-to-date version of Puppet is preferred.

~~~ENDSECTION~~~

!SLIDE smbullets small noprint
# Requirements - Puppet & Facter

* Support matrix

Puppet version         | Foreman installer | Smart proxy     | Report/fact processors | ENC
-----------------------|-------------------|-----------------|------------------------|--------------------------------
0.25.x, 2.6.0 - 2.6.5  | Not supported     | Untested        | Untested               | No Parametrized Classes
2.6.5+                 | Not supported     | Supported       | Supported              | Supported
2.7.x                  | Supported         | Supported       | Supported              | Supported
3.0.x                  | Limited support   | 1.1 or higher   | Supported              | Supported
3.1.x - 3.4.x          | 1.1 or higher     | 1.1 or higher   | Supported              | Supported
3.5.x                  | 1.4.3 or higher   | 1.4.2 or higher | Supported              | Supported
3.6.0+                 | 1.4.3 or higher   | 1.5.1 or higher | Supported              | Supported
4.x                    | 1.12 or higher    | 1.12 or higher  | Supported              | Supported
5.x                    | 1.16 or higher    | 1.16 or higher  | Supported              | Supported

* Puppet Enterprise is not supported
* All-in-one and FHS packaging model are both supported for Puppet 4 and 5
* Puppet Master and Puppet Server are both supported
* Facter 1.x is supported, 2.x requires Foreman >= 1.4.2
* Structured Facts are supported with Foreman >= 1.12

!SLIDE smbullets small printonly
# Requirements - Puppet & Facter

Puppet version | Foreman installer | Smart proxy     | Report/fact processors | ENC
---------------|-------------------|-----------------|------------------------|--------------------------------
0.25.x         | Not supported     | Untested        | Untested               | No Parametrized Classes
2.6.0 - 2.6.5  | Not supported     | Untested        | Untested               | No Parametrized Classes
2.6.5+         | Not supported     | Supported       | Supported              | Supported
2.7.x          | Supported         | Supported       | Supported              | Supported
3.0.x          | Limited support   | 1.1 or higher   | Supported              | Supported
3.1.x - 3.4.x  | 1.1 or higher     | 1.1 or higher   | Supported              | Supported
3.5.x          | 1.4.3 or higher   | 1.4.2 or higher | Supported              | Supported
3.6.0+         | 1.4.3 or higher   | 1.5.1 or higher | Supported              | Supported
4.x            | 1.12 or higher    | 1.12 or higher  | Supported              | Supported

~~~PAGEBREAK~~~

* Puppet Enterprise is not supported
* All-in-one and FHS packaging model are both supported for Puppet 4
* Puppet Master and Puppet Server are both supported
* Facter 1.x is supported, 2.x requires Foreman >= 1.4.2
* Structured Facts are supported with Foreman >= 1.12

~~~SECTION:handouts~~~

****

An up-to-date version of Puppet 3.x is recommended while other versions will work. Puppet 4.x support is
introduced with Foreman 1.12, supporting All-in-one and Filesystem-Hierarchy-Standard packaging standard.
Puppet 5.x support was added with Foreman 1.16 in the same way.
Puppet Enterprise is not supported, but can work with manual tweaking of the setup.

Both versions of the central server in a Puppet environment are supported. If the All-in-on package of Puppet 4 or 5
is found it will use the Puppet Server, in all other cases it will setup Puppet Master using Apache and Passenger.

Facter 1.x is supported, Facter 2.x is supported by requires at least Foreman 1.4.2. Support for structured
facts provided by Facter 2.x is also added with Foreman 1.12.

~~~ENDSECTION~~~

!SLIDE smbullets small
# Requirements - Communication

* Port matrix (depending on installation)

Port        | Protocol  | Required For
------------|-----------|------------------------------------------------------------------
53          | TCP & UDP | DNS Server
67, 68      | UDP       | DHCP Server
69          | UDP       | TFTP Server
80, 443     | TCP       | HTTP & HTTPS access to Foreman web UI - using Apache + Passenger
3000        | TCP       | HTTP access to Foreman web UI - using standalone WEBrick service
3306        | TCP       | Separate MySQL database
5910 - 5930 | TCP       | Server VNC Consoles
5432        | TCP       | Separate PostgreSQL database
8140        | TCP       | Puppet Master
8443        | TCP       | Smart Proxy, open only to Foreman

~~~SECTION:handouts~~~

****

~~~PAGEBREAK~~~

Depending on your installation the ports above are required to be accessable on the Foreman server,
by Foreman and the managed systems.

~~~ENDSECTION~~~
