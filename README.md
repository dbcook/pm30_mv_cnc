# pm30_mv_cnc

This repo holds design artifacts for my CNC conversion of a Precision Matthews PM-30MV bench mill
using a ballscrew and motor mount kit from Arizona CNC Kits.

## The Mill

The base mill for this is a [Precision Matthews PM-30MV](https://www.precisionmatthews.com/shop/pm-30mv/), which is a medium sized (~200 kg) Chinese made bench mill
with USA distribution and support.  It is similar in size and cost to the [Grizzly G0761](https://www.grizzly.com/products/grizzly-10-x-32-2-hp-hd-benchtop-mill-drill-with-power-feed-and-tapping/g0761),
but the PM-30MV is a much better candidate for CNC conversion.

### Mill Features

The PM-30MV has several salient features that are relevant to CNC
adaptation.

* It has a variable speed 2HP (1.5kW) brushless DC motor that can be controlled
via a normal 0-10VDC analog voltage.  The speeds are noticeably
quantized in the electronic controller (seems like 32 steps) but that
doesn't hurt much in practice.  It's trivial to implement a switch on
the 0-10V signal to transfer
control from the potentiometer on the stock control box to the CNC controller.

* The E-stop button that comes with the PM-30 is a clone of the standard
Omron type with stackable contacts, so you can easily add a contact module to
provide the E-stop input to the CNC controller.

* The spindle has a pulley drive that provides 1500rpm and 3000 rpm ranges, so
you can get more torque at lower speeds if desired.  In practice, when using
carbide tooling on aluminum I've never encountered a need to go to the lower
speed pulley.

* The column has a square flat mounting surface to the base casting and is not
cantilevered, unlike many small mills.  That allows the column to be shimmed
on the base if needed to adjust head nod.  On my unit the verticality of the
column is very good and I have not had to shim it.

* It's possible to extend the Y travel in the outward direction by around an
inch via a simple modification to the base casting.  This doesn't really
increase the net Y travel wtihout resetting the work on the table, but does
allow some additional flexibility in positioning larger workpieces.

## The CNC Conversion Kit

I used the PM-30 conversion kit from [Arizona CNC Kits](https://www.arizonacnckits.com/).  The owner Dave Clements is fantastic to work with and very conscientious.
When my Y mount plate turned out to be too thick for my particular unit, he
made me a new one immediately.

The kit with the mechanical parts - ballscrews, ballnuts, and NEMA-34 motor mounts -
will cost around $1K.

## Motors and Drivers

In addition to the mechanical kit, you'll need motors and controllers to drive the
ballscrews.  Here you have options:

*  Closed-loop stepper motors
*  DMM servos (Canada)
*  [Clearpath servos (USA)](https://teknic.com/products/clearpath-brushless-dc-servo-motors/)

The closed-loop steppers weren't a realistic option when I built my system
in 2019, but they have come a long way and now provide speed and torque
approaching that of servos at lower cost.

I used the 750W DMM 86N-DHT-A6MD1 (NEMA flavor) servos from [Dynamic Motor Motion](https://www.dmm-tech.com/products_main.html) with their DYN4 series drivers.
A motor+drive pair costs about $USD 560 on the 2023 price list.  It would
have been OK to use the next smaller size servos for the X and Y axes, but I
consciously chose to keep them all the same type for interchangeability.
Overall I've been happy with the performance, but I've had two servos burn out
(one on X and one on Z) in the four years I've been running the system, despite
only moderate levels of use.  In both cases it was the motors rather than the DYN4 drive units that failed.

The Z axis has some tendency to sink under its weight, so the next time the Z
motor fails I'm going to replace the Z servo with a 86N-DHT-A6MDB that has a
24VDC holding brake.

If I had it to do over, I'd probably go with the Clearpath servos based on the
failure history with the DMM units and the fact that Clearpath has an extensive
series of integrated step/direction servos that don't require a separate
driver.  The Clearpath product line is extensive and has many more options for
motor size and power options.

## Controller Design

### Power Section 

Here is a block diagram of the power section of the DMM servo system.  This
design follows the DMM recommended setup almost exactly, except for inclusion
of separate fuses on the controller logic AC power connections.

![Power Section Block Diagram](art/PM-30MV_power_section.drawio)
