# Essential Tooling for the PMC-30MV

After building and using the CNC converted PMC-30MV for a few years, some things
stand out as totally vital tooling for use with the machine.

## Toolholding

| Name                  | Manufacturer  | Description         |
| ----                  | ----          | ----                |
| Tormach TTS           | Tormach       | Tool holder system  |
| R8 to TTS adapter     | Tormach       | Allows use of TTS holders in R8 spindle |
| R8 collet set         | Generic       | Collets for native R8 spindle interface |
| Edge Tech tool setter | Edge Tech.    | Measure height of tool above workpiece or reference plane |
| Haimer "3D Taster"    | Haimer        | Edge and surface finding in all 3 dimensions |      

### Tormach TTS Tool Holder System

Tormach's TTS tool holder system is a great thing for any small to medium size R8 mill.  It converts
the threaded R8 interface to a single 3/4" collet, with standard holders that all have a cylindrical 3/4" shank
and make positive contact on the spindle nose for Z axis repeatability.  It's called a two-surface
system because the tool is both gripped by the collet and seated against the face of the spindle nose.

The single greatest benefit of TTS is that it shortens the time to change a tool holder by a very large factor.
Changing a tool using the stock R8 spindle requires fully un-threading the previous collet, inserting
the new tool and collet, and completely re-threading the drawbar into the collet.  If you have to do it
by hand, it takes 30-60 seconds.  Hence many Bridgeport type mills have pneumatic tool changer systems
that spin the drawbar for you.

With TTS the time to switch tools is a few seconds, requiring just 1/4 to 1/3 turn of the drawbar.
This is because you are not unscrewing the whole collet; just loosening the TTS collet enough to
change out the holder.

Another advantage of the TTS system is that automatic tool changing (ATC) is possible.  This can be
seen on Tormach's own CNC mills.

### R8 to TTS adapter

This is mandatory for using TTS holders in any R8 spindle mill.  You can get it directly from Tormach.
It resembles a standard 3/4" R8 collet except that the nose of the collet is shortened so that the TTS
holder can contact the spindle nose without bumping into a protruding section of collet.

### R8 Collet Set

Even with a TTS setup, you will sometimes want to put something in a native R8 collet, like endmills
with over 1/2" shank size, or small tools where you want minimum runout.  So you still need a
reasonable R8 collet set.  For most purposes the ones you can get from Grizzly or Shars will be OK.

### Edge Tech Tool Setter

This is a little gadget with a dial that shows you when the tip of a tool is exactly 4.000" above
its base.  You can use this directly with the Mach4 "set tool" button on the Offsets page.
There are different ways of setting the Z axis reference, but this is by far the easiest for
use with one or two tools in a session.  Edge Technology products are generally very well made
and quite inepensive.

### Haimer 3D Gauge ("3D Taster" in German)

The Haimer gauge has been my go-to surface locator ever since I got it.  True to its name, it
senses reference locations in all 3 dimensions, taking the place of edge finders.  But beccause
it's got a calibrated dial, it can also be used for measuring tramming accuracy when lining up
a piece for machining, aligning your mill vise on the table, checking table slot alignment, 
measuring height differences on a workpiece, etc.  The mechanism is very sensitive and smooth.
Despite nominally having resolution of 0.0005", in reality it can show differences of 
just 0.0001-0.0002 or so.  The probe tips come in short and long lengths, and are replaceable
because you will break one every once in a while.

If you buy the inch version of the Haimer gauge, make sure you always get the inch versions
of the probe tips.  The ones for the metric gauge are not the same and will give incorrect
results if used with the inch gauge.

## Metrology

After using a whole bunch of different Mitutoyo, Starrett and generic measuring gear, I am
now convinced that the Mitutoyo equipment is consistently the best available in most cases.
Getting a good set together will cost some money, but you won't have to do upgrade them a
year later after you get frustrated.

### Essential

| Name                  | Manufacturer  | Description         |
| ----                  | ----          | ----                |
| Steel rules           | Mitutoyo      | 300/450 length inch and metric rules |
| Digital calipers      | Mitutoyo      | 8" Digimatic absolute
| Micrometer set        | Mitutoyo      | 1-4" or 1-6" set, analog type
| Telescoping gauges    | Starrett      | standard set
| Machinist squares     | generic       | 3-5" squares        |
| Dial indicators       | Mitutoyo      | 2" dial, any face color you want, get 2
| Dial test indicator   | Mitutoyo      | 0.0001 precision version
| Indicator mag holder  | Noga          | NogaFlex holders, small and large
| Indicator spindle holder | Edge Tech  | Indicator holder with shank to go in spindle tool holder

### Optional

| Name                  | Manufacturer  | Description         |
| ----                  | ----          | ----                |
| Precision level       | Starrett      | 4" size is fine
| Height gauge          | Mitutoyo      | 12/18/24" sizes available
| Surface plate         | Grizzly       | 12x18x3", 70lb, normal grade

## Workholding

| Name                  | Manufacturer  | Description         |
| ----                  | ----          | ----                |
| DX-4 or DX6 vise      | Kurt          | mill vise
| T-slot clamp set      | generic       | size to match your table slots (14mm for PM-30MV)
| extra T-nuts          | Te-co         | you can also fabricate on your mill from 1018 steel
