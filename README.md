

            ____  _____    __  ___                   ___    ____  ____
           / __ \/ ___/   /  |/  /___ _   _____     /   |  / __ \/  _/
          / /_/ /\__ \   / /|_/ / __ \ | / / _ \   / /| | / /_/ // /
         / ____/___/ /  / /  / / /_/ / |/ /  __/  / ___ |/ ____// /
        /_/    /____/  /_/  /_/\____/|___/\___/  /_/  |_/_/   /___/

                                   http://thp.io/2010/psmove/


PS Move API [![Documentation Status](https://readthedocs.org/projects/psmoveapi/badge/?version=latest)](https://psmoveapi.readthedocs.io/en/latest)  [![Build Status](https://travis-ci.org/thp/psmoveapi.svg?branch=master)](https://travis-ci.org/thp/psmoveapi)  [![AppVeyor Build Status](https://ci.appveyor.com/api/projects/status/github/thp/psmoveapi?branch=master&svg=true)](https://ci.appveyor.com/project/thp/psmoveapi)
===========

The PS Move API is an [open source](https://github.com/thp/psmoveapi/blob/master/COPYING) library for Linux, macOS and Windows to access the Sony Move Motion Controller via Bluetooth and USB directly from your PC without the need for a PS3. Tracking in 3D space is possible using a PS Eye (on Linux, Windows and macOS), an iSight camera (on macOS) or any other suitable camera source.

PS Move API has successfully participated in [Google Summer of Code 2012]([3] http://www.google-melange.com/gsoc/homepage/google/gsoc2012). Detailed documentation can be found in [my master's thesis](http://thp.io/2012/thesis/) about sensor fusion.


Core Features
-------------

 * Pairing of Bluetooth controllers via USB
 * Setting LEDs and rumble via USB and Bluetooth
 * Reading inertial sensors and buttons via Bluetooth
 * Tracking up to 5 controllers in 3D space via OpenCV
 * 3D orientation tracking via an open source AHRS algorithm
 * Sensor fusion for augmented and virtual reality applications

Supported Languages
-------------------

 * Core library written in C for portability and performance
 * SWIG-based bindings for Python, Java, Processing and C#
 * ctypes-based bindings for Python 3

Need Help?
----------

 * Free community-based support via the PS Move Mailing List[5]
 * Professional support and custom development [upon request](http://thp.io/about)

Hacking the Source
------------------

 * Coding style: No strict rules; keep consistent with the surrounding code
 * Patches should be submitted on Github as [pull request](https://github.com/thp/psmoveapi/pulls)
 * Bug reports and feature requests can be added to the [issue tracker](https://github.com/thp/psmoveapi/issues)

Environment Variables
---------------------

### `PSMOVE_TRACKER_CAMERA`

If set, this is the camera that will be used when using `psmove_tracker_new()`
instead of using auto-detection

Example: 

    export PSMOVE_TRACKER_CAMERA=2  # Will use the 3rd camera

### `PSMOVE_TRACKER_FILENAME`

If set, this will use a video file to playback instead of capturing from a
camera. Any camera settings are ignored.

Example:

    export PSMOVE_TRACKER_FILENAME=demo.avi # Will play demo.avi

### `PSMOVE_TRACKER_ROI_SIZE`

If set, this controls the size of the biggest (initial) ROI that will be used
to track the controller. Bigger means slower in general, but recovery from
tracking loss might be faster.

Example:

    export PSMOVE_TRACKER_ROI_SIZE=200

### `PSMOVE_TRACKER_WIDTH, PSMOVE_TRACKER_HEIGHT`

If set, these variables control the desired size of the camera picture.

Example:

    export PSMOVE_TRACKER_WIDTH=1280
    export PSMOVE_TRACKER_HEIGHT=720


Licensing
---------

The PS Move API source code is released under the terms of a Simplified BSD-style license, the exact license text can be found in [COPYING](https://github.com/thp/psmoveapi/blob/master/COPYING) and "Licensing" above) file.

Some third party code under ["external/"](https://github.com/thp/psmoveapi/blob/master/external) and "Licensing" above)) might be licensed under a different
license. Compiling PS Move API with these modules is optional, you can use
CMake options to configure which features you need. CMake will give you a
hint about the library licensing for your current configuration depending
on your options at configure time.

In general, all dependencies are under a MIT- or BSD-style license, with the
exception of the following dependencies:

 - PS3EYEDriver: Released under the MIT license, parts based on GPL code

   For interfacing with the PSEye camera on macOS (only in the tracker)
   CMake option: `PSMOVE_USE_PS3EYE_DRIVER` (disabled by default)

More information about the third party modules and licenses:

  - http://thp.io/2012/thesis/thesis.pdf (page 51-53)
  - File ["external/README"](https://github.com/thp/psmoveapi/blob/master/external/README) in this source tree


More Information
----------------

 * License: Simplified BSD-style license (see [COPYING](https://github.com/thp/psmoveapi/blob/master/COPYING) and "Licensing" above)
 * Maintainer: Thomas Perl <m@thp.io>
 * Website: http://thp.io/2010/psmove/
 * Git repository: https://github.com/thp/psmoveapi
 * Mailing list: psmove@googlegroups.com (see the [web interface](https://groups.google.com/forum/#!aboutgroup/psmove) for details)
 * Documentation: https://psmoveapi.readthedocs.io/


