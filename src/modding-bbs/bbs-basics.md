# Learning BBS

<hr>

The two best tutors to learn BBS from, are Arcsys and **you**. Read the vanilla game scripts, try to understand them, and also just go in and get your hands dirty. Learn by experimentation.

Having said that, we're not throwing you completely into the deep-end. What follows on this page, is a sort of quick overview of how BBS is structured.

If you want an actual glossary encompassing nearly everything BBS, check out [BBScript Documentation (Strive)](https://docs.google.com/document/d/1oVp_HDS-sjy2bEntQUHVaIk-P-4jeJx-3G89MC87xMw/edit), [DBFZ BBS doc](https://docs.google.com/document/d/1r8Uv-jz6R8VQuGp42_XV42vl4a1ZdWyxUEDlduMI3vM) or [DBFZ BBS Lookup](https://dobosken.github.io/dbfz_bbs_lookup/).

Note that the latter uses Broscar's bbscript for the `name_given` field and any code examples, so you can't directly copy-paste those unless you use the same system.

## State

The very basis of a move. The game reads and executed a state from top to bottom. This is called the program flow.

When a state ends for a character object, that character object is returned to a neutral state by the battle state manager (`CmnActStand` while grounded, `CmnActJump` while airborne). When a state ends for an effect object, that effect object is deleted.

If you players to be able to enter a state directly (e.g. through user input), you'll have to register it with `addMove` and `registerMove`. However, that is not needed if you only interact with a state by jumping to it.

## Subroutine

A subroutine is a bit of code in it's own block, seperate of states. It cannot contain sprites and has no real program flow, but it can contain pretty much every other function.

When you call a subroutine in your state, you can think of it like simply copy-pasting the code from that subroutine in it's place.

Subroutines are usually used to share one block of code with multiple different states.

If a subroutine starts with `cmn`, that means you'll find that specific subroutine inside `CMNEF`, and not inside the character's script.

## Labels

Remember that states are read from top to bottom? With labels, you can instead have the game jump to a specific point within a state.

```bbs_o
label: s32(loop)
sprite: s32(xxx034_13), 3
sprite: s32(xxx034_14), 3
sprite: s32(xxx034_12), 3
spriteEnd:
gotoLabel: s32(loop)
```

Congratulations, you just created an infinite loop! That's not very useful of course. Instead of `gotoLabel`, you can instead write `gotoLabelIfOperation: s32(loop), (IS_LESS_OR_EQUAL), var(ActionTime), int(60)`. Now you'll get a loop, **until** ActionTime hits 61. ActionTime is a variable that tracks how long an object is in a certain state, in game ticks. If ActionTime is 61 or more, the gotoLabel function does not trigger, and regular state flow is resumed from that point onwards.

You can find more functions like `gotoLabel`, by visiting [DBFZ BBS Lookup](https://dobosken.github.io/dbfz_bbs_lookup/) and clicking on the 'Flow' button next to the search bar.

## Variables

## Interrupts

Referred to as `upon` in the world of BBS. Why? Lol I dunno.

An interrupt executes a bit of code, the moment it's condition is triggered. This happens independent of program flow, meaning you can allow your objects to react to an event the moment it actually happens.

```bbs_o
beginState: s32(ExampleMove) {
    upon: (IMMEDIATE) {
        copyVar: var(act1), int(0)
        upon: (IDLING) {
            if: var(act1) {
                addTension: 20
            } endIf:
        } endUpon:
        upon: (RECEIVE_ATTACK) {
            clearRegisteredUponCode: (IDLING)
        } endUpon:
    } endUpon:
    sprite: s32(avp022_01), 1
    sprite: s32(avp022_02), 1
    sprite: s32(avp022_03), 1
    copyVar: var(act1), int(1)
    sprite: s32(avp022_04), 1
    spriteEnd:
} endState:
```

When you register an interrupt, you simultaneously define what code runs when it is triggered. As you can see, calls to set interrupts can also be nested.

In the code above, `upon: (IMMEDIATE)` activates **before** everything else, even before the first sprite is drawn. It also registers 2 new interrupt. `IDLING` runs every game tick.

Can you guess what this entire bit of code does?

## CMNEF

`CMNEF` is a special BBS file, used to share states and subroutines among all objects in the game. This makes it extremely potent for applying changes that affect all characters and all spawned effect objects.
However, if you alter it, it means your mod becomes incompatible with any other mods that change it.

In short, if you're creating a single custom character, you're better off not changing it.

If you're making a complete overhaul / balance patch, use and abuse it.

## Signals

## Interacting with other objects

applyTo, triggerUponInObject, signals, copyVarFromObject, linkObject

## Examples

Here is a document listing several techniques and how one can choose to implement them:

[google doc]()

TODO: Split off the BBS snippets from the DBFZ Google Doc into their own document.
  - Armour
  - Locking out moves
  - Revive on death

## Tips
In 10.1 there's a section called `Bulk extracting all BBS from the game`. If you parse all of them, you can use them to find the various uses of a certain bit of code in all vanilla game scripts.
Notepad++, for example, allows you to search for bits of text in multiple files (ctrl+shift+f). Just point it at the directoy where all those parsed scripts are stored, and you're good to go!
