FVZCoin integration/staging tree
================================

http://www.fvzcoin.com

Copyright (c) 2009-2013 Bitcoin Developers
Copyright (c) 2013-2014 DarkCoin Developers
Copyright (c) 2014      FVZCoin Developers

What is FVZCoin?
----------------

FVZCoin is a lite version of Bitcoin using X11 as a proof-of-work algorithm.
 - Super secure hashing algorithm: 11 rounds of scientific hashing functions (blake, bmw, groestl, jh, keccak, skein, luffa, cubehash, shavite, simd, echo)
 - Block reward is controlled by : 5678/(((Difficulty+2600)/11)^2)
 - GPU/CPU only mining
 - Block generation: 1 minutes
 - Difficulty Retargets every block using DARK Gravity Wave
 - Est. 5,000-50,000 Coins in 1 Year, 20,000-200,000 in 5 Years, 37,000-367,000 in 15 Years,  42,000-417,000 in 25 Years, 44,000-434,000 in 50 Years
 - Anonymous blockchain using darkSend technology (Based on CoinJoin): Beta Testing

For more information, as well as an immediately useable, binary version of
the FVZCoin client sofware, see http://www.fvzcoin.com

License
-------

FVZCoin is released under the terms of the MIT license. See `COPYING` for more
information or see http://opensource.org/licenses/MIT.

Development process
-------------------

Developers work in their own trees, then submit pull requests when they think
their feature or bug fix is ready.

If it is a simple/trivial/non-controversial change, then one of the FVZCoin
development team members simply pulls it.

If it is a *more complicated or potentially controversial* change, then the patch
submitter will be asked to start a discussion (if they haven't already) on the
[mailing list](http://sourceforge.net/mailarchive/forum.php?forum_name=bitcoin-development).

The patch will be accepted if there is broad consensus that it is a good thing.
Developers should expect to rework and resubmit patches if the code doesn't
match the project's coding conventions (see `doc/coding.txt`) or are
controversial.

The `master` branch is regularly built and tested, but is not guaranteed to be
completely stable. [Tags](https://github.com/fvzcoin/fvz) are created
regularly to indicate new official, stable release versions of FVZCoin.

Testing
-------

Testing and code review is the bottleneck for development; we get more pull
requests than we can review and test. Please be patient and help out, and
remember this is a security-critical project where any mistake might cost people
lots of money.

### Automated Testing

Developers are strongly encouraged to write unit tests for new code, and to
submit new unit tests for old code.

Unit tests for the core code are in `src/test/`. To compile and run them:

    cd src; make -f makefile.unix test

Unit tests for the GUI code are in `src/qt/test/`. To compile and run them:

    qmake BITCOIN_QT_TEST=1 -o Makefile.test bitcoin-qt.pro
    make -f Makefile.test
    ./fvzcoin-qt_test