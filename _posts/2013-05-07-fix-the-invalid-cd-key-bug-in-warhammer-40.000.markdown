---
  layout: post
  title: "Fix the invalid CD key bug in Warhammer 40.000"
  categories: archive
---

Warhammer 40.000 is a great RTS series for the PC. What's good for us Linux people is that it works excellent under Wine. I bought the "Warhammer 40K - Dawn of War Anthology", I believe it's called Dawn of War Platinum Edition on Steam. It really is an awesome game and it should be able to find it fairly cheap (I bought it at a "local" online retailer for about $20, however the USD is really low compared to the SEK right now so it might sound cheeper to me then it does to you). There is a new expansion out called Soul Storm but I havn't bought it yet. Dawn of War 2 is under development as well.

The anthology edition contains Warhammer 40K - Dawn of War and Winter Assault and Dark Crusade. Installing Dawn of War and Winter Assault went just fine but I ran into some trouble with Dark Crusade. Dark Crusade is a expansion but they've made it into a stand alone game so you can play it without having Dawn of War or Winter Assault installed (or owned). However, if you wish to play the races from Dawn of War and Winter Assault you have to enter the CD-keys from those games.

When I tried to enter these CD-keys I got the error message saying "Your CD-key seems to be invalid. Please try again." even though I have bought the games and the keys are valid. I Googled it and found a lot of people had the same problem (on the Windows side as well) but the only solution they had was to re-install it. I did not feel like re-installing it because it's a pain in the ass and you have to switch between 6 CDs.

I felt that there could be something messy in the Windows Registry Editor (open it with wine using "wine regedit") since they recomended a re-install so I started searching through it and found the strings which caused this problem. It seems as the Winter Assault and Dawn of War keys for Dark Crusade is located in "HKEY\_LOCAL\_MACHINE/Software/THQ/Dawn of War - Dark Crusade". However, the same strings can also be found in "HKEY\_LOCAL\_MACHINE/Software/THQ/Dawn of War" and it looks like the game checks these strings as well.

For some reason these strings just contained zeros so what you have to do is to change these strings to your CD-keys in the "Dawn Of War"-folder (not "Dawn of War - Dark Crusade"!). The CD-key string for Dawn of War is named CDKEY (16 chars) and the Winter Assault is named CDKEY_WXP (20 chars). I have also read that some recieved a 16 chars long CD-key for Winter Assault. This seems to be a printing error and cant be fixed this way.

Start the game again after you've entered your CD-keys (with the "-" between them ofcourse). You will be prompted for you CD-keys in the game once more but they should report as valid. You can enter them directly in to you "Dawn of War - Dark Crusade" registry folder as well. The Dawn of War string is named W40KCDKEY and the Winter Assault is named WXPCDKEY (and the CDKEY-string in this folder is for the Dark Crusade game itself). I have heard that the Soul Storm has a similair problem but since I havn't bought it yet I cant tell you how to fix it. My guess is that it is pretty much the same deal.

###Update:

For Windows 7 64-bit: "HKEY\_LOCAL\_MACHINE/Software/Wow6432Node/THQ/"