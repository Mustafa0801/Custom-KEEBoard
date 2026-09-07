# First part of creating PCB, approx 2 hours, 06-09-2026
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

