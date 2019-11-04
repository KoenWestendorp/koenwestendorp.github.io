---
layout: post
title:  "AutoHotkey at work"
date:   2019-06-21 19:10:40
---

Over the summer I have been working at a trailerbuilder where I am reorganizing a storageroom. The contents need to be labeled using small stickers. These stickers show a short description of the product, a bar code and the part number. 
To print a sticker for a part that has already been added to the database, I need to click on a very small button, then click another small button in a pop-up and finally click 'OK' in a dialogue box. Now, this really isn't that much of a hassle, until you take into account that this storage room stores more than 400 different parts. Especially when printing a long list of parts this really gets under my skin. So I set out to find a solution. 

Enter: [AutoHotkey](https://www.autohotkey.com/), the (dodgy, botched half-way reliable) antidote to all your mouseclick and software frustrations! This is the script I wrote for the label printing. A true time-saver.

```autohotkey
~LButton & E::
MouseGetPos, xcoord, ycoord
Click, 220, ycoord ; select the row the mouse is hovering over
Sleep, 200         ; wait for the software to act
Click, 134, 273    ; click on the buttons for the printing...
Sleep, 200
Click, 300, 325
Sleep, 200
Send, {Enter}      ; confirm the dialog box
return
```

## Script for finding coordinates
The programming of the clicks required very precise coordinates, since a click a few pixels to the top would result in the printer in the office being occupied, printing page upon page of database entries. I clicked this button accidentally once (like I said, it is located just above the button for printing the labels and also no dialoge box is shown to confirm the printout of around a 1000 pages) and I was fortunate enough that someone over in the office noticed and canceled the print.

This hotkey uses the middle mouse button as a trigger and displays a small messagebox containing the coordinates of your cursor.

```autohotkey
MButton::
MouseGetPos, xcoord, ycoord 
MsgBox, X = %xcoord%, Y = %ycoord%. 
return
```

## Reinventing the copy-paste wheel
Also, I was keeping a list of my progress in Excell. The copying and pasting of information like the article number was absolutely horrible, because when I would paste an article number from Excell into the search box -- without fail -- two escaped unicode return characters would be appended to the text. So this required me to press backspace twice, for each querry... Of course, this was so painfull to my soul, that when I woke up from fainting at the mere idea of doing this even three more times, I woke up to find another little script waiting on the crummy Windows Vista desktop. 

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
SendInput, {Backspace}{Backspace} ; I mean, seriously... 
; ...WHY DO I HAVE TO DO THIS??!!??!/!1
Sleep, 100
SendInput, {Enter}
return
```

I don't intend to get all personal here, but I think it could be said that the existance of AutoHotkey has truly saved my life over the summer. It helped me shape my work tasks as if I were in a [Factorio](https://factorio.com/) game, 100 hours in at 04:00 in the monday morning. 

Well, I'm off writing a script that writes itself scripts to improve my efficiency. The factory must grow!

Love, Koen
