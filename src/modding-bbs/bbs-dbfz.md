# DBFZ

<hr>

# Bugs
  - BRS: Replace createParticle: `s32'bg_	roundsmokeL', 0` with `createParticle: s32'bg_groundsmokeL', 0`
  - ASN: Do a global search and replace to turn `Don’t` into `Dont`
  - JNNEF: Do a global search for `KidanFire', 0, 100` and remove the odd symbol at the beginning of every one of them.
  - FRN: The subroutine named `FDownLoop_Type` is missing 1 function.
    - Add `storeValue: (VARIABLE), 52, (STATIC), 1` if you're using old bbscript.
    - Add `storeValue: Mem(52), Val(1)` if you're using regular bbscript 1.0(+).
    - Add `copyVar: var(act7), int(1)` if you're using Broscar's bbscript.
    - Add `Unknown46: Unknown, Unknown, Unknown, Unknown` if you're using Burritoscript.


# Broscar's workflow
A consequence of DBFZ barely having any modders active in BBS, is that Broscar has been pushing forward solo, with little regard for existing BBS conventions. You may choose to go along for the ride.

| Pros | Cons |
| ----------------------------- | ----------------------------- |
| Easy to use tools that allow for very fast iteration | The first setup requires a bit more work |
| Detailed documentation |  Uses a different 'dialect' of BBS.<br />All concepts of BBS still apply, but functions and variables use different keywords. |
| Automatically fixes the parser bugs for BRS, ASN and JNNEF | Assumes you have *some* experience with programming |
| Has better indentation, code folding and works with the `Function list` feature of Notepad++ | |

[https://github.com/dobosken/bbscript](https://github.com/dobosken/bbscript)

[https://github.com/dobosken/dbfz_npp](https://github.com/dobosken/dbfz_npp)

[https://dobosken.github.io/dbfz_bbs_lookup/](https://dobosken.github.io/dbfz_bbs_lookup/)

TODO: Clean up and share build scripts. Check if ye olde Windows versions still work.
