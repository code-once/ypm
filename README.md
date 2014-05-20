YPM - your package manager
============================
![YPM](http://ypm.it-o-t-f.com/logo.svg "YPM Logo")

PROJECT GOALS:
==============
* cross platform
* cross language
* binary distribution support
* open source database containing recipes
* install from github/bitbucket like sites if they ship build/install recipes
* serve all distributions by providing the data they need: Information about
  how to install projects
* allowing you to choose your own balance between beeing bleeding edge and
  stable and which to optimize: Estimated build/download time or being closer
  to your preferred set of most stable/up to date packages.
* clearly separate build from runtime dependencies. Thus replacing a library
  in between will only cause some reconfiguration, but no full rebuilds.
  Obviously this "might" brake for some combinations but very often it just
  works and is fastest.

SAMPLE USAGE
============
This shell example shows how it'll look like installing a python project called A,
a Ruby project called B and so on:

    # Note how packages get simply prefixed by language file extension
    $ ypm i[nstall] py-A rb-B hs-C java-D js-E ml-F scala-G

      ypm: You haven't setup a configuration file yet.
      May I assume you want
        * to use latest versions unless there are known bugs or security issues
        * you trust the global package database
      [Y]/n
      .. thanks .. installing ..
      downloads: 200 MB of source
      downloads: 180 MB of prebuild binaries
      estimated execution time: 40 min
      ... build/download logs


Sample shell session installing from github like repositories:

    $ # assuming package has sane package description in its repository
    $ ypm install github:user/package


Starting to hack on an arbitrary project:

    $ # this will checkout sources, provide utilities, whatever you need to get
    $ # started hacking on a project:
    $ ypm hack-on "package-foo"


How to configure the solver?

    $ export YPM=SOLVER_CONFIG=file:PROFILE=~/ypm-profile:PACKAGE_POOL=A:PACKAGE_POOL=B

    where A,B can be the open source package database run by YPM project.


LANGUAGE PROGRESS
=================
* C (planning)
* C++ (planning) [details](./LANG-C-AND-CPP.md)
* lua (planning) [details](./LANG-LUA.md)
* Ruby (planning)
* PHP (planning)
* Haskell (planning)
* Perl (planning)
* Python (planning)
* FreePascal (planning)
* NodeJS (planning)
* Java (planning)
* Scala (planning)
* TCL (planning)
* Erlang (planning)
* Rust (planning)
* Ocaml (planning)
* D (planning)
* Fortran (planning)
* urweb (planning)
* Elisp (Emacs extensions) (planning)
* Lisp (planning)
* VimL (Vim plugins) (planning)
* mono (planning, no idea how much work this would be yet)

Which language do you think is missing?

TEST CASES (SOFTWARE TO INSTALL)
================================
    { package: "YPM"; description = "this package manager"; }
    { package: "c-Vim"; description = "my favorite editor allowing to enable python/ruby/lisp/... support"; }
    { package: "Vim-and-YouCompleteMe"; description = "Vim along with YouCompleteMe extension using Py interface interfacing with C extensions"; }
    { package: "elips-Emacs"; description = "favorite editor written in Elisp and C"; }
    { package: "c-Qgis"; description = "advanced cross platform C++ application"; }
    { package: "rb-rails"; description = "favorite ruby web system"; }
    { package: "py-plone"; description = "favorite Python web system"; }
    { package: "hs-Yi"; description = "Haskell editor which can reconfigure itself at runtime"; }
    { package: "ps-Lazarus"; description = "Free Pascal IDE"; }
    { package: "c-git"; description = "C/Perl/.. common version control system also used by github"; }
    { package: "js-etherpad"; description = "nodejs collaborative editing software with dependencies"; }
    { package: "haxe-openfl"; description = "cross platform gaming dev environment. Requires Ocaml (to build haxe) and haxe to build libraries"; }

    Which ones do you want me to work on?

PLATFORMS WHICH WILL BE SUPPROTED
=================================
* linux
* OSX/Darwin
* cygwin (thus Windows)
* mingw ?
* FreeBSD/OpenBSD

NEXT STEPS
==========
* describe package recipe format
* prototype implementation
* make test cases work
* think about what is next

PROGESS / TIMELINE
==================
I'm working on this project in my spare time only. Sorry, no timeline yet.
Donate to change this, see next section

SUPPORT THIS PROJECT
====================
* By donating to [bounty source fundraiser](https://www.bountysource.com/fundraisers/572-ypm-your-package-manager)
* By telling me in which alternative way you want to support such as coding,
  testing, reviewing documentation
* By telling me which software to support first


MY BACKGROUND
=============
I've been coding for 15 years. Years ago I switched to linux (gentoo), then to
nixos.org always reaching for the best platform to use. Yet I didn't find it.

BACKENDS
========
* Nix (my current favorite package distribution system serving cygwin, darwin,
  linux and people are working hard to optimize the BSD systems)
* a newly written one making home installs painless
