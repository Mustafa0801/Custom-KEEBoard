# Part 2 of making PCB, approx 1 hour, 07-09-2026

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
