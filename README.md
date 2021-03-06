# boostbuilder

A makefile designed to build the well-known Boost C++ library to be included in projects as a dependency.

## Getting Started
To get started, simply clone this repo, and download the latest Boost library (this project was tested with the latest version of 1.66.0) from the [Boost](http://www.boost.org/users/history/version_1_66_0.html) website.


:warning:**NOTE**: Boost was not included in this build because the archive is around 85mb compressed, and 683mb uncompressed.
----

## Prerequisites

* Make
* C++ 11 capable compiler (this makefile uses a defined variable to define the compiler as g++)
* Linux environment (this makefile is built for a linux/mac environment)
* Boost source (this was tested with v1.66.0)

## Usage

* Download the contents of this repo and extract to a directory
* Download the Boost source archive
  * Extract the Boost archive to the project root
* Run the makefile, and include variables about the Boost version and wanted libraries
  * ``make -f build_boost_libs.mk BOOST_LIBS_TO_BUILD="filesystem timer chrono system" BOOST_LIB_DIR="lib_boost_1_66_0" BOOSTDIR="boost_1_66_0" BOOST_VER="_1_66_0``
* ``BOOST_LIBS_TO_BUILD`` : A comma seperated list of boost libraries to build (corresponding to folders in ``boost_1_66_0\libs\``)
* ``BOOST_LIB_DIR`` : The directory to output the .a files that are to be built
* ``BOOSTDIR`` : The directory pointing to the folder that was extracted form the Boost archive
* ``BOOST_VER`` : The version suffix for the boost verison extracted (corresponds to the suffix of the extracted boost folder -- in this example it is "_1_66_0")

:warning:**NOTE**: I am aware that this makefile uses the paradigm of recursive makefiles, which is frowned upon (due to innefficient make use, and long build times), but was unsure how to abstract configurations and such nicely. [Recursive Make Considered Harmful - Peter Miller](http://aegis.sourceforge.net/auug97.pdf)

## Output
The output of this build are the .a c++ library files (depicted by the BOOST_LIB_DIR makefile variable) that can be linked with another project during the linking phase of building.
