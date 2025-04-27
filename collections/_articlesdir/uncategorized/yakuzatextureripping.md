---
title: how to rip textures in yakuza 7
---

BECAUSE I KEEP FORGETTING HOW TO DO IT!!!

## materials

- yakuza 7 steam download
- windows pc
- Kaplas80's [ParManager](https://github.com/Kaplas80/ParManager) to unpack the game's PAR files
- a program that can open/convert the game's DDS images into useable PNGs, i'm using [krita](https://krita.org/en/) (my free, open source drawing program of choice!) including...
- Sepera-okeq's [Krita DDS Evrika Plugin](https://github.com/Sepera-okeq/DDS-Evrika-Plugin)

## step 1: open game directory

in file explorer, go to wherever you have the game downloaded, and into its data folder. for me, it's...

C:\Program Files (x86)\Steam\steamapps\common\Yakuza Like a Dragon\runtime\media\data

you'll see a bunch of folders, PAR files, and CFG files.

here we'll look at "ui.yazawa.en.par", which contains ui textures for the english game, among other things.

(textures include restaurant foods, equipment icons, enemy and employee portraits, all kinds of buttons, and even running pixel ichiban from the business minigame LOL)

## step 2: preview PAR file contents

(to download ParManager from its github page, scroll down the righthand sidebar and click "releases", then grab the correct ZIP file for your operating system) (somehow i always forget where the releases are)

extract the ParManager "ParTool.exe" and place it somewhere easily accessible, such as your desktop

open command prompt

- drag and drop the "ParTool.exe" icon into command prompt. this will write down its path.
- after the path, type a space, then type "list" (without quotes), then type another space
- drag and drop the "ui.yazawa.en.par" file into command prompt. again, this will write down its path.

the line should look like this: "[partool path] list [PAR file path]". hit enter!

command prompt will return a (VERY LONG) list of every file inside your chosen PAR file. this is how you preview the contents before unpacking. ex: if you want 3d character models, you'd look for GMD files, i think.

(hint: you can also add " -r" (without quotes) to the end of your command to recursively list the contents of nested PAR files)

## step 3: unpack PAR file contents

once you've found the package you want, do the same command as step 2, but without "list"

- drag and drop the "ParTool.exe" icon into command prompt. this will write down its path.
- after the path, type a space
- drag and drop the "ui.yazawa.en.par" file into command prompt. again, this will write down its path.

the line should look like this: "[partool path] [PAR file path]". hit enter!

command prompt will unpack everything into a new folder "ui.yazawa.en.par.unpack". it'll show up in the directory of the PAR file you chose, so you should probably move it somewhere else in case it interferes with the game.

(hint: you can also add " -r" (without quotes) to the end of your command to recursively unpack the contents of nested PAR files)

## step 4: preview textures

crack open "ui.yazawa.en.par.unpack"! open "en", then open "texture".

it's full of DDS images! for me, file explorer shows proper thumbnails for most all of them, so i go to view -> extra large icons to get a better look as i scroll through.

once you find a pic you wanna open/convert...

## step 5: convert texture

again, i'm using krita + DDS Evrika Plugin... the plugin github page has an installation tutorial around halfway down, so just follow that one, i don't feel like typing it sorry {{site.data.emojis.reigen}}

once you've opened krita with the plugin properly installed...

in the top bar, go to tools -> scripts -> import DDS

navigate to your "ui.yazawa.en.par.unpack" folder. you can also copy/paste the path from its file explorer window!

select the image you wanna open. you can also copy/paste the filename into the box! (sadly, it seems you can only open one image at a time)

click open, select the image format you want (i prefer PNGs), then click ok.

the image will open, yippee!

ctrl + shift + s to "save as", then save it where you wanna save it!

## step 6: congratulations!

you can now open/edit/lovingly stare at your images!

i was able to grab y0 and y5 textures just fine using the same method. happy browsing!!! 😎

---

## extra links i've used, for further reading

- [Achiev4ble's Small modding info-dump/guide - Yakuza Kiwami](https://steamcommunity.com/sharedfiles/filedetails/?id=2813243580): focused on yk1, but has great filetype info
- [Drogean's PC Texture Modding Guide](https://steamcommunity.com/app/638970/discussions/0/1739964766316515626/): focused on y0, but again same principles apply
- [SteamyJ's PS2 Sprite/Texture Ripping for 2022](https://www.vg-resource.com/thread-40768.html): if you wanna browse y1's textures (I FORGOT HOW TO DO THIS ALSO. it's a different method that uses an emulator)
- [some info on how y0 chunks/folders aren't named properly LOL](https://www.reddit.com/r/yakuzagames/comments/157ok01/need_help_getting_yakuza_0_city_textures/)
