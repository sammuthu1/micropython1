---
title: Introducing Raspberry Pi Picos to Middle and High School Students
author: J. E. Tannenbaum
author_url: http://github.com/jetannenbaum
author_image_url: https://github.com/jetannenbaum.png
tags: [STEM, MicroPython, Mentor, Raspberry Pi Pico]
hide_table_of_contents: false
---
I'm continuing to mentor at a title 1 school in North Philadelphia.  This time, I introduced a hardware component, the Raspberry Pi Pico.  The parts were purchased through a grant from Optum, so there is no cost to the school or students.  I've spoken to the sponsoring teachers and they agreed to combine the middle school and high school students so I can mentor a weekly club.  This should work better than the previous separate clubs which met every other week.

I'll be onsite for the first meeting.  The teacher has assured me that the students will be able to solder headers onto the pico boards; however, I'm bringing an extra set of pre-soldered boards, just in case.  My son assured me that he soldered boards at that age, so it should work out. (Side note, I had to fix some of his projects).  I soldered projects at a much younger age, but that was not as delicate work.

There will be 10 different labs, each structured to utilize different sections of the pico.  I may add a lab at the end to connect the UART to a BlueTooth receiver, but I'm likely to save that for the bot lab that will [follow](../makerPiRP2040Bot).  The first lab will be fairly simple since it is mostly centered around setting up the environment.  I'll be introducing Thonny as the IDE and Github as the data repository.  The students will solder the headers onto the pico boards and create their first program, blinking the onboard LED.  Once the program runs correctly, they will upload it to their GitHub repository.

The second lab introduces the use of a solderless breadboard and the GPIO pins.  A quick review of how the breadboard works followed by a discussion of the different functions of the pico inputs and outputs.  This lab will concentrate on the GPIO pins for output, controlling LEDs.  The students will connect two LEDs to the pico and, extending the program from the first lab, alternately toggle the LEDS.

I had been in contact with the on-site teacher several times, making sure that he understood the project needs, namely soldering irons, the ability to install Thonny, and access to GitHub.  He assured me that all would be done; however, since I intended to be on-site for the first meeting, I would need certain clearances from the state.  It wasn't a problem since I already had one of the two required, and the second clearance took seconds to obtain (I live a boring life).  I arrived at the school in time to see the last-period class in action and got a tour of the various projects the students had worked on.  The "engineering class" reminded me of the technology education and shop classes that are available in my local school district.

I was prepared for the first hiccup in execution, namely that the soldering irons that the teacher had in his classroom consisted of an old Weller solder gun and a pencil-style soldering iron that didn't heat up.  Not what I expected when I was told the students could solder in class.  Fortunately, I came prepared with headers that were pre-soldered in the pico boards.  I couldn't overcome the second problem though.  The teacher neglected to get clearance to install Thonny onto the student's laptops or allow them to access GitHub.  A lesson to be learned, meet at least one week before the first class to ensure everything is ready to go on the first day with students.  I ordered 4 sets of new soldering irons for the class and we'll try again next week.
