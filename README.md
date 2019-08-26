# BootGenie
Patches for Boot Sector Games for Cheating

Boot Genie works on many 512-byte Boot Sector game titles for archaic x86 systems with proper BIOS support. Most effects are created to be valid at the same time.

## Introducing Boot Genie Game Ehnhancer for Boot Sector Games

With Boot Genie, you can patch certain game-play features and create special effects on a selection of available Boot Sector games found on the github ecosystem. These patches will change the original source, if you want to revert, just note the patches you have made and re-run them all with the -R option to 'patch.' You could also re-clone/update the repo as well. These patches use the standard 'patch' utility found in most *nix platforms

## Patching
run the patch utility and redirect in the patch. For example, if the game is tetranglix and you want to apply the time cheat, then patch the source with the following command:
 patch < tetranglix_time.patch

Reverting to the original source by removing this particular time cheat is as easy as:
 patch -R < tetranglix_time.patch

## Re-Assemble
Note that you are patching the source file, not the game image. You must reassemble the patched game in order to see your effects. An example of reassembling the tetranglix game after patching is the same as if you were to assemble it for the first time. One example with nasm is as follows:
 nasm -f bin tetranglix.asm -o tetranglix

## Playing
You can then flash to a real floppy drive or emulate in things such as Virtual Box and Qemu. A Qemu example of running one of these games after patching is:
 qemu-system-i386 -hda tetranglix

## Code Symbols
There are several types of codes that you can use to enhance the game-play elements with Boot Genie patches. Below are some quick visual cues as to what the code may do, and each code in the individual game sections will have further descriptions.

<img src=https://github.com/XlogicX/BootGenie/blob/master/invincible.png>
<img src=https://github.com/XlogicX/BootGenie/blob/master/expert.png>
<img src=https://github.com/XlogicX/BootGenie/blob/master/lives.png>
<img src=https://github.com/XlogicX/BootGenie/blob/master/speed.png>
<img src=https://github.com/XlogicX/BootGenie/blob/master/time.png>
<img src=https://github.com/XlogicX/BootGenie/blob/master/score.png>
<img src=https://github.com/XlogicX/BootGenie/blob/master/rules.png>
<img src=https://github.com/XlogicX/BootGenie/blob/master/multiplier.png>
<img src=https://github.com/XlogicX/BootGenie/blob/master/color.png>

## Games:

### Tetranglix: ab97c4173af22c083bf4a28cc732cc57 / https://github.com/shikhin/tetranglix/tree/85e65dba4a1c4569baef1275d5afe7859d626d03
tetranglix_color.patch (color.png)
    Just a pallet change to a brighter green environment
tetranglix_multiplier.patch (multiplier.png)
    Makes score increment by 255 points instead of just 1 point per vertical movement
tetranglix_square.patch (rules.png)
    This makes every tetronimo a square
tetranglix_score.patch (score.png)
    This makes the top score 1,000, instead of 100,000
tetranglix_time.patch (time.png)
    This makes the game slow down to half speed

### Invaders: 01d0277fdd7860ba12d350b0a49e734a / https://github.com/nanochess/Invaders/tree/0de3b3bb4ab03f1b9d4562e6ac05eec30f9c1168
invaders_advancement.patch (rules.png)
    Invaders advance down about a 1/3rd of the vertical distance for each horizontal swipe
invaders_lives.patch (lives.png)
    127 lives instead of the original 4 lives
invaders_speed.patch (speed.png)
    Invaders move much slower than normal

### fbird: e30ba26b36016aaf005e2b61c76606ec / https://github.com/nanochess/fbird/tree/7a7c27ac0081ea21b169964e2592a99d9b33eb9d
fbird_faster.patch (speed.png, expert.png)
    The game plays much faster
fbird_morepipes.patch (score.png, expert.png)
    pipes come in much more frequently
fbird_pipe.patch (rules.png)
    rediculous clearance in each pipe

### tronsolitare:
tronsolitare_highscore.patch (score.png)
    Initializes the score to 0x0e00
tronsolitare_speed.patch (speed.png)
    Game plays at half speed
tronsolitare_speed2.patch (speed.png)
    Game plays at half speed and doesn't get incrementally faster
tronsolitare_noclipping.patch <img src=https://github.com/XlogicX/BootGenie/blob/master/invincible.png>
    Bounds checking is off, you are invincible
tronsolitare_lowscore.patch (socre.png)
    Makes the winning highscore 0x2000 instead of 0xf600