<!--
    This Source Code Form is subject to the terms of the Mozilla Public
    License, v. 2.0. If a copy of the MPL was not distributed with this
    file, You can obtain one at http://mozilla.org/MPL/2.0/.
-->

<!--
    Copyright (c) 2014, Joyent, Inc.
-->

# aperture-config

This repository is part of the Joyent SmartDataCenter project (SDC).  For
contribution guidelines, issues, and general documentation, visit the main
[SDC](http://github.com/joyent/sdc) project page.

aperture-config contains the shared
[aperture](http://github.com/joyent/node-aperture) configuration files for any
service needing to authorize requests using the RBAC system, including
cloudapi, manta-muskie and manta-marlin. Notably, it contains the type table
that maps condition variable names to types. For example, an aperture sentence
can be written like:

    Can read foo if sourceip::ip = 192.168.0.0/16

The `::ip` suffix indicates that `sourceip` should be parsed as an IP (or range
of IPs). Including a type table for aperture allows the `::ip` suffix to be left
off:

    Can read foo if sourceip = 192.168.0.0/16


Services that wish to be consistent with other services using aperture should
use the type table included in aperture-config.
