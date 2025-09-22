---
layout: page
title: Airball
---

My long-standing personal project, creating a novel aircraft instrument, has been very rewarding and eductional for me.

## Inflight loss of control

Loss of control inflight is an important problem leading to injuries and fatalities in aviation. Very broadly, this occurs when the airplane is flown in such a way that its wings can no longer be effective at controlling where it goes (including, keeping it up in the air). The effectiveness of the wings is in turn dependent on the _relative wind_ -- the strength and direction of the air flow as viewed from the position of the airplane.

Consider an airplane cruising along. It is likely moving straight ahead through the air, and the air flow impinging on it is, conversely, coming from straight ahead:

{% include gallery.md imgs="relative-wind-cruise.png" %}

Now consider an airplane preparing to land. It is likely moving slowly, and flying downwards. However, the way it is moving _through the air_ is such that it is _mushing_ downwards, and the air flow impinging on it is weaker and comes much more from below.

{% include gallery.md imgs="relative-wind-landing.png" %}

The basic idea here is: _airplanes are not necessarily moving where they are pointed_. This is intentional. But under certain conditions, particularly when slow or when making sharp turns, the direction of the airflow can result in an [aerodynamic stall](https://en.wikipedia.org/wiki/Stall_%28fluid_dynamics%29) where the wings lose lift -- i.e., lose the ability to control the airplane. This condition can cause the airplane to drop suddenly, and sometimes even to spin out of control. And if this happens near the ground, a pilot may not have time to react properly. Click on the below image for a video of that happening at a safe height:

{% include imagelink.md img="spin.png" link="https://www.youtube.com/watch?v=9rBRKj3x3I0" %}

## Relative wind visualization

In a typical airplane, a pilot sees something like this:

{% include gallery.md imgs="pilot-view.png" %}

Because air is invisible, the all-important relative wind is not clear; it has to be interpreted from numerous instruments and readouts. But the relative wind is a _vector_. What if we visualized it as such? The orientation relative to the nose of the airplane can be visualized by the location of a dot, as though the pilot could see the vector out the window:

{% include gallery.md imgs="relative-wind-pilot-view.png" %}

And the strength of the relative wind can be represented by the size of the dot, as though the vector were growing and shrinking in the windshield:

{% include gallery.md imgs="relative-wind-pilot-view-strength.png" %}

This is the basis of my project: to _measure_ the relative wind with fidelity, and _visualize_ it intuitively.

## X-Plane and Google Glass

The first iteration of this idea was an Android app, using flight data broadcast via UDP from the [X-Plane](https://www.x-plane.com/) flight simulator. Here is the app, and my son "flying" it:

{% include gallery.md imgs="demo-xplane-panel.jpg,demo-xplane-aden.jpg" %}

What followed was a "science fair" style demo rig, for my pilot friends to try out.

{% include gallery.md imgs="demo-science-fair.jpg" %}

Another demo was to run the Android app in Google Glass, using Bluetooth and another Android device to broadcast actual flight data from my friend Paul Eastham's airplane:

{% include gallery.md imgs="paul-n42pe-glass.jpg" %}

## EAA Founder's Innovation Prize

I entered my idea as a proposal to a competition held by the Experimental Aircraft Association, and [won first prize](https://www.eaa.org/airventure/eaa-airventure-news-and-multimedia/eaa-airventure-news/eaa-airventure-oshkosh/07-27-2016-airball-wins). This provided a boost of confidence -- and some funding -- to proceed.

{% include gallery.md imgs="ihab-fip.jpg" %}

All in all, I wrote 3 reports to the EAA, which you can read here:

* [2016 EAA Founder’s Innovation Prize Entry](https://drive.google.com/file/d/0B1WyIFBvIVXGaEo5M1BkSVBIYnM/view?usp=drive_link&resourcekey=0-hKeU2Cs2CQLbSydsGagICg)
* [2018 EAA Founder’s Innovation Prize Entry](https://drive.google.com/file/d/19jX5vYdsG4OXD59Apxj7Yl_7_6Oo2iwy/view?usp=sharing) (with Jeremy Cole)
* [2021 EAA Founder’s Innovation Prize Entry](https://drive.google.com/file/d/1CLmlZuDzg3iunJi1LHqINDj63gcTR4US/view?usp=sharing)

## First prototypes

After the 2016 EAA event, I set out to build the device I had proposed: A low cost air data measurement and display device. The first display unit was made from a basic Raspberry Pi and an LCD panel, with a laser cut plastic bezel:

{% include gallery.md imgs="first-display-wiring.jpg,first-display-assy.jpg" %}

The first air data measurement probe started out as a bunch of breakout boards and bare wiring:

{% include gallery.md imgs="first-probe-wiring.jpg,first-probe-assy.jpg,first-probe-mount.jpg" %}

The next step was to try to test this versus some known airspeeds. I tried creating a "mast" on top of the family car, with a whole rigging and retraction system, so I could mount the probe on top, drive down the road, and get data:

{% include gallery.md imgs="prius-pole-front.jpg,prius-pole-back.jpg" %}

Unfortunately, the lesson I learned is that the air flow near the ground around roads is _incredibly_ turbulent. I certainly got some readings, but they were unusably noisy. However, for a while, I was the most ridiculed geek in my neighborhood, and _nobody_ was going to steal that car....

## Testing at Wichita State University

Through a chance posting on Facebook, I got in contact with a team of aeronautical engineering students at Wichita State University, led by Matthew Schmid. They needed a senior project and had a wind tunnel. I had a project and needed data. We collaborated to get the first set of useable data that verified both the testing approach and the general performance of the probe.

Hilariously, the "small" wind tunnel at Wichita State was not operational when we did the testing, so the probe was tested in the [Walter H. Beech Wind Tunnel](https://www.wichita.edu/industry_and_defense/NIAR/Laboratories/wind-tunnel.php), which is big enough to fit a whole car! In the below pictures, you can see the team standing _inside_ the tunnel with the test article!

{% include gallery.md imgs="wichita-kit.jpg,wichita-probe.jpg,wichita-team.jpg" %}

## Testing at an undisclosed location

As the project progressed, I required more accurate data, and also needed to test a probe configuration where I could avoid having an extra tube sticking out. I needed a more extensive test. Through a friend, I got a day's worth of time on a wind tunnel at an undisclosed location (I was asked not to reveal the location as a condition of my use).

First, I tried out my existing probe against the outlet of the wind tunnel. You can see how the instrument shows a consistent speed regardless of which way the probe is pointed into the airflow; this is a result of the calibration that accounts for the off-axis errors.

{% include imagelink.md img="wind-tunnel-quick-check.png" link="https://photos.app.goo.gl/YZCGZ8Dv3iew5edA8" %}

To position the test article at different angles within the tunnel, I needed accurate 2-axis motion control. I splurged and bought two [Dynamixel](https://www.robotis.us/dynamixel-xm540-w270-t/) servos, and never looked back. For all the time and money I invested in the project so far, these things were a zero-hassle solution and worked amazingly. To measure pressures, I used some of the [Honeywell HSC pressure sensors](https://prod-edam.honeywell.com/content/dam/honeywell-edam/sps/siot/zh-cn/localized/datasheets/sps-siot-trustability-hsc-series-high-accuracy-board-mount-pressure-sensors-50099148-a-ciid-151133-cn.pdf) that I had from various prototypes, and I precision-calibrated them with a home-made water manometer.

{% include gallery.md imgs="wind-tunnel-sensors.jpg,wind-tunnel-probe.jpg" %}

See the [**photo album**](https://photos.app.goo.gl/vXBPdkm69QaMvYfZ9) for more photos!

This work is in the [`airball-tunnel`](https://github.com/airball-aero/airball-tunnel/blob/master/data/2022-07/doc/README.md) Github repo. The result is a series of pressures at various points on the test articles, as a function of the angle relative to the air stream:

{% include gallery.md imgs="alpha-beta-q.png,alpha-beta-down.png" %}

This information is used by the calibration code in the [`airball-probe`](https://github.com/airball-aero/airball-probe/tree/main/airball_probe_esp32/calibration) Github repo to generate tables that are used by the firmware.

## Air data probe basics

The air data probe has gone through many design iterations. The majority of them were tailored towards a wireless, battery powered installation, allowing it to be tried on any airplane. The quantities measured are:

* Angle of attack, _α_
* Angle of yaw, _β_
* Dynamic pressure, _q_
* Static pressure, _p_
* Temperature, _T_

This 5-tuple (_α_, _β_, _q_, _p_, _T_) is enough to:

* Fully characterize the relative wind vector;
* Derive the airplane's altitude (with knowledge of barometric pressure from a nearby weather station); and
* Derive the airplane's rate of climb or descent (with numerical differentiation).

To compute the 5 unknowns (_α_, _β_, _q_, _p_, _T_), we require 5 sensor readings, which are:

* 3X differential pressure sensors ([Honeywell HSC series](https://automation.honeywell.com/ca/en/products/sensing-solutions/sensors/pressure-sensors/board-mount-pressure-amplified/trustability-hsc-series));
* 1X barometric pressure sensor ([Bosch BMP280](https://www.bosch-sensortec.com/media/boschsensortec/downloads/product_flyer/bst-bmp280-fl000.pdf) or equivalent); and
* 1X temperature sensor (TI [TMP102](https://www.ti.com/lit/ds/symlink/tmp102.pdf)).

All variants of the air data probe so far have used these components, along with an [ESP32](https://www.espressif.com/en/products/socs/esp32) to collect the data and transmit it over a Wi-Fi connection. The code is in the [`airball-probe`](https://github.com/airball-aero/airball-probe/) Github repo, and is mostly Arduino code (mainly to take advantage of Arduino libraries supporting the various sensors) with a few FreeRTOS primitives where needed.

## Display device basics

The data display has also gone through lots of iterations, but in all cases, it has been a Raspberry Pi single-board computer with an LCD panel, often with a rotary push encoder to change settings. The software is a C++ program that does some math, and paints the display using the [Cairo](https://www.cairographics.org/) UI library.

## Wireless battery powered clip-on system

The project reached a good technology milestone with an iteration of the system that could be installed on a wide range of aircrat without having to go through any FAA regulated approvals. This required a clip-on, battery powered air data probe; a display unit that could be powered by a USB charger; and wireless communication between the probe and display.

The probe is built around a system of 4-40 threaded rods that clamp the whole assembly together, while 3D printed inserts form the structural and aerodynamic components. A mounting plate mates with a pair of studs, and is secured with a thumb screw, allowing the probe to be removed for charging. The PCB is an SMT design incorporating an ESP32 module, battery charging and monitoring, and interfaces to the sensors:

{%include gallery.md imgs="proto1/probe/cad-mounted.png,proto1/probe/cad-unmounted.png,proto1/probe/pcb.png,proto1/probe/PXL_20220223_041841023.jpg,proto1/probe/PXL_20220225_053250555.jpg" %}

The probe mounting to an aircraft wing strut is a "tee square" clamp fixed with bungee cords. Initially, this used a RAM mount ball, but we later re-engineered to a stronger metal pivot. I designed a sighting device -- using a fiber optic bow sight insert -- allowing the probe to be lined up with the axis of the airplane by sighting at a distant object at optical infinity:

{% include gallery.md imgs="proto1/mount/PXL_20220227_024304394.jpg,proto1/mount/PXL_20220305_234816234.jpg,proto1/mount/IMG_20220424_141238842.jpg,proto1/mount/PXL_20220213_031035762.PORTRAIT.jpg" %}

The display is built around a Raspberry Pi 3A+ and a 4.3" WaveShare HDMI LCD panel:

{% include gallery.md imgs="proto1/display/PXL_20220226_034807436.jpg,proto1/display/PXL_20220226_054800174.jpg,proto1/display/PXL_20220401_191208974.jpg" %}

In use, settings were changed via Wi-Fi using a Dart Web app served from a Web server on the display. The display could be mounted anywhere in an airplane, with a commodity USB charging cable:

{%include gallery.md imgs="proto1/use/settings.jpg,proto1/use/PXL_20220306_004023817.jpg" %}

My "customers" got the full packaging experience:

{% include gallery.md imgs="proto1/pack/IMG_20220410_203544032.jpg,proto1/pack/IMG_20220414_183200587.jpg,proto1/pack/IMG_20220414_205318352.jpg,proto1/pack/IMG_20220414_205443146.jpg" %}

See the [**more complete build album**](https://photos.app.goo.gl/6UBZfob4zw4UfJUm6) for this system for more photos!

## STOL antics with Jimmy

Along the way, I met my friend Jimmy O'Neal, who owns a RANS S-20 "Raven" based in Camarillo, CA ([KCMA](https://skyvector.com/?ll=34.20968155820602,-119.10263644844828&chart=24&zoom=1)). He is an amazing off-airport STOL pilot and became a mentor to me in my own piloting journey. And, he really loved the Airball concept and became my most dedicated, vocal, and insightful tester:

{% include gallery.md imgs="jimmy-probe-install.jpg,jimmy-rans-s20.jpg" %}

Jimmy uses Airball to compete in a STOL contests, and credits the intuitive human-machine interface with not only his ability to fine-tune his flying, but also with getting safely out of unexpected situations in the back country:

{% include imagelink.md img="jimmy-national-stol.png" link="https://www.youtube.com/watch?v=fyoe3qHYqzE&t=14325s" %}

## Education

The Airball system is particularly useful for educating pilots about how their airplane flies. See this presentation I gave at the Hiller Museum in San Carlos, CA, about the system:

{% include imagelink.md img="ihab-hiller-presentation.png" link="https://www.youtube.com/watch?v=MXWuIW_5PoU" %}

See also this YouTube playlist of original videos I created to explain "How Airplanes Fly" in a correct but inuitive and non-mathematical way:

{% include imagelink.md img="ihab-how-airplanes-fly.png" link="https://www.youtube.com/watch?v=6QBWjSOvajY&list=PLadSd3pcmeLuX9xlmwISg20MUvXG_Lmyn" %}

## Next generation display

Based on feedback from Jimmy, it was clear that the system needed to be more "heads-up" and visible to the pilot. I chose a [Newhaven 2.4 inch 1000 nit 240x320 TFT panel](https://newhavendisplay.com/2-4-inch-sunlight-readable-tft-without-touchscreen/) which, at that time, was available with a SPI or parallel interface. I did not find any comparable LCD panels that had a standard RGB interface allowing me to use (say) a [TFP401](https://www.adafruit.com/product/2218) with the Raspberry Pi HDMI output. But SPI did not give me an adequate frame rate. I therefore needed a more "custom" driver.

My solution was to use the Raspberry Pi [Secondary Memory Interface](https://forums.raspberrypi.com/viewtopic.php?t=280242) to build a very simple display driver, sending data via the [8080 protocol](https://www.displaymodule.com/blogs/knowledge/the-interface-of-8080) to the display controller. I mapped 16 bits of the Raspberry Pi GPIO to the interface, allowing a very fast 1-2 millsecond frame refresh rate. Once all the hardware was debugged, the actual code (see [`st7789vi_frame_writer_smi`](https://github.com/airball-aero/airball-display/blob/main/src/airball/screen/st7789vi_frame_writer_smi.cpp)) was fairly simple.

{% include imagelink.md img="new-display-bench.jpg" link="https://photos.app.goo.gl/WLuh4FyV63Z1QHxE7" %}

The next step was a minimum viable PCB and mechanical build that put all the wiring together using the existing Raspberry Pi 3A+, and allowed us to test the ergonomics. In addition to basic GPIO wiring, this incorporated a backlight LED driver with PWM dimming by the Raspberry Pi. The result was this device:

{% include gallery.md imgs="new-display-first-front.jpg,new-display-first-side.jpg" %}

And as you can see from this video, the utility of the device was immensely improved as a result of the brightness and "heads up" location right on the aircraft centerline. Thank you Jimmy! Check out this video:

{% include imagelink.md img="new-display-first-flying.jpg" link="https://photos.app.goo.gl/zDef3VpSJ52WqYiZ6" %}

In addition, due to the complexity of the Dart settings editor, I went back to using a plain push encoder knob to change settings using a minimal firmware UI. I programmed the knob using CircuitPython to act as a [USB HID](https://en.wikipedia.org/wiki/USB_human_interface_device_class) device, which made things easy to interface together.

{% include gallery.md imgs="new-display-first-knob.jpg" %}

The next step was to design a custom PCB around this concept. This is a carrier board for a Raspberry Pi [Compute Module 4](https://www.raspberrypi.com/products/compute-module-4/) with an SD card slot for the boot file system.

In addition to the LCD circuitry, it contains a [1 Mbit I2C EEPROM](https://www.digikey.com/en/products/detail/stmicroelectronics/M24M01-DFDW6TP/4729292) for parameter storage, which can be mapped to a file on Raspbian. I created an [`atomic_store`](https://github.com/airball-aero/airball-display/blob/main/src/airball/util/atomic_store.cpp) utility to format the data in two alterating "banks" to preserve integrity if the system is powered down during a write operation.

The main interface to the outside world is a USB-C port supporting reverse power delivery. Because previous experience with the Raspberry Pi 3A+ showed flakey connect/disconnect behavior of the built-in USB system, I added a GPIO-resettable [USB hub IC](https://www.microchip.com/en-us/product/usb2412) to act as the standards compliant interface to the outside world. This is a convenient form factor, because it allowed me to use any peripherals that Linux supports, and hook up my display to a USB/Ethernet adapter and log into it in the laboratory! USB-C is also a really convenient and compact wiring standard, and cables are easy to get.

{% include gallery.md imgs="small-display-components.png,small-display-rpi.png,small-display-opened.jpg,small-display-back.jpg" %}

I could now install the system in my airplane and have a convenient panel-mounted knob for adjusting settings! This was finally the form factor I was looking for all that time, with **all** critical flight information displayed right where I could see it:

{% include gallery.md imgs="small-display-installed-display.jpg,small-display-installed-knob.jpg,small-display-installed-flying.jpg" %}

## Next generation probe

I turned my attention to the air data probe, hoping to shrink the form factor and make it more reliable. After a lot of experience with the battery powered version, it was becoming clear that people just wanted a more permanently installable unit. As I shopped my work around, I came to realize that my primary "market" is people with [Experimental Amateur-Built](https://www.faa.gov/aircraft/gen_av/ultralights/amateur_built) aircraft, on which it's far easier to install accessories without complex FAA approvals. The "clip-on" and battery charging are less useful there.

I redesigned the probe PCBs to re-arrange the layout, adding among other things a voltage regulator and a CANBus interface. Now there were three PCBs: A main compute module; a carrier for the barometer and thermometer using I2C; and a carrier for 3 main pressure sensors using SPI.

{% include gallery.md imgs="compact-probe-components.png,compact-probe-connectors.png,baro-temp-qwiic-components.png,baro-temp-qwiic-connectors.png,pressure-spi-3.png" %}

The mechanical parts count was now massively reduced, by using a stack solid parts as "manifolds" to route the pressures to the various sensors. I could also use the new wind tunnel calibration to eliminate the long brass static pressure probe, and have side holes serving the same function:

{% include gallery.md imgs="compact-probe-mech-assembled.png,compact-probe-mech-exploded.png,compact-probe-completed.jpg" %}

See the [**more complete build album**](https://photos.app.goo.gl/CBAUGTwsZmvsJbtm7) for more photos of the probe under construction!

## Future directions

At this point, I have enough material to have verified most of my important hypotheses. Jimmy and I, and all my co-owners in the [Coyote Valley Sport Flyers](../n291dr_cvsf/) club, have been flying with this hardware for several years now, and we have come to consider it an important part of our flying experience. Sergey Kataev, a flight instructor, regularly brings his students to our airplane to learn using Airball!

The question is what the total addressable market is for this device, and if there is a way to create a simplified product offering that can achieve all these goals with less expense. For example, can we use existing probes and get data that is not as good as what the custom probe provides, but is "good enough"? Can we use CANBus throughout the system to make it easier to install for the typical airplane owner? Can we create a companion app that uses the data to fine-tune the flight configurations of an airplane for optimium performance?
