Dependencies
************

Build dependencies
==================

.. list-table::

   * - **dependency**
     - **comment**

   * - c++11 & c11 compiler: gcc >= 4.8 or clang >= 3.4
     - required

   * - python >= 2.6
     - required

   * - scons
     - required

   * - ragel
     - required

   * - gengetopt
     - required, unless you disable building command-line tools

   * - pkg-config
     - optional, auto-detected, used for better discovery of system libraries

   * - config.guess
     - | optional, auto-detected, used for better identification of system type
       | (may be provided by autotools, automake, or libtool)

   * - | libtool, intltool, autoconf, automake
       | make, cmake, meson, ninja
     - | optional, used to build dependencies automatically
       | when ``--build-3rdparty`` option is given

Vendored dependencies
=====================

.. list-table::

   * - **dependency**
     - **version**
     - **license**
     - **comment**

   * - `dr_wav <https://github.com/mackron/dr_libs/blob/master/dr_wav.h/>`_
     - 0.13.14
     - MIT-0
     - single-header library

   * - `hedley <https://nemequ.github.io/hedley/>`_
     - 15
     - CC0
     - single-header library

Runtime dependencies
====================

.. list-table::
   :widths: 10 25 30 25

   * - **dependency**
     - **version**
     - **license**
     - **comment**

   * - `libatomic_ops <https://github.com/ivmai/libatomic_ops/>`_
     - >= 7.6.0
     - MIT
     - required on non-GNU toolchains

   * - `libsndfile <https://libsndfile.github.io/libsndfile/>`_
     - >= 1.0.26
     - LGPL
     - optional, enables additional audio file formats

   * - `libunwind <https://www.nongnu.org/libunwind/>`_
     - >= 1.2.1
     - X11
     - optional, enables backtrace on panic or crash

   * - `libuv <https://libuv.org>`_
     - >= 1.5.0 (recommended >= 1.35.0)
     - MIT
     - required

   * - `OpenFEC <https://openfec.inrialpes.fr>`_
     - >= 1.4.2 (recommended to use `our fork <https://github.com/roc-streaming/openfec>`_)
     - CeCCIL-C (LGPL-like) + CeCCIL (GPL-like, only for LDPC-Staircase) + BSD-like + CC BY-SA
     - optional, enables packet loss repair with FECFRAME

   * - `OpenSSL <https://www.openssl.org/>`_
     - >= 1.1.1
     - Apache
     - optional, enables CSPRNG

   * - `PulseAudio <https://www.freedesktop.org/wiki/Software/PulseAudio/>`_
     - >= 5.0
     - LGPL
     - optional, enables PulseAudio support

   * - `SoX <https://sox.sourceforge.net>`_
     - >= 14.4.0
     - LGPL
     - optional, enables additional audio file formats and sound servers

   * - `SpeexDSP <https://github.com/xiph/speexdsp>`_
     - >= 1.2beta3
     - BSD
     - optional, enables fast Speex resampler

.. note::

   For OpenFEC, it's highly recommended to use `our fork <https://github.com/roc-streaming/openfec>`_ or manually apply patches from it. The fork is automatically used when using ``--build-3rdparty=openfec`` option. It contains several critical fixes that are not available in the upstream.

.. note::

   On some systems (e.g. Raspbian), you may need to explicitly install ``libatomic1``. It is part of GCC runtime, but is packaged separately and is not pre-installed everywhere.

.. note::

   libuv versions before 1.5.0 may have problems on 64-bit ARMs.

.. note::

   SpeexDSP (libspeexdsp) below 1.2rc3 was part of Speex (libspeex) package.

Development dependencies
========================

.. list-table::

   * - **dependency**
     - **comment**

   * - `CppUTest <http://cpputest.github.io>`_ >= 4.0
     - needed to build tests

   * - `Google Benchmark <https://github.com/google/benchmark>`_ >= 1.5.5
     - needed to build benchmarks

   * - `clang-format <https://clang.llvm.org/docs/ClangFormat.html>`_ >= 10
     - needed to format code with ``scons fmt``

   * - `doxygen <https://www.doxygen.nl/>`_ >= 1.6, `graphviz <https://graphviz.gitlab.io/>`_
     - needed to build doxygen and sphinx documentation

   * - `sphinx <https://www.sphinx-doc.org/>`_ >= 5, `breathe <https://github.com/michaeljones/breathe>`_
     - needed to build sphinx documentation

.. note::

   Different versions of clang-format may format the code differently, thus we restrict the range of allowed versions. If you use another version, CI checks may fail.
