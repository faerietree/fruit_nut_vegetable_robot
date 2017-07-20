Fruit Nut Vegetable Carer
==========

Open design and documentation for an agricultural robot similar in function to the AgroKruh, invented by Ján Šlinský, but simpler, cheaper (10K€ instead of 60K+€) and highly automated reusing the worlddevelopment pivot: <a href="http://github.com/faerietree/manipulator">industrial robot</a>.


<a href="environment/README.md">Environment</a>
---
<img src="environment/20170510_121423.jpg" alt=""/>

Overview
-------

<img src="high_level_overview.jpg" alt="high_level_overview"/>


###Variants
* [deprecated] Operates on a circular field. (Robot attached to linear slider which itself is attached to a rotational center joint.) [see AgroKruh]
* [deprecated] Operates on a linear field. (Robot attached to linear slider.) [see FarmBot]
* <a href="http://github.com/faerietree/manipulator">5 axis manipulator</a> for static usage
* <a href="http://github.com/faerietree/walker">walker</a> + <a href="http://github.com/faerietree/manipulator">manipulator</a> for dynamic|infinite field size deployment.



Requirements:
----

* Operate on an as big as convenient ground surface to produce enough food to feed at least a dozen people (12).
* Resolution high enough to reach as much of this surface as possible and useful.
* Prepare soil for growing plants on this surface of operation.
* Grow plants on this surface of operation.
* Allow manual intervention where and when appropriate.
* Cultivate and nurse ground and plants for fulfilling all requirements of plants (soil nutrients, light, water, space).



Example: AgroKruh (by Ján Šlinský)
===

* Can automate 80% of the required work.
* Radial arm length 18m:
  surface of operation = PI * 18^2 = ca 1017m²
* Propulsion power input: 0,75 KW (typical electrical system efficiency)
* Power / year = 4000KW for 15 fields (radial arm can be mounted on several field center point slots).
* => 267 kWyear / field.
* Harvest: 2 tons / field.
* 1 robotic unit for 3..5 fields (also see satellite images)



Documentation
---

https://vimeo.com/99343531

All implements:
http://www.youtube.com/watch?v=mYrJ0BJ4Qak (English)
https://www.youtube.com/watch?v=nStEuHWJE-o (sk)

http://www.google.de/maps/@48.1699222,17.3968533,339m/data=!3m1!1e3

http://opensourceecology.org/w/images/1/1c/CEPTA_-_Introducing_AGROKRUH.pdf



###Port

http://www.youtube.com/watch?v=IMbGA-nOW64#t=53

Function: Fixed installation holding a bearing. Accept 480VAC 3 phase electricity. Accept water. Optional electrical wiring for data (e.g. network).

Immobile due to high mass or good fixture to the ground.


###Rotary bearing

Function: Holding and rotary joint of the radial arm. Relays the connection of the port to the sliding element, tool.

Realisation: http://www.youtube.com/watch?v=IMbGA-nOW64#t=5m35

* optional incremental encoder (for feedback)
* Electrical sliding contacts:
  5x (L1-3, Neutral, PE/Grounding),
* Build out of copper (Cu) tube, carbon, plastic,
* 16A current rating (Attention false friend: The longer the wire, the thicker it must be.).
* Sprocket/Gear for radial sliding movement chain.

###Radial slider

Function: Hold tool/person, absorb torque and forces.

Realisation:

* 3 sided,
* if required attach support wheel / stabiliser.
* Forklift beam, or lattice beam. Or custom weld.


Main Propulsion (tangential direction)
-----

Function: Circular movement and powering other actuators/tools.

Realisation:

http://www.youtube.com/watch?v=Von3EgRGutw#t=1m35
http://www.youtube.com/watch?v=Von3EgRGutw#t=2m01
Pedal propulsion: http://www.agrokruh.sk/node/33
3phase motor + transmission (prototype utilizes 750W motor).
Alternative: Custom wound motor, wound for torque and low RPM. Also possible is direct drive with an AC motor similar to how it's done in electric vehicles.

A main wheel with two stabilizing secondary wheels.
Alternative: Two main wheels.


Propulsion in radial (sliding) direction (speed sets spirale movement)
-----

Ján Šlinský coupled the rotary movement in tangential direction with and uses this as energy source to move the slider. This is possible by fixing e.g. a chain in the center, such that the chain must rotate when the arm is moving around the center (due to the motor attached to outer tip).
The center attachment method, e.g. sprocket/pulley diameter sets speed and gauge/track width of the spirale.


Tool holder
----

http://www.youtube.com/watch?v=IMbGA-nOW64#t=4m30
http://www.youtube.com/watch?v=IMbGA-nOW64#t=6m55

* Self-constraining transmission ratio + stepper motor,
* Chain- or cable drive with feedback of the optional incremental encoder, to compensate for slip of the main drive (in tangential direction which is coupled to the sliding movement and thus the sliding speed varies).
* Position detection via markers on the traversing beam (slider holding structure).
    inductive, rfid, optical or position measurement (relative to e.g. center).
* High speed mode for returning to tool home position.
* Power outlet (for electrical tools),
* And/or PTO (power take-off) or pulley,
* Protection for wiring and (water) piping,
* Sliding plain bearing or rollers,
* Standardised Tool interface/coupler (e.g. of 1-axle tractors),
* Solenoid valve for water control.



Tools
---

* Modified hand tools.
* Tools of 1-axle tractors.
* Custom-built.

Overview of the used tools in Slovakia:
https://www.youtube.com/watch?v=nStEuHWJE-o



###Striding spades

https://www.youtube.com/watch?v=2Rb5o1D7laI
http://www.agrokruh.sk/node/954



###Tiller

* Tillage: https://www.youtube.com/watch?v=FOb1tvbV8-w
* Weed control: https://www.youtube.com/watch?v=Qy5D3NGZPzk ('Beikraut' is the correct term. Thanks! 'Unkraut' is misleading, creates sentiments like the 'Fischreiher' which is now called 'Graureiher'.)


###Grubber (Sowing/seeding preparation tool)

http://www.youtube.com/watch?v=Von3EgRGutw#t=1m35

http://www.youtube.com/watch?v=Von3EgRGutw#t=3m55


###Electronics (optional)

For automating task (e.g. watering time + amount).

* uC (microcontroller),
* inverter,
* timer,
* communication interface (e.g. WLAN or 2-wire bus I2C or CAN).




Sammlung
---

###Ján Šlinský

An ecological farmer. He has a diploma from the Mendel University in Brno, Faculty of Gardening. Jan Šlinský is the author of the agricultural system Agrokruh, whose main idea is to produce vegetables sustainably and ecologically. He has also built a net of local buyers, thus supporting local trade in his area. Jan Šlinský is a practical and witty person with a well-developed common sense.

”Enough talk, it's time to act. It is not in the power of an individual to save the entire planet. However, each of us can help a particular place on Earth. But he must be sufficiently educated and skilled, and he has to love the place he is aiding.“

<!-- phone: 0918 655 564 -->

Talk TEDx Bratislava (english subtitles):
http://www.youtube.com/watch?v=ZwP3A6z4sFc

HD version of TEDx Talk:
http://www.youtube.com/watch?v=2P7MGNLz5xE



Discussion
----
http://forum.opensourceecology.de/viewtopic.php?f=28&t=632&p=3504#p3504

https://groups.google.com/forum/#!forum/agrocircle




###Relevant SCAD tutorials:

Export scad files to step using freecad:
http://forum.lulzbot.com/viewtopic.php?f=8&t=243




