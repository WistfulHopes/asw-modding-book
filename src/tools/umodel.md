# Using Umodel

<hr>

Installation is fairly simple, however I would recommend instead using Fmodel unless you have specific reasons to use Umodel (such as audio or something). It's generally just a more mature piece of software.
However, for posterity, install it as such:

- Install Umodel from [this link](https://cdn.discordapp.com/attachments/828965774894563400/926715841083506759/umodel_animscale.rar?ex=66fd89a2&is=66fc3822&hm=f634f15a6a96a056788f88fbde8f72e24d0ffb864dd496d44c42954266315c57&) (if this is dead, it's in #strive-resources in the discord)
- Get it opened, point it at your game's install directory and *force the game override to 4.25*
- hit Okay, provide it the AES key `0x3D96F3E41ED4B90B6C96CA3B2393F8911A5F6A48FE71F54B495E8F1AFD94CD73`
<hr>
Steps 2 and 3 will need to be done *every time you launch*. However, Umodel can be launched with arguments using a shortcut;
mine is configured like such in the Target field, set it up as needed.
`"D:\MODDING\-- PROGRAMS\umodel_win32\umodel.exe" -gui -path="C:\Users\muuyo\Documents\UnrealEditor\RED\Content\Paks" -game="ue4.25" -sounds -aes="0x3D96F3E41ED4B90B6C96CA3B2393F8911A5F6A48FE71F54B495E8F1AFD94CD73"`