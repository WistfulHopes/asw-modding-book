# Learning BBS

<hr>

The two best tutors to learn BBS from are ArcSys and **yourself**. Read the vanilla game scripts, try to understand them, and go in and get your hands dirty. Learn by experimentation.

Having said that, we're not throwing you completely into the deep-end. What follows on this page is a sort of quick overview of how BBS is structured.

If you want an actual glossary encompassing nearly everything BBS, check out [BBScript Documentation (Strive)](https://docs.google.com/document/d/1oVp_HDS-sjy2bEntQUHVaIk-P-4jeJx-3G89MC87xMw/edit), [DBFZ BBS doc](https://docs.google.com/document/d/1r8Uv-jz6R8VQuGp42_XV42vl4a1ZdWyxUEDlduMI3vM) or [DBFZ BBS Lookup](https://dobosken.github.io/dbfz_bbs_lookup/).

Note that the latter uses Broscar's bbscript for the `name_given` field and any code examples, so you can't directly copy-paste those unless you use the same system.

## State

The very basis of a move. The game reads and executed a state from top to bottom. This is called the program flow.

When a state ends for a character object, that character object is returned to a neutral state by native code (`CmnActStand` while standing, 'CmnActCrouch' while crouching, or `CmnActJump` while airborne). When a state ends for an effect object, that effect object is deactivated.

If you require players to be able to enter a state directly (e.g. through user input), you'll have to register it with `addMove` and `registerMove`. However, that is not needed if you only interact with a state by jumping to it.

## Subroutine

A subroutine (or function) is a separate block of code that can be reused in any state. It cannot contain sprites, but all other elements of BBS are usable.

Think of calling a subroutine as copy-pasting the contained code into the part of the state you call it in.

Subroutines are usually used to share one block of code with multiple different states. For example, if several special moves share common code, a subroutine could be used.

If a subroutine starts with `cmn` (not case-sensitive), that means you'll find that specific subroutine inside `CMNEF`, and not inside the character's script.

## Labels

Normally, states are run from top-to-bottom. However, with labels, you can instead have the game jump to a specific point within a state.

```bbs_o
Label: s32(loop)
CellBegin: s32(xxx034_13), 3
CellBegin: s32(xxx034_14), 3
CellBegin: s32(xxx034_12), 3
CellEnd:
Goto: s32(loop)
```

The above code runs an indefinite loop. However, this isn't very useful by itself. Instead of `Goto`, you can instead write `ID_GotoIfOP2: s32(loop), (IS_LESS_OR_EQUAL), var(ActionTime), int(60)`. Now the loop will run **until** ActionTime hits 61. ActionTime is a variable that tracks how long an object is in a certain state in terms of frames. If ActionTime is 61 or more, the gotoLabel function does not trigger, and regular state flow is resumed from that point onwards.

You can find more functions like `Goto` by visiting [DBFZ BBS Lookup](https://dobosken.github.io/dbfz_bbs_lookup/) and clicking on the 'Flow' button next to the search bar.

## Variables

## Interrupts

Also known as `upon` in the standard BBS dialect.

An interrupt executes a bit of code the moment its condition is triggered. This happens independent of the script flow, meaning you can allow your objects to react to an event the moment it actually happens.

```bbs_o
ActionBegin: s32(ExampleMove) {
    InterruptBegin: (IMMEDIATE) {
        copyVar: var(act1), int(0)
        InterruptBegin: (IDLING) {
            if: var(act1) {
                addTension: 20
            } endIf:
        } InterruptEnd:
        InterruptBegin: (RECEIVE_ATTACK) {
            clearRegisteredUponCode: (IDLING)
        } InterruptEnd:
    } InterruptEnd:
    CellBegin: s32(avp022_01), 1
    CellBegin: s32(avp022_02), 1
    CellBegin: s32(avp022_03), 1
    OpCopy: var(act1), int(1)
    CellBegin: s32(avp022_04), 1
    CellEnd:
} ActionEnd:
```

When you register an interrupt, you also define what code runs when it is triggered. As you can see, calls to set interrupts can also be nested.

In the code above, `InterruptBegin: (IMMEDIATE)` activates **before** everything else, even before the first sprite is drawn. It also registers two new interrupts. `IDLING` runs every game tick.

As an extra challenge, try to understand what this entire block does.

## CMNEF

`CMNEF` is a special BBS file used to share states and subroutines among all objects in the game. This makes it extremely potent for applying changes that affect all characters and all spawned effect objects.

However, if you alter it, it means your mod becomes incompatible with any other mods that change it.

In short, if you're creating a single custom character, you're better off not changing it. If you're making a complete overhaul / balance patch, use and abuse it.

## Signals

## Interacting with other objects

applyTo, triggerUponInObject, signals, copyVarFromObject, linkObject

## Examples

Here is a document listing several techniques and how one can choose to implement them:

[google doc]()

TODO: Split off the BBS snippets from the DBFZ Google Doc into their own document.
  - Armor
  - Locking out moves
  - Revive on death

## Tips
In 10.1 there's a section called `Bulk extracting all BBS from the game`. If you parse all of them, you can use them to find the various uses of a certain bit of code in all vanilla game scripts.
Notepad++, for example, allows you to search for bits of text in multiple files (ctrl+shift+f). Just point it at the directoy where all those parsed scripts are stored, and you're good to go!
