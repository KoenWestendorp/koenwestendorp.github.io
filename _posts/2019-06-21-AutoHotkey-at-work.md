---
layout: post
title:  "Amazing picture!"
date:   2019-06-20 19:10:40
---

Since a few weeks I have been working at a trailerbuilder where I am reorganizing a storageroom. The contents need to be labeled using small stickers. These stickers show a short description of the product, a bar code and the part number. 
To print a sticker for a part that has already been added to the database, I need to click on a very small button, then click another small button in a pop-up and finally click 'OK' in a dialogue box. Now, this really isn't that much of a hassle, until you take into account that this storage room stores about 350 different parts. Especially when printing a long list of parts this really gets under my skin. So I decided to find a solution. 

## 
```autohotkey
~LButton & E::
MouseGetPos, xcoord, ycoord
Click, 220, ycoord
Sleep, 200
Click, 134, 273
Sleep, 200
Click, 300, 325
Sleep, 200
Send, {Enter}
return
```

Now this works really well and I decided to try and improve my life a little bit more by making some other hotkeys.

## Trick for finding coordinates
The programming of the clicks required very precise coordinates, since a click a few pixels to the top would result in the printer in the office being occupied, printing page upon page of database entries. I clicked this button accidentally once (like I said, it is located just above the button for printing the labels and also no dialoge box is shown to confirm the printout of around a 1000 pages) and I was fortunate enough that someone in the office knew how to cancel the print.

This hotkey uses the middle mouse button as a trigger and displays a small messagebox containing the coordinates of your cursor.

```autohotkey
MButton::
MouseGetPos, xcoord, ycoord 
MsgBox, X = %xcoord%, Y = %ycoord%. 
return
```

## Reinventing the copy-paste wheel

```autohotkey
~LButton & C::
KeyWait, LButton
Sleep, 10
Send, ^C
Sleep, 300
Click, 80, 373
Sleep, 100
Send, ^V
Sleep, 100
SendInput, {Backspace}{Backspace}
Sleep, 100
SendInput, {Enter}
return
```

