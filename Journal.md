---
title: "Custom-KEEBoard"
github: "https://github.com/Mustafa0801/Custom-KEEBoard/tree/main"
description: "Built a simple and basic keyboard as its my first project in this field. The layout is similar to a 60% layout but some of the sizes are slightly different."
created_at: "2026-09-24"
total_time: "15h 30m"
---

# Journal of designing keyboard

# Planning keyboard, approx 40 minutes (or 2/3 hours), 06-09-2026
This is the initial sketch for my keyboard, along with a photo I used for reference/inspiration.
I created this with the idea in mind that this wasn't final, so I didn't put too much detail.
It's just the general layout and features of the keyboard. 
Perhaps the most ambitious idea is to somehow make the LEDs emit a ripple effect from whichever key is pressed.
Also I currently don't know much about the rasberry pi pico, switches, etc so the placement may be wrong.
<img width="1988" height="1149" alt="image" src="https://fabricate.hackclub-assets.com/710a71cd6f896e5ccbe35945d3dfecebc95a2def07117eee67c66e79fc1fb226/image-png/7adb25d8-e282-4690-b304-f46026c45898.png" />

# First part of creating PCB, approx 2 hours, 06-09-2026
This first photo shows the first switch and diode connection I made:
 \
<img width="960" height="504" alt="Screenshot 2026-09-06 161545" src="https://fabricate.hackclub-assets.com/0a424dacd35110eed8c66333468e8e1926f1fb36cf9fc7fec62676c053264d33/image-png/855fe7e1-6176-41ec-9c79-40035d8b3594.png" />
 \
This was obviously quite simple, however creating the matrix did take some time.\
 \
The first issue was the UI of KiCad, initially it was a bit overwhelming and difficult to understand but eventually I got the hang of it.
Creating the rows was relatively easy, it didn't take as much time as the columns.  
 \
The main and most time-consuming issue was the non-uniformity of the keys; each row had a different number of keys and some of varying lengths. 
Hence each column would not have 5 switches connected to it, so I did struggle a bit to figure out the best arrangement of which switches should be connected to which columns.
There was even one part where I had misaligned the columns such that 3 switches were left without a column, forcing me to have to redo a lot of the wiring.  
 \
Here is the final keyboard matrix I made:
 \
 <img width="728" height="327" alt="Screenshot 2026-09-06 172220" src="https://fabricate.hackclub-assets.com/b17898c567e26e30577f48bf808820f31a8d7c186eee624f9422fc4c3c3561c2/image-png/cdfc2633-8e1b-4614-96ca-33d8af6514e8.png" />
 \
 \
Then I labelled the pins of the Raspberry Pi Pico with the rows and columns, and placed 4 stabilizers for the backspace, shift, enter and spacebar keys.
 \
 <img width="345" height="379" alt="Screenshot 2026-09-06 174126" src="https://fabricate.hackclub-assets.com/f870d953819b0000a06e594d12a7f4955177400dc569ed9ca0b231cdc178677a/image-png/c58014ca-884a-40a4-ac01-7e128af996ad.png" />
 <img width="202" height="299" alt="Screenshot 2026-09-06 174553" src="https://fabricate.hackclub-assets.com/0256db50508ba039f7ce50b5cf41a46f0a9d3bb2b94cb1210e384a8d8e0a74c8/image-png/129a5e54-3f14-4f7a-bd46-e8c9b135e99b.png" />

# Part 2 of making PCB, approx 1 hour, 07-09-2026
This was a big hiccup in my journey. Firstly I added the mounting holes and then assigned the footprints:
 \
<img width="480" height="252" alt="Screenshot 2026-09-07 093700" src="https://fabricate.hackclub-assets.com/7f6a1002e0577c47042e1d6c634b70c60d56cd186bdd19e929a88905152dbbe6/image-png/cc447edb-ba30-4903-b2f5-e2a5d02b73bd.png" />
<img width="480" height="252" alt="Screenshot 2026-09-07 094249" src="https://fabricate.hackclub-assets.com/1adf3b54ff938d3d0da386f4317fcd525fa94d6b3b99e66414b6746d2d1e65a0/image-png/76085ab3-a3ad-4400-b9a5-ff09d57b9f89.png" />
  \
The issue then arose when I imported the schematic to the .pcb file.
  \
Once again it was quite overwhelming initially, but that wasn't the main problem.
I realized I had made mistakes in my design which created unnecessary problems.   

Firstly, as mentioned before, the varied sizes of the keys made things confusing since there isn't that much variation in size in the example in the docs.
Some keys were less than 2u wide but more than 1u, so I was unsure how to space the switches for those since the doc stated to keep consistent spacing.

Secondly, I had left no empty space for the pico, I was originally unaware of this problem because I thought the pico could be in the same area as the switches but this was clearly not possible.
As you can see I placed the pico as such but once I started placing the switches I realized that I could not have the pico and switches overlapping.
  \
<img width="337" height="356" alt="Screenshot 2026-09-07 094833" src="https://fabricate.hackclub-assets.com/edea641e8c02adbd0a674fba25216f4d7be3356cfd61287731434c1b1b8e3c15/image-png/69f7154c-8e91-46f7-88b6-61403d3e28a7.png" />
<img width="437" height="272" alt="Screenshot 2026-09-07 102838" src="https://fabricate.hackclub-assets.com/b35773e9d272de430622852fd32fd6ab2da6427f1cdf9c2bb5f814ae9274900c/image-png/bf900b01-e9d4-4b0f-a2fe-ab8e1c1ade01.png" />
  \
  \
I believe all of this was a product of me not reading through everything before starting, rather just doing it as I went.
With this in mind, I have decided to redesign the keyboard, knowing what I do now. I will also be arranging the keys in a simpler way instead of making it the same as other keyboards.
Failure is simply part of the process.

# September 8, 2026: Redesigning of the keyboard, approx 30 mins (or 1/2 hour)
<!-- fabricate:entry 957 -->

I didn't end up changing the keyboard too much in the end.
The main changes were:  
1. Changing the length of some keys to make the design simpler--the only keys that had a different length were those 2u or longer.
2. Adding extra space on the right for the pico and adding an OLED screen to fill the space.
3. Overall I planned the arrangement and number of keys a little better with the knowledge I had now.
  \
  \
There isn't too much of a difference in the number of keys so the schematic will probably be almost the same, aside from more stabilizers.
Here is the new design:
<img width="1795" height="920" alt="image" src="https://fabricate.hackclub-assets.com/3a14fed43d0f2f282fa6149c712b61cdf39a4652bd825802a356e05c68cbd42f/image-png/2d8f2272-4121-4b7c-ad10-d01a3e7cfc81.png" />

**Total time spent: 30m**

# September 9, 2026: Part 3 of making PCB, approx 2 hours
<!-- fabricate:entry 958 -->

I finished up where I left off,  
First I tweaked the schematic; all I did was add 1 more switch along with 3 more stabilizers (The extra switch did mean I had to rewire some of the columns)
  \
 <img width="592" height="236" alt="Screenshot 2026-09-09 160640" src="https://fabricate.hackclub-assets.com/237401caeec1d8bd9924b893d6c3539c35e97140e8b540dcbd04b91c664ad520/image-png/d9153259-5a54-44b0-b562-09c3771c0637.png" />
  \
  \
Then I finished the layout of the keyboard in the .pcb, adding all the switches and diodes as well.
The process was very repetitive and tedious, and obviously took some time.
The only problem which arose, that I actually noticed while writing this, was that the switch 41 and 42 were ordered as 42 41 in the schematic but 41 42 in the .pcb file, which was an easy fix
  \
  \
<img width="567" height="235" alt="Screenshot 2026-09-09 160803" src="https://fabricate.hackclub-assets.com/89293cf41316e48bf47a038067155e034651dce7fc21d9b38b3fa98d77e9b12d/image-png/4e57ddeb-1d06-4499-80e7-378e3213a99e.png" />

**Total time spent: 2h**

# September 10, 2026: Trying to add LEDs and OLED display, approx 3 hours
<!-- fabricate:entry 959 -->

I decided that now would be the best time to add these extra parts because it would obviously not be feasible later.  
There wasn't much info on how to correctly add them to the schematic so I had to use a lot of google.
I tried many youtube videos but most of them didn't really fit my needs, so I took a lot of help from reddit as well to figure out what exactly I was supposed to do.  
  \
I'll be honest I'm still very unsure if I did anything right, so I have asked in #keeb-help if I am going in the right direction or not. 
Currently nobody has replied so I guess I'll have to wait, which is really unfortunate since I want to finish this project quickly to not bring it down to the wire.  
Moreover, I don't think I can continue with the pcb layout before finalising these extra parts.
  \
Here is the schematic I created (second pic is level shifter for LEDs):
<img width="744" height="278" alt="Screenshot 2026-09-10 191549" src="https://fabricate.hackclub-assets.com/cf10f28ca45b7afeabc8364d62cce4070eb03166dd268729ba2918cfa32e1c9f/image-png/4c4a0fa6-555a-44f8-8af1-1e1a7138a5e4.png" />
<img width="319" height="317" alt="Screenshot 2026-09-10 191602" src="https://fabricate.hackclub-assets.com/bfe3c9e12e0b0f2d4f0d17a47f5fe036b33e14b9b0b4e9146d9779c7dc986a26/image-png/df08b7d3-c307-4058-adb6-c36e0572b5e5.png" />
<img width="230" height="204" alt="Screenshot 2026-09-10 191608" src="https://fabricate.hackclub-assets.com/659fd2e2982eb8aa662ee261939ca9c84f28144aca24a6e061d1c75c490b162f/image-png/84f85225-cef9-49ae-b142-b8f3ebbded70.png" />
<img width="475" height="391" alt="Screenshot 2026-09-10 191629" src="https://fabricate.hackclub-assets.com/e4c01f6cc61cb971ad7c8dabe9de8662d81545da67dcc800d016f02008495a70/image-png/82831e48-565d-4582-be28-517da81fdd4a.png" />

**Total time spent: 3h**

# September 13, 2026: Finalzing these extra parts, approx 1 hour
<!-- fabricate:entry 960 -->

Unfortunately I got no response in #keeb on slack; I ended up looking at the finished keyboard github repos that had been provided to see how they had done it.  
I think they may have confused me even more but my setup was sort of similar so I think I was on the right track. 
 \
I took some more help from google and just tweaked some things in the schematic to make it a bit more organized. Also changed the 74LS125 to 74AHCT125.
Really hope this works!!!
<img width="603" height="383" alt="Screenshot 2026-09-13 164053" src="https://fabricate.hackclub-assets.com/28b7b065186f4a9ba320be4419034334be6d29b7c734a21e2134debb74fb378d/image-png/eaafa543-2e05-40fc-94aa-b165c9a6949e.png" />
<img width="341" height="233" alt="Screenshot 2026-09-13 164104" src="https://fabricate.hackclub-assets.com/fc0ace2cd9f891b5b30fcc000e6f65b859059e09c9e828a1b91ab444c3bd03d9/image-png/d99a420f-499e-4ea9-93d6-026e8c80afb0.png" />

**Total time spent: 1h**

# September 15, 2026: Final part of making PCB, approx 3.5 hours
<!-- fabricate:entry 961 -->

It saddens and disappoints me, but I decided to give up on adding LEDs and an OLED display.
It simply felt like I was biting off more than I could chew, and I didn't want to create more problems for myself.
I decided it would be smarter to make a simpler keyboard for my first project instead of doing too much while not understanding what I'm even doing.  
  \
This meant I could finally move onto finishing the PCB layout; it was quite easy but once again felt redundant connecting all the traces.  
<img width="564" height="225" alt="Screenshot 2026-09-15 153924" src="https://fabricate.hackclub-assets.com/8218a94db7fd53a92aa52ad7c42fa4bb19936acf00c8bc9bdc89349b32cbf648/image-png/da241c4a-e27c-479f-935a-cf98f2854123.png" />
<img width="539" height="217" alt="Screenshot 2026-09-15 155813" src="https://fabricate.hackclub-assets.com/68b6759984406a418e12b095abde062ce68d15885cb921023cf14f75d26815e4/image-png/c9e51a36-7942-4778-9c8f-21e04a6973d8.png" />
  \
  \
I did face some errors when doing the check, involving the stabilizers being too close to any other stabilizers below or above, which was a simple quick fix.  
Here is the model of the board, not sure why the keycaps werent showing by default but I ignored it since I didn't want to manually add the 3D model to each switch.  
  \
<img width="770" height="302" alt="Screenshot 2026-09-15 161716" src="https://fabricate.hackclub-assets.com/5810ada97a2af3bf3098c6ebff836da9ea58268752504eabff3ab406ab6e3c8d/image-png/7f0af40c-6584-4c61-b7cc-9e4ce762cfe3.png" />

**Total time spent: 3h 30m**

# September 20, 2026: Making the keyboard case, approx 3 hours
<!-- fabricate:entry 962 -->

Making the case was relatively easy, the only issue I face was once again trying to figure out the UI of onshape which was a bit confusing.  
I eventually got the hang of it though and was able to breez through most of the steps.
  \
<img width="612" height="237" alt="Screenshot 2026-09-17 175159" src="https://fabricate.hackclub-assets.com/2f7c035255969b6352a2f98b76d6d61b08691ee00e0e6e0a48d547f3e85056cb/image-png/2a679607-4209-460d-88a9-55a10f4a1a17.png" />
<img width="520" height="208" alt="Screenshot 2026-09-19 181111" src="https://fabricate.hackclub-assets.com/78168c568ae91cfb97627f0fb3afcf73813d715e619ff3d2b4a1bd8d2715bfa4/image-png/7c2d845e-9261-4842-b848-72a4f9f230e1.png" />
  \
The only issue I faced was with splitting the case and adding the tongue and groove joints, but after watching a video on youtube I was able to figure it out.
  \
<img width="624" height="284" alt="Screenshot 2026-09-20 124357" src="https://fabricate.hackclub-assets.com/0d58ed92c042f3f92f01c53eab2313e7d6966a611b7d8acf9ed67a77654f2745/image-png/3f5f19a7-f51e-48a7-b194-df5eb54c8649.png" />

  \
  Now onto just adding everything to the repo and then submitting!

**Total time spent: 3h**

# November 1, 2026: fixed all issues with previous ship
<!-- fabricate:entry 1788 -->

made all the change that it was sent back for, the case was the only thing that took time since it had to be almost completely redone.
I had misread the guide and made switch cutouts in the base instead of making a top plate, so I did that properly. The guide didnt mention cutouts for stabilizers but I attempted to do those too and I hope its correct. Also added one switch and keycap just too see if it fits properly, didnt add every switch cuz it would take too much time
![](https://fabricate.hackclub-assets.com/3de659c0f2f7b8f5369ec0efb90776e52fe21b520f690d944fc3ece808b4f891/image-png/FIXED%20final%20case%20other%20angle.png)
![](https://fabricate.hackclub-assets.com/c4196ee5b7bdf7b8becd802a21a3a8c99e41685a2daabbbb82989e33c868ea15/image-png/FIXED%20final%20case.png)

**Total time spent: 2h**

# November 4, 2026: updated and optimized bom
<!-- fabricate:entry 2143 -->

fixed the bom since i forgot to update 3d printing charges for the new case. I checked quite a few sources for pcb manafacturing but a lot of websites didnt seem reliable and I found other people on reddit also saying that jlc is generally the best, so I decided to stick with that. However when I made the cart this time, I got a bigger discount coupon for some reason so the price was less.
![](https://fabricate.hackclub-assets.com/dbc073f86dec0f988120147e36dba86251b223cf1a750834442a9886130ff5ef/image-png/image.png)

**Total time spent: 30m**
