Installing and wiring the LEDs inside the dome
==============================================

Once you’ve tested all the LEDs, it’s time to put them in the dome. But there is one final consideration. The interior of the dome was painted flat black to minimize light scattering. But you’re about to install LEDs that are mostly white in color, and will scatter light quite effectively. I calculated that for the 12” dome I’m building here, the 48 LEDs will cover about 10% of the total area inside the dome, which could lead to quite a bit of scattered light. To reduce that, I paint the LEDs with a non-conductive flat black paint:

.. figure:: ../figures/led_wiring/led_wiring_1.jpg
   :align: center
   :width: 8cm

However, since I still need to know which wire is positive and which negative/ground, I leave a little bit of the end next to the positive lead wire unpainted so that I can keep track of the polarity.

To install the LEDs inside the dome, I put a small dab of adhesive on the back of the LED. I use a silicone-based adhesive because I’ve found that if you don’t use too much of it, it’s possible (with some effort) to pry off the LED if something goes wrong. I then press the LED on top of one of the position markings you created way back in step one, with the positive lead facing to the right as you look directly at it:

.. figure:: ../figures/led_wiring/led_wiring_2.jpg
   :align: center
   :width: 8cm

Continue the process until all of the LEDs have been installed:

.. figure:: ../figures/led_wiring/led_wiring_3.jpg
   :align: center
   :width: 8cm

Before the adhesive dries, check to make sure that all of the LEDs have the positive lead facing to the right, and the wire leads face left and right when you look directly face on at the LED. Once you’re sure everything is oriented correctly, set the dome aside to allow the adhesive to set for at least 12 hours, and preferably 24.

It may look like an intimidating amount of wiring needs to get done, but don’t worry – there is a method to the wiring madness that keeps it from becoming too complex to keep track of.

Once the adhesive you’ve used to attach the LEDs to the inside of the dome is dry, it’s time to do the wiring that will control and supply power to the LEDs. But there’s a bit of prep work that needs to be done first.

Flip the dome so that the interior faces up, and place a marker (masking tape here) on the bottom of the rim in a position that bisects two of the LED columns:

.. figure:: ../figures/led_wiring/led_wiring_4.jpg
   :align: center
   :width: 8cm

As you can see, one of the LEDs in the lowest row (closest to the base) is to the left of the marker, and the LED in the next row up is to the right.  That’s actually not a critical reference position, you could wire the dome with the marker to the right of the first and the left of the second. But for now, probably best to follow this convention, since all of the wiring in these instructions (and the pictures) will work off the above marking. Beyond that, pick any pair of columns you want – doesn’t matter.

Next, place additional markers on the base of the rim, between LEDs on the lowest row (above those on the next lowest row), three on each side as shown in these pictures:


.. figure:: ../figures/led_wiring/led_wiring_5.jpg
   :align: center
   :width: 8cm



.. figure:: ../figures/led_wiring/led_wiring_6.jpg
   :align: center
   :width: 8cm

Now flip the dome over, and put marks on the rim of the dome corresponding to the tape marks; doesn’t require absolute precision, just as close as you can. Differentiate the first mark you put down from the rest somehow (an asterisk in the example below):

.. figure:: ../figures/led_wiring/led_wiring_7.jpg
   :align: center
   :width: 8cm

For all the marks except the first one, mark the position where you will drill two holes above them, the first about 3/8” above the bottom, the second about ½” above that. These will be for zip ties that will guide and hold some wires in place.

.. figure:: ../figures/led_wiring/led_wiring_8.jpg
   :align: center
   :width: 8cm

In the next pic, there will be similar ½”-spaced marks directly above the first reference mark, placed about one-third and two-thirds distance from the base to the top of the dome. These are also for zip tie holes to hold wires in place. However, after finishing the wiring, I realized that these weren’t really necessary for the 12” diameter dome I’m using here, and probably wouldn’t be necessary for any dome up to at least 18” in diameter; the wires are short enough and stiff enough that they don’t need to run through guides to stay in place. So I have those marks in place, and wound up drilling them out, but didn’t install any zip ties through them. For smaller domes you can skip these.

.. figure:: ../figures/led_wiring/led_wiring_9.jpg
   :align: center
   :width: 8cm

Pull out your electric drill and 1/8” plastic drill bit, and drill holes through the marks you’ve just made. Use lubricant (vegetable oil is fine), and don’t use too much pressure, or you may crack the dome.

.. figure:: ../figures/led_wiring/led_wiring_10.jpg
   :align: center
   :width: 8cm

.. figure:: ../figures/led_wiring/led_wiring_11.jpg
   :align: center
   :width: 8cm

If you’re building a larger dome that requires vertical wire guides, drill those holes as well (didn’t need them for my small dome, but didn’t know that yet):

.. figure:: ../figures/led_wiring/led_wiring_12.jpg
   :align: center
   :width: 8cm

Now mark three additional sets of holes. First, put two marks 3/8” above the base of the rim, 1” apart, centered on the main reference point. Measure about 1” to the left of the leftmost hole, and put another mark there. Then, put two marks about ¾” above the left two marks, and one mark about ½”-5/8” above the rightmost mark. These holes are for zip ties that will hold the power cables in place.

.. figure:: ../figures/led_wiring/led_wiring_13.jpg
   :align: center
   :width: 8cm

Drill 1/8” holes with your plastic drill:

.. figure:: ../figures/led_wiring/led_wiring_14.jpg
   :align: center
   :width: 8cm

Now mark one position about ½” above the rim, directly above the main reference mark. Put a second mark about 5/8” above the rim, to the right. I have it about ½” to the right of the rightmost holes, but ¾” or even 1” probably would have been a better choice.

.. figure:: ../figures/led_wiring/led_wiring_15.jpg
   :align: center
   :width: 8cm

Drill a 1/8” starter hole at each of these marks, then use a step drill (Unibit) to drill ½” holes at each of these locations; this is where the power cables will go into the dome. The picture shows holes closer to ¼” in diameter, but I found those to be too small and expanded them later on to ½”.

.. figure:: ../figures/led_wiring/led_wiring_16.jpg
   :align: center
   :width: 8cm

Clean up the debris from the drilling (and the marks you made). Now it’s time to get wired.

Can’t avoid it any longer – it’s time to wire up all the LEDs in the dome into a matrix configuration, like the one shown schematically here:


.. figure:: ../figures/led_wiring/led_wiring_17.png
   :align: center
   :width: 8cm

This is an 8x8 matrix, where the rows get connected to ground control, and the columns connected to positive voltage control. For the RTIMage system, the P-channel MOSFETs control the columns/+ voltage, while the CAT4101s control the rows/ground (and also set the current). For the small 12” dome I’m building here, there are only 6 rows, but a full 8 columns, so two of the CAT4101 chips will remain idle with this system.

So here’s a shot of the LEDs inside the dome, after being glued in place in a previous step:

.. figure:: ../figures/led_wiring/led_wiring_18.jpg
   :align: center
   :width: 8cm

Even with only 48 LEDs, instead of the maximum 64 the controller can support, the prospect of wiring all these up may be a bit daunting. Not going to pretend that this is going to be fun – you’re probably looking at 4-5 hours of tedious work. But I’ve come up with a system that I hope works reasonably well, keeps the pain level down, and lets you fix any mistakes fairly easily. Also remember that this is a small dome, 12” in diameter, so things are packed in pretty tight; with larger domes, there will be more space to work with.

You’re going to be connecting the LED ground leads in a row, and all the LED + leads in a column. Remember that when you painted the LEDs black, you left a little bit unpainted to mark the + side, but painted the -/ground side black, and you can see that above. So you’ll be wiring up the ground rows like this:


.. figure:: ../figures/led_wiring/led_wiring_19.jpg
   :align: center
   :width: 8cm

… where the blue mark at the top represents the main reference mark from the previous step. The wiring from only two rows is shown here in green, but all of the remaining rows will be wired in a similar fashion – you connect all the ground LED leads in a single row together, and then the last wire needs to be long enough to reach within about an inch or so of the bottom of the dome.

Similarly, you’ll be connecting all the + LED leads together in a column. Unlike the row, though, the column elements are a bit staggered, so you’ll need to zigzag back and forth:

.. figure:: ../figures/led_wiring/led_wiring_20.jpg
   :align: center
   :width: 8cm

The last lead will be a short one at the bottom, which you’ll be connecting to another wire.

.. warning::
   
   Some of the upcoming pictures will show the + leads bent down towards the bottom, like this:

   .. figure:: ../figures/led_wiring/led_wiring_21.jpg
   :align: center
   :width: 8cm
   
   **DON’T DO THIS!!!**
   
   I had an idea that this would make the wiring a bit easier. I was wrong, and ultimately wound up bending them back. Just leave the + LED leads as straight as they were when you glued the LEDs inside the dome – it makes the wiring a lot easier.

Let’s start with the rows. You’re going to have to connect 8 pieces of wire together, 7 bridging the 8 LEDs in the row, and the last one leading down to a hole you drilled near the base in the previous step (it’s the hole at right in the picture above). What length should the wire be? The wire length will depend on the size of the dome, and the number of columns in the row. 

You’ll have to choose a wire length long enough to connect adjacent ground leads, plus some slack to let you bend the wire into a position that doesn’t block light from the LEDs. However, a good first guess for the wire length can be obtained by measuring the distance between two adjacent LEDs in a row, then adding about 1.5” to that. 

Start by cutting two pieces of wire that length, and stripping off 2.5-3mm of insulation off each end. Crimp a female Dupont pin onto the end of one wire, the same way you did in previous steps. Now comes a slightly trick step. You need to hold the uncrimped ends of two wires together, and then crimp both of them in a single female Dupont pin. The tricky part is that the crimp end of the Dupont pin is just barely big enough to fit two wires, but you have to stick them in just the right way.

The best way I found is to pinch the two wire ends together as close as possible, and then slide them into the crimper vertically (perpendicular to the general orientation of the crimper). Most times, you will feel them slide in a bit, and then stop as the insulation catches on the end of the pin. Don’t crimp at this point; while it might work, I’ve found that more often than not the crimping doesn’t hold, and one or both wires fall out.

You need to get a little bit of the insulated part of both wires into the crimp end of the pin. To do this, you need to gently jiggle and twist the two wires in the crimper, until you feel them start to slide a bit further in. This is your signal that you’ve got the insulation in the crimp end, and you can finish the crimping process. These first two wires crimped together should look like this:


.. figure:: ../figures/led_wiring/led_wiring_22.jpg
   :align: center
   :width: 8cm

As in previous crimpings, put a bit of solder on the crimped end to secure the wires and ensure good electrical contact. Then take two of the 1-pin plastic female Dupont housings, and slide the pins into them. They may slide in easily to the end, but more often than not they will likely slide in partway and then stop. They need to slide in all the way to the end, otherwise the LED male Dupont pin will not be able to make contact with the female Dupont connector above. The best method I’ve found for dealing with recalcitrant connectors is to hold the wires at the base of the connector firmly,  grip the plastic housing with a pair of needlenose pliers, then push the housing down towards the base of the connector; works pretty well. The pair of wires will now look like this:

.. figure:: ../figures/led_wiring/led_wiring_23.jpg
   :align: center
   :width: 8cm

Now you’ll need to check whether your initial guess for the wire length (distance between LEDs + 1.5”) was correct. Go back to the dome, and see whether the two connectors are able to reach the first two LED pins, plus a bit of slack in the wire to let you bend it into position. In the picture below, I’ve underlined the wires in green, showing that they do reach between LED leads when bent properly, with a bit of slack:

.. figure:: ../figures/led_wiring/led_wiring_24.jpg
   :align: center
   :width: 6cm

It may look from the picture as though I inserted the LED pin into the female connector. That’s because I did - but you shouldn’t. The pins are easy to bend, and if they bend and break you’ll need to pry off the LED to fix it, which is not fun. Best to only insert the pins once, and there’s some prep work that will make the pins slide in more easily (more on that in a bit). For now, just check for the proper wire length. If it looks fine, then you can stick with that LED distance + 1.5” guesstimate for all of the remaining rows. If it seems like a close fit, feel free to add a bit more length to the wire – better too long than too short.

You’ve cut and crimped two wires for the top row; now cut 5 more wires of the same length to connect the ground pins on the remaining LEDs in that row, plus one more last wire long enough to reach from the last LED in the row down to the hole at the base of the dome. Keep crimping and soldering two wires together until you get to the last longer wire, then crimp and solder a female connector to the single end of that last wire. Stick the female pins into the plastic housings, bend the wires so that they’ll connect more easily to the LEDs, and you should have something that looks like this:

.. figure:: ../figures/led_wiring/led_wiring_25.jpg
   :align: center
   :width: 8cm

The first LED connector is at lower right, and the longer wire that should reach to the base of the dome is near the top. Stick a male Dupont pin into each end, then use a multimeter to make sure you have good electrical connectivity between both ends. For extra safety, you can check to make sure that every intermediate connector has electrical connectivity, but I’ve found that if the ends are electrically connected, the rest of the connectors are usually good as well.

One more thing. Take a male Dupont pin, and slide it in and out of each of the female connectors 2-3 times. I’ve found that this helps make the LED pin slide in more easily, making it less likely that it will bend.

Time to wire up the top row. Start with the LED on the end of the row, and slide the connector onto the LED ground pin. The safest way to do this is to hold the ground pin firmly flush against the side of the dome so that it can’t move, then hold the female connector/housing against the dome surface and slide it onto the pin by pushing against the back end until you feel it go in as far as it can. Be careful not to force it, as this might bend the LED pin. If you're not sure about this, practice with some scrap connections outside the dome until you get a feel for it. Repeat this with every other LED ground pin in the top row. When you’re done, it should look like this (wires and connectors are paralleled by the green line):

.. figure:: ../figures/led_wiring/led_wiring_26.jpg
   :align: center
   :width: 8cm

The last wire on the right is the lead that goes down to the base of the dome (out of the picture), and will ultimately be connected to one of the two power cables.

Don’t worry too much at this stage if wires are blocking LEDs – wait until all the wiring is done before bending wires out of the way.

Repeat this process for all the rows in your dome, 6 in this case:

.. figure:: ../figures/led_wiring/led_wiring_27.jpg
   :align: center
   :width: 8cm

Now repeat the process for the columns, using the wiring pattern in the picture below for every LED column in the matrix:

.. figure:: ../figures/led_wiring/led_wiring_28.jpg
   :align: center
   :width: 8cm

The bad news is that every wire between adjacent LEDs in the column will probably have to be a different length, since the distances are shorter near the top and longer near the bottom. The LED distance + 1.5” rule is again a good starting guess, possibly even a bit longer than it needs to be. The good news is that if you keep track of the correct lengths for the first column, you can just repeat the pattern for every column, since those distances should be the same for every column. The last lead in the connector wire, the one closest to the bottom of the dome, should be about 1.5” in length.

Now that all the wires are done, bend down any wire slack reasonably flush with the interior surface of the dome (doesn’t have to be touching), while not blocking any of the LEDs. The picture above shows a reasonably good example of this. When you do the bending, be careful not to bend any of the wires where they’re soldered to the LED; bend it too far, or too many times, and it may break. For all except the bottom row, try to bend the wires below the LED row, closer to the bottom of the dome; for the bottom row, bend them to be above that row. Doesn’t have to look pretty, since the dome interior will be unseen most of the time. It’s also OK to have the wire touch or go across an LED star, as long as it doesn’t block the actual LED in the middle.

Now that the LED matrix is fully wired, the last step is to make the connection between the matrix rows/columns and the power cables. Power is supplied using Ethernet cables, the same ones you chopped one short end off of in a previous step to make a testing cable. Grab the remaining cables, and trim them both to be the same length. The recommended original length was 7 ft., and 5-6 ft. is a reasonable trimmed length (longer for big domes, shorter for smaller ones). If you start with a 5 ft. cable, 4-4.5 ft. is OK.

You should have one red cable, which will supply positive voltage to the columns, and one cable of some other color, which will connect the rows to ground. In this case, I have a white cable that will do the ground connections (to color-coordinate with the white dome). Using the same method as in a previous step, cut off about 2” of exterior insulation from both cables, trim off any central plastic rib, unwind the paired wires, and trim off about 3 mm of insulation from the end of each wire. 

.. figure:: ../figures/led_wiring/led_wiring_29.jpg
   :align: center
   :width: 8cm

.. figure:: ../figures/led_wiring/led_wiring_30.jpg
   :align: center
   :width: 8cm

Crimp male Dupont pins onto the ground (rows) cable wires:

.. figure:: ../figures/led_wiring/led_wiring_31.jpg
   :align: center
   :width: 8cm

Crimp female Dupont pins onto the MOSFET (columns) cable wires:

.. figure:: ../figures/led_wiring/led_wiring_32.jpg
   :align: center
   :width: 8cm

As with earlier similar steps, put a bit of solder on the crimped end to hold the wire firmly in place and ensure good electrical connectivity. Then put some heat shrink tubing on the male Dupont pin connectors to insulate them, and slide the female connectors into plastic housings to insulate them. With the latter, you may have to use a pair of needlenose pliers to get them to slide all the way into the housings. You should wind up with the ends of the Ethernet cables looking like this:

.. figure:: ../figures/led_wiring/led_wiring_33.jpg
   :align: center
   :width: 8cm

You’ll notice that the wires on the red cable are shorter than those on the white cable, even though I specified that you strip off about the same length of external insulation. That’s because I decided later on that the original length of 1” on the red cable was too short, and stripped off more insulation to make them 2” long.

I’ve also made a very subtle mistake here. Each of the wires coming off the white cable attaches to one of the rows in the dome. But there are 8 wires here, while there are only 6 rows in the dome – two of the wires are unneeded. Looking at the Ethernet cable wire chart:


.. figure:: ../figures/led_wiring/led_wiring_34.png
   :align: center
   :width: 8cm

For the dome I’m building here, I don’t need the cables for pins 7 and 8 on the white cable, since there are no rows 7 and 8. Those correspond to the wires with white/brown and brown colors, so I cut those off. Obviously, if you build a dome with the maximum allowed 8 rows, you would leave those wires in place. There are 8 columns of LEDs in the matrix, so I leave the wires on the red cable untouched; if there were fewer than 8 columns, I could have trimmed off some of the higher-number pins as well.

Next, install zip ties in the hole pairs around the rim; the ratchet part of the zip tie should be on the inside. If you’re using additional zip ties up the side, install them there as well; as I mentioned in a previous step, I drilled the holes for this dome but decided that the zip ties weren’t necessary for such a small dome. Don’t tighten them up yet, leave them mostly “unzipped” for now.

.. figure:: ../figures/led_wiring/led_wiring_35.jpg
   :align: center
   :width: 8cm

Feed the Ethernet cables as shown in the photo below through the zip ties near the large holes, feeding the wires from the cables through the holes into the inside of the dome.  Make sure the red cable feeds into the indicated hole, with the ground cable (white in this case) going into the other hole. When the cables/wires are in place, tighten the zip ties as tight as possible – use pliers if necessary to make the ties tight enough to hold the cables firmly in place. Trim off the excess for these specific zip ties on the inside after you’re done, to get them out of the way.

.. figure:: ../figures/led_wiring/led_wiring_36.jpg
   :align: center
   :width: 8cm

Here's how those cable wires look on the inside, before they’re connected to anything:

.. figure:: ../figures/led_wiring/led_wiring_37.jpg
   :align: center
   :width: 8cm

The wires from the ground cable (the white one) have male pins, which will be plugged into the female pins coming off the ends of the rows. You’ll want to follow the Ethernet cable chart above to figure out which color wire plugs into which row. 

For example, wire 1 is white/orange, so you’ll plug that pin into the female connector for row 1, wire 2 (orange) to row 3, etc. until all the rows are connected. Try running these connection wires underneath other wires in the dome as best as you can. Final result should look something like this:

.. figure:: ../figures/led_wiring/led_wiring_38.jpg
   :align: center
   :width: 8cm

Looks messy, but this won’t be in view during regular operation.

Next come the connections to the positive voltage cable (should be the red one, always). There are female connectors on this cable, and female connectors at the base of the wiring of every column. So you’ll need to measure and cut 24 AWG Kynar wire lengths that will be long enough to run from the base column connector to the corresponding wire from the red cable. 

When measuring the wires, measure along the surface of the dome, just above the base. Crimp male Dupont pins on both ends, solder and heat shrink tube the connectors on these wires, and then connect them to the corresponding female connectors; run them through the zip tie wire guides along the base of the dome. First, do the first four connections running in order, white/orange to the nearest column on the right, orange to the second, white green to the third, blue to the fourth:


.. figure:: ../figures/led_wiring/led_wiring_39.jpg
   :align: center
   :width: 8cm

For the other four, work in reverse order in the other direction. In other words, brown (pin 8) will connect to the closest LED column on the other side, then white/brown (pin 7) to the next closest, and so on; as before, run the wires through the zip tie guides. You could run the wire for pin 8 all the way around the edge of the dome, but doing it this way reduces the amount of wire you need. When done, the full set of positive voltage connections to LED columns should look like this:

.. figure:: ../figures/led_wiring/led_wiring_40.jpg
   :align: center
   :width: 8cm

Time to test the wiring. I’ve written two programs that will test all the LEDs; you should find these in the Files section :

* the first one, Dazzler, lights up the LEDs `at random <https://www.youtube.com/watch?v=sZodZTIxyog>`_
* the second one, Serial_Test, lights up the LEDS `one at a time <https://www.youtube.com/watch?v=BidsNozm-DQ>`_, first by row, second by column.

Upload these individually to the Arduino controller using the Arduino IDE (described in an earlier step). The default setting for both these programs is 8 Rows, 8 Columns; if your dome has fewer Rows or Columns, modify the appropriate constants in the program. So for my test, I changed the Rows constant from 8 to 6 (no decimal point). If you’ve finished the control box while waiting for the LED adhesive to dry, use that; otherwise, use the same wiring configuration in the system test done earlier.

Plug the dome’s red cable into the MOSFET board Ethernet connection, plug the ground cable into the CAT4101 board Ethernet connection, then plug the 9V power supply in – if you only have the USB cable plugged in, the lights will not go on. Dazzler looks cooler, and spots major problems faster. Serial_Test runs slower (set the time in milliseconds with the LED_Time constant; default is 200 milliseconds = 0.2 seconds), which lets you pin down a specific LED that might be a problem.

Hopefully, all the LEDs will light up, and everything will work fine. But if it doesn’t, don’t worry – didn’t work for me the first time, either. If a row doesn’t light up, double check the matching wire connection on the ground cable; for a dark column, check the connection on the red cable. For an isolated LED, carefully check the connections to both pins of the LED. In my case, one of the columns didn’t light up the first time I tried it; after unplugging and re-plugging in the appropriate column wires, it worked perfectly.

When all the LEDs are working, the wiring is done! Tighten up all the zip ties, and trim off the excess on the inside. If the dome will be sitting permanently in one location, you can leave the interior as is. Since this dome is designed to be portable, I cover the wires on the bottom of the interior with black Gorilla tape to keep them more secure (less prone to being accidentally yanked):

.. figure:: ../figures/led_wiring/led_wiring_41.jpg
   :align: center
   :width: 8cm

One problem with Gorilla tape is that it’s glossy, so it will reflect light from the LEDs to places you may not want it. To fix this, I painted the Gorilla tape with flat black paint to dull the finish.
I like to seal up the two holes where the wires/cables go into the dome, just to keep them from rubbing on the edges. Use silicone adhesive, or in my case, hot glue:

.. figure:: ../figures/led_wiring/led_wiring_42.jpg
   :align: center
   :width: 8cm
   
Finally, I put some Gorilla tape over the cable zip ties and holes, to make it look cleaner:

.. figure:: ../figures/led_wiring/led_wiring_43.jpg
   :align: center
   :width: 8cm

I also have an extra piece of tape covering up the holes I drilled but didn’t use. Feel free to omit this tape  if you want, or use some other method to cover this area up.

That’s it – dome is done! Handle with care.