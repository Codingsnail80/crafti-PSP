crafti ported to the PSP
======

Screenshots
-----------

![menu](https://github.com/Vogtinator/crafti/assets/1622084/14ab2afb-5230-4b84-9f09-c90114474670)
![anim](https://github.com/Vogtinator/crafti/assets/1622084/7ff80a5e-8ffc-43e2-ad8f-3cb5a3e393f5)

![newinv](https://github.com/Vogtinator/crafti/assets/1622084/ab4e649c-6959-4d47-937c-c0c657d6dc83)
![redstone](https://github.com/Vogtinator/crafti/assets/1622084/cc21d688-199f-49a6-a65b-b3586224f893)

![help](https://github.com/Vogtinator/crafti/assets/1622084/70135a04-63c5-4e8f-ac1f-7095d4043110)
![settings](https://github.com/Vogtinator/crafti/assets/1622084/f3c9630e-c4c7-4e4f-900f-d4e251af04b9)

![ticalc.org Program Of The Year 2014](http://www.ticalc.org/archives/files/ss/859/85909.gif)

Controls
--------

Move around using the numpad: 8-4-6-2  
Jump using 5  
Switch the current inventory slot with 1-3  
Open a list of blocks with "."  
Set the current inventory slot with 5 while the block list is open  
Put a block down with 7 and destroy a block with 9  
Open the menu with menu, move the cursor with 8-2 and select it with 5  
ESC is a shortcut for "Save & Exit"

Limitations
-----------

crafti doesn't use floats, so there will be some graphical inaccuracies.


# How to build:
First you need to isntall the pspdev library if you haven't already.
Get it from their downloads page: https://pspdev.github.io/installation.html
If you don't see your operating system listed then follow their instructions on compiling it for your system. I recomend getting a download if possible though.

run these commands:
`````
git clone https://github.com/Codingsnail80/crafti-PSP.git

cd crafti-PSP.git

git submodule update --init --recursive

cd SDL-legacy

./autogen.sh

LDFLAGS="-L$(psp-config --pspsdk-path)/lib" LIBS="-lc -lpspuser" \
     ./configure --host psp --prefix=$(psp-config --psp-prefix)

make

make install

cd..

psp-cmake .

make
`````

Once it has compiled it should generate a EBOOT.PBP file that you can run on an emulator or on your firmware modded PSP.
