# Journal of designing keyboard

## Planning keyboard, approx 40 minutes (or 2/3 hours), 06-09-2026
This is the initial sketch for my keyboard, along with a photo I used for reference/inspiration.
I created this with the idea in mind that this wasn't final, so I didn't put too much detail.
It's just the general layout and features of the keyboard. 
Perhaps the most ambitious idea is to somehow make the LEDs emit a ripple effect from whichever key is pressed.
Also I currently don't know much about the rasberry pi pico, switches, etc so the placement may be wrong.
<img width="1988" height="1149" alt="image" src="https://github.com/user-attachments/assets/7adb25d8-e282-4690-b304-f46026c45898" />

## First part of creating PCB, approx 2 hours, 06-09-2026
This first photo shows the first switch and diode connection I made:
 \
<img width="960" height="504" alt="Screenshot 2026-09-06 161545" src="https://github.com/user-attachments/assets/855fe7e1-6176-41ec-9c79-40035d8b3594" />
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
 <img width="728" height="327" alt="Screenshot 2026-09-06 172220" src="https://github.com/user-attachments/assets/cdfc2633-8e1b-4614-96ca-33d8af6514e8" />
 \
 \
Then I labelled the pins of the Raspberry Pi Pico with the rows and columns, and placed 4 stabilizers for the backspace, shift, enter and spacebar keys.
 \
 <img width="345" height="379" alt="Screenshot 2026-09-06 174126" src="https://github.com/user-attachments/assets/c58014ca-884a-40a4-ac01-7e128af996ad" />
 <img width="202" height="299" alt="Screenshot 2026-09-06 174553" src="https://github.com/user-attachments/assets/129a5e54-3f14-4f7a-bd46-e8c9b135e99b" />

## Part 2 of making PCB, approx 1 hour, 07-09-2026
This was a big hiccup in my journey. Firstly I added the mounting holes and then assigned the footprints:
 \
<img width="480" height="252" alt="Screenshot 2026-09-07 093700" src="https://github.com/user-attachments/assets/cc447edb-ba30-4903-b2f5-e2a5d02b73bd" />
<img width="480" height="252" alt="Screenshot 2026-09-07 094249" src="https://github.com/user-attachments/assets/76085ab3-a3ad-4400-b9a5-ff09d57b9f89" />
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
<img width="337" height="356" alt="Screenshot 2026-09-07 094833" src="https://github.com/user-attachments/assets/69f7154c-8e91-46f7-88b6-61403d3e28a7" />
<img width="437" height="272" alt="Screenshot 2026-09-07 102838" src="https://github.com/user-attachments/assets/bf900b01-e9d4-4b0f-a2fe-ab8e1c1ade01" />
  \
  \
I believe all of this was a product of me not reading through everything before starting, rather just doing it as I went.
With this in mind, I have decided to redesign the keyboard, knowing what I do now. I will also be arranging the keys in a simpler way instead of making it the same as other keyboards.
Failure is simply part of the process.

## Redesigning of the keyboard, approx 30 mins (or 1/2 hour), 08/09/2026
I didn't end up changing the keyboard too much in the end.
The main changes were:  
1. Changing the length of some keys to make the design simpler--the only keys that had a different length were those 2u or longer.
2. Adding extra space on the right for the pico and adding an OLED screen to fill the space.
3. Overall I planned the arrangement and number of keys a little better with the knowledge I had now.
  \
  \
There isn't too much of a difference in the number of keys so the schematic will probably be almost the same, aside from more stabilizers.
Here is the new design:
<img width="1795" height="920" alt="image" src="https://github.com/user-attachments/assets/2d8f2272-4121-4b7c-ad10-d01a3e7cfc81" />

## Part 3 of making PCB, approx 2 hours, 09/09/2026
I finished up where I left off,  
First I tweaked the schematic; all I did was add 1 more switch along with 3 more stabilizers (The extra switch did mean I had to rewire some of the columns)
  \
 <img width="592" height="236" alt="Screenshot 2026-09-09 160640" src="https://github.com/user-attachments/assets/d9153259-5a54-44b0-b562-09c3771c0637" />
  \
  \
Then I finished the layout of the keyboard in the .pcb, adding all the switches and diodes as well.
The process was very repetitive and tedious, and obviously took some time.
The only problem which arose, that I actually noticed while writing this, was that the switch 41 and 42 were ordered as 42 41 in the schematic but 41 42 in the .pcb file, which was an easy fix
  \
  \
<img width="567" height="235" alt="Screenshot 2026-09-09 160803" src="https://github.com/user-attachments/assets/4e57ddeb-1d06-4499-80e7-378e3213a99e" />

## Trying to add LEDs and OLED display, approx 3 hours, 10/09/2026
I decided that now would be the best time to add these extra parts because it would obviously not be feasible later.  
There wasn't much info on how to correctly add them to the schematic so I had to use a lot of google.
I tried many youtube videos but most of them didn't really fit my needs, so I took a lot of help from reddit as well to figure out what exactly I was supposed to do.  
  \
I'll be honest I'm still very unsure if I did anything right, so I have asked in #keeb-help if I am going in the right direction or not. 
Currently nobody has replied so I guess I'll have to wait, which is really unfortunate since I want to finish this project quickly to not bring it down to the wire.  
Moreover, I don't think I can continue with the pcb layout before finalising these extra parts.
  \
Here is the schematic I created (second pic is level shifter for LEDs):
<img width="744" height="278" alt="Screenshot 2026-09-10 191549" src="https://github.com/user-attachments/assets/4c4a0fa6-555a-44f8-8af1-1e1a7138a5e4" />
<img width="319" height="317" alt="Screenshot 2026-09-10 191602" src="https://github.com/user-attachments/assets/df08b7d3-c307-4058-adb6-c36e0572b5e5" />
<img width="230" height="204" alt="Screenshot 2026-09-10 191608" src="https://github.com/user-attachments/assets/84f85225-cef9-49ae-b142-b8f3ebbded70" />
<img width="475" height="391" alt="Screenshot 2026-09-10 191629" src="https://github.com/user-attachments/assets/82831e48-565d-4582-be28-517da81fdd4a" />

## Finalzing these extra parts, approx 1 hour, 13/09/2026
Unfortunately I got no response in #keeb on slack; I ended up looking at the finished keyboard github repos that had been provided to see how they had done it.  
I think they may have confused me even more but my setup was sort of similar so I think I was on the right track. 
 \
I took some more help from google and just tweaked some things in the schematic to make it a bit more organized. Also changed the 74LS125 to 74AHCT125.
Really hope this works!!!
<img width="603" height="383" alt="Screenshot 2026-09-13 164053" src="https://github.com/user-attachments/assets/eaafa543-2e05-40fc-94aa-b165c9a6949e" />
<img width="341" height="233" alt="Screenshot 2026-09-13 164104" src="https://github.com/user-attachments/assets/d99a420f-499e-4ea9-93d6-026e8c80afb0" />

## Final part of making PCB, approx 3.5 hours, 15/09/2026
It saddens and disappoints me, but I decided to give up on adding LEDs and an OLED display.
It simply felt like I was biting off more than I could chew, and I didn't want to create more problems for myself.
I decided it would be smarter to make a simpler keyboard for my first project instead of doing too much while not understanding what I'm even doing.  
  \
This meant I could finally move onto finishing the PCB layout; it was quite easy but once again felt redundant connecting all the traces.  
<img width="564" height="225" alt="Screenshot 2026-09-15 153924" src="https://github.com/user-attachments/assets/da241c4a-e27c-479f-935a-cf98f2854123" />
<img width="539" height="217" alt="Screenshot 2026-09-15 155813" src="https://github.com/user-attachments/assets/c9e51a36-7942-4778-9c8f-21e04a6973d8" />
  \
  \
I did face some errors when doing the check, involving the stabilizers being too close to any other stabilizers below or above, which was a simple quick fix.  
Here is the model of the board, not sure why the keycaps werent showing by default but I ignored it since I didn't want to manually add the 3D model to each switch.  
  \
<img width="770" height="302" alt="Screenshot 2026-09-15 161716" src="https://github.com/user-attachments/assets/7f0af40c-6584-4c61-b7cc-9e4ce762cfe3" />

## Making the keyboard case, approx 3 hours, 20/09/2026
Making the case was relatively easy, the only issue I face was once again trying to figure out the UI of onshape which was a bit confusing.  
I eventually got the hang of it though and was able to breez through most of the steps.
  \
<img width="612" height="237" alt="Screenshot 2026-09-17 175159" src="https://github.com/user-attachments/assets/2a679607-4209-460d-88a9-55a10f4a1a17" />
<img width="520" height="208" alt="Screenshot 2026-09-19 181111" src="https://github.com/user-attachments/assets/7c2d845e-9261-4842-b848-72a4f9f230e1" />
  \
The only issue I faced was with splitting the case and adding the tongue and groove joints, but after watching a video on youtube I was able to figure it out.
  \
<img width="624" height="284" alt="Screenshot 2026-09-20 124357" src="https://github.com/user-attachments/assets/3f5f19a7-f51e-48a7-b194-df5eb54c8649" />

  \
  Now onto just adding everything to the repo and then submitting!
