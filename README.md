# boostbuilder

A makefile designed to build the well-known Boost C++ library to be included in projects as a dependency.

## Getting Started
To get started, simply clone this repo, and download the latest Boost library (this project was tested with the latest version of 1.66.0) from the [Boost](http://www.boost.org/users/history/version_1_66_0.html) website.


**NOTE**: Boost was not included in this build because the archive is around 85mb compressed, and 683mb uncompressed.
----

## Prerequisites

* Make
* C++ 11 capable compiler (this makefile uses a defined variable to define the compiles as g++)
* Linux environment (this makefile is built for a linux/mac environment)
* Boost source (this was latest tested with v1.66.0)

## Usage

* Download the contents of this repo and extract to a directory
* Download the Boost source archive
  * Extract the Boost archive to {project root}\shared\
* Change makefile references to use the version you just extracted
  * edit {project root}\makefile
    * change the BOOST_VER variable (around line #9) to reflect your Boost source that was uncompressed
      * this variable is the last part of the Boost source folder (after the word "boost" and including characters such as "_")
      * there are NO spaces after the "=" sign
    * change the BOOST_LIBS_TO_BUILD variable
      * this specifies the boost libraries to build (based on folder names in boost/libs/)
* The above makefile calls {project root}\shared\build_boost_libs.mk and passes arguments about version and wanted libs
* Run ```make dependencies``` from the command line, targetting {project root}\makefile


