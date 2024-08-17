Hummingbird is a GUI for the TI-84 Plus CE programmable graphing calculator written completely in TI-BASIC.

**1: Installation:**
Use TI-Connect CE or an alternative program to send HBIRD.8xp and HSYSP.8xp to your calculator. Ensure that HSYS.8xp is stored in RAM.

**2: Pre-Use/How to Add Programs to HBIRD**
**2.1: HSYSP APP DISPLAY**

  HSYSP.8xp is the Hummingbird component reliable for storing several presets used for configuration (like a .conf file but callable), and it relies on having somewhat hard-coded configuration in it to work properly.
Edit HSYS.8xp on your calculator or with TI-CONNECT CE or TokenIDE or whatever you want to edit it with. Whatever value is stored into the variable M on the first line (0 by default) must be exactly equal to
how many programs will be pinned on the desktop. For adding a first program, this should be:
_1→M_
  Then, below the area commented "APP DISPLAY", insert the following code:
_Output(⌊AY(_N_),⌊AX(_N_),"_NAME_")_
  where N is the number you just set M to and NAME is a four-character name you wish the program to appear as. ⌊ can be typed on the calculator by going into 2nd+list -> OPS -> B:⌊ The following example APP DISPLAY is adequate for
handling 4 programs:
_Output(⌊AY(1),⌊AX(1),"PONG")
Output(⌊AY(2),⌊AX(2),"WORD")
Output(⌊AY(3),⌊AX(3),"SNKE")
Output(⌊AY(4),⌊AX(4),"MATH")_

**2.2: HSYSP APP EXEC**

  Scroll down to the area commented "APP EXEC". Then insert the following line of code underneath the line "Z→⌊CD(3)" and "ClrHome":
_If ⌊CD(3)=1:prgmPRGM_
  _PRGM_ is the name of whatever program you want to be run whenever the item you labeled as _NAME_ is clicked on from the desktop.
Now you can exit your editor and startup HBIRD by running prgmHBIRD.

**3: Navigation and Use**

  Hummingbird is yet another example of the desktop metaphor. The cursor ("^\") is moved quickly by the d-pad (arrows), and slowly by the _del_, _stat_, _vars_ and _clear_ (or _trace_ and _graph_) buttons. Clicking is done with the
_enter_ key or the _2nd_ key (which I find a lot more comfortable). Basic settings and information can be seen in the "Alpha Menu", accessed by pressing the _alpha_ or _y=_ keys. You can also move where programs are pinned to by
placing the cursor onto a program and pressing the _MODE_ button, moving it around, and then clicking.
