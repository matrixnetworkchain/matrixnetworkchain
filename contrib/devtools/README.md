Contents
========
This directory contains tools for developers working on this repository.

optimize-pngs.py
================

A script to optimize png files in the MatrixNetwork
repository (requires pngcrush).

update-translations.py
======================

Run this script from the root of the repository to update all translations from transifex.
It will do the following automatically:

- fetch all translations
- post-process them into valid and committable format
- add missing translations to the build system (TODO)

See doc/translation-process.md for more information.