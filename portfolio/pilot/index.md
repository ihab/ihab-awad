---
layout: page
title: Pilot
---

My long-standing personal project, creating a novel aircraft instrument, has been very rewarding and eductional for me.



Around the time I started my [flight training](../pilot/) at Palo Alto Airport (KPAO), a Boeing 777-200ER, Asiana Airlines flight 214, collided with the seawall near the threshold of Runway 28 Left at San Francisco Airport (KSFO). The aircraft was in perfect condition; but it was too low and slow on short final, and for various reasons, the flight crew did not correct this condition until it was too late. Happening as it did near where I lived, in a spot visible from the city park where my family and I would often go to watch the airplanes land, this made quite an impression on me.

The 


Every such incident is an opportunity for us to learn, and I never assume I am immune from the mistakes of others. So I set out to think of what I could build, for my own flying, that could help me achieve better awareness of my aerodynamic state despite the many other tasks (traffic, radio, ...) that I as a pilot must also attend to. This led me down a path that has taken many years, and which I hope you will follow with me.

Many friends helped me, including Paul Eastham, the owner and builder of N42PE, a lovely Van's RV-9A. We patched wires into his panel, did test flights, and tried out ideas together.



Eventually, in 2016, I came across the EAA Founder's Innovation Prize competition, and I submitted my entry. Much to my delight and honor, Airball was the first prize winner! The encouragement and funding from this event was very important in helping me continue my work.


Since then, I have made a lot of progress, and built a whole array of successful prototypes with the help of many amazing collaborators. I believe we are at the threshold of a completely new way to teach and practice flying -- one grounded in aviation's earliest ideas, and enabled by our latest technology. I hope you will join me in my journey of discovery.


As I learned to fly, I started reading Stick and Rudder, by Wolfgang Langeweische. In it, he describes the relative wind as:

This so-called "Relative Wind," this onrush of air, this "wind of flight," always comes at the airplane from the direction toward which the airplane is moving.

As pilots, we are taught to think of three quantities: Angle of attack, angle of yaw, and airspeed. But these are just the "numbers" that describe the relative wind vector. Langeweische spent a lot of time in his book trying to get us to visualize it, using imaginary arrows and windsocks on cartoon airplanes:





The stakes are high. As Langewische's illustrations show, where the wind is coming from is not where the nose is pointed relative to the ground. Whether it's the airliner that crashed in San Francisco, or the Cirrus SR20 that crashed in Houston Hobby Airport in 2016, or any of a number of such accidents, pilots time and time again, in perfect weather, lose awareness of the relative wind, with fatal results.

We can describe the relative wind by three numbers. The indicated airspeed gives us the strength of the relative wind. The angle of sideslip gives us its direction to the left or to the right. And the angle of attack gives us its direction above or below the nose. We are accustomed to the first two quantities in most aircraft from the ASI and the turn and slip "ball". Glider pilots, wanting a more sensitive yaw signal, measure it directly using a "yaw string" taped to the canopy. And (all too infrequently), we have the angle of attack represented on yet another instrument.





But we are working too hard! The relative wind is a vector quantity. A vector is just a quantity and a direction. We are getting mired in the numbers we used to describe the vector and forgetting that it is all really quite simple. Where is the wind coming from? No numbers -- just point in that direction! And how hard is it blowing? Again, no numbers -- is it big or little?


Can it be that simple? We believe it can! Stay tuned to hear more!

Last time, we talked about the relative wind. In the 1940s, getting a good measurement of this or any other aerodynamic quantity was rocket science. Think of the piece of metal tube sticking out of a Citabria or Aeronca to get an idea of the technology of the time.


But actual rocket scientists at NASA had a solution -- the Q Ball. This flew on the nose of both the Bell X-15 and the Saturn V rockets, and consisted of a ball with a series of holes, and motors to move it around. The air pressure on the holes would tell the system if the ball was facing directly into the wind, and the motors would rotate it as needed. And so these vehicles had an exact measurement of where the air was blowing from, and how hard.

This is what the Q Ball looked like on the nose of the X-15. If you zoom in, you can see the tiny holes on the metal ball. And the X-15 control panel had lots of tapes and readouts with technical terminology in Greek alphabet to display all this information!




It turns out that, if we don't plan to be supersonic, we can achieve the same effect with a stationary ball with holes in it. If we carefully measure the pressures at the different holes and do some math, we can "sniff" the direction and strength of the relative wind. And in fact, this is also common: lots of instruments used for flight testing employ this technique.


These instruments often need fancy calibration and cost thousands of dollars. How can we make them cheaper? Well, three ways. First of all, if we make the "ball nose" larger, then we can get reasonably consistent results without having to do fancy calibrations. Second, we can 3D print the parts rather than use expensive machining and welding. And third, hobby electronics and sensors are amazingly cheap these days! We did all these things, and created the Airball probe. Here is a prototype, and our design for a more productionized version:



This sends out relative wind information 20 times per second, and the battery lasts all day. It's all Open Source, meaning the blueprints and software are out there for anyone to use, free of charge. Here is our 3D printer cranking out a set of "ball noses", and a couple of probes kitted out on our workbench.



Our "ball nose" is 2 inches in diameter, which is no larger than action cameras that people stick on their airplanes all the time. We fly with this kind of setup regularly on our test ship, N291DR, using a 3D printed strut mount of our own design. It works pretty slick.


So there is no barrier to this information being at everyone's disposal. But what then? Do we all get X-15 control panels with Greek letters on them? We don't think so. We'll talk about that next time.


