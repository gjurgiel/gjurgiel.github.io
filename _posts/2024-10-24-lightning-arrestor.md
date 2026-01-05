---
layout: post
title: "W1XM Lightning Arrestor"
category: club-projects
---

The [MIT UHF Repeater Association](https://web.mit.edu/w1xm/www/) maintains and operates a VHF/UHF amateur radio station on top of the Green Building (building 54) along with a UHF Repeater and the Radome, a radar dish primarily used for radio astronomy.

![MIT Green Building]({{ site.baseurl }}/assets/2024-10-24-lightning-arrestor-files/bldg_54.jpg "Building 54")

As with all radio equipment on top of a tall building, there is a string possibility of lighting strikes damaging equipment. Each of the antennas mounted on the roof have their own commercial lightning arrestors designed for protecting our equipment from a direct strike. However many other auxiliary controls cables, such as those for antenna rotors, and LNA switching, also need some protection. This protection does not need to withstand a direct strike which would likely hit one of the buildings many lightning rods of another protected antenna, but they would likely see a current and voltage spike from the large E and B fields such a strike could produce. Therefor we designed a small DIN rail mount board to provide additional protection to the rotor, LNA switching controllers, and any other connections we may make to equipment on the roof.



The design is rather simple, based off a sketch by fellow club member Daniel Sheen. It is composed of a TVS diode, inductor, and a MOV. The inductor is intended to hold off large spikes in current, while the TVS and MOV clamp the voltage. The TVS diode is on the unprotected side of the inductor as it should be able to switch quickly shunting current from any fast voltage spikes. The MOV is on the protected side of the inductor since we expect it to switch slower byt be able to handle more higher current for longer. For this reason we choose components such that the TVS had a higher switching voltage than teh MOV.

![Lightning Arrestor Schematic Sketch]({{ site.baseurl }}/assets/2024-10-24-lightning-arrestor-files/Lightning_Arrestor_Schematic_Sketch.jpeg "Schematic Sketch")

Using this design, I did the component selection and PCB layout for these board which can be found at the clubs git repository [here](https://github.mit.edu/w1xm/W1XM_Lightning_Arrestor_Board) (However it may only be viewable internal to MIT). The boards are currently in service and the roof has experienced several lighting strikes and none of the protected equipment has been damaged, however without direct comparison it is hard to say if the board had a significant impact.

![Lightning Arrestor Board]({{ site.baseurl }}/assets/2024-10-24-lightning-arrestor-files/W1XM_Lightning_Arrestor_3D_Rendering.png "Lighting Arrestor Board")