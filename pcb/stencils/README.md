
# Cutting PCB Stencils from Polyimide 
## A guide for the lab64 trotec laser cutter

This write-up documents a working procedure for cutting PCB stencils on the trotec 130W CO2 laser cutter. 
This procedure is **by no means** optimized and users are encouraged to experiment with better methods/techniques. 

The thickness of the stencil and the size of the opening are specific for each component included in the PCB design and will be defined by the manufacturer (typically in the datasheet). This turtorial describes a process for cutting a non-adhesive polyimide (aka Kapton) film that is 0.005 inch (5 mils) thick. 


![Figure 1]()


1.	Begin by exporting the solderpaste artwork from the PCB layout tool. This example shows the process for Autodesk's Eagle layout software. Figure 1 shows which layers to enable in Eagle.
	>NOTE: although we won't be cutting the board outline, it's important to include for scaling/alignment purposes. 

	![Figure 2]()

2.	After configuring the layers, the artwork must then be exported in SVG format. Eagle does not have a native SVG exporting feature, so [download this Eagle ULP script](). Once downloaded, click FILE -> Run ULP -> Browse -> and choose the downloaded script. Setup the export window as shown in Figure 2.

	![Figure 3]()

3.	Once exported, open the SVG file in Inkscape. This can be done on the laptop in 004 if you don't have inscape installed. It should look something like Figure 3.

4.	Begin preparing the SVG file by selecting everything (Ctrl+A on windows), then ungroup everything (Ctrl+U) This will maintain each component's group, but allow the PCB outline to be selected.

5.	Select each piece of the board's outline by left clicking and holding shift. Ensure you've selected corners that have a radius and any other small features along the line.

6.	With the entire boarder selected, group the outline paths together (Ctrl+G)

	![Figure 4]()

7.	The Fill and Stroke parameters of the group will now be undefined, as indicated by the highlighted questionmark shown in Figure 4. 
	>NOTE: If you do not seen the Fill and Stroke menu, enable it by going to EDIT -> Fill and Stroke (Shift + Ctrl + F). 

	![Figure 4b]()

8. While on the Fill tab, click the "X" box to change the paint parameters from "undefined" to "no paint.

9.	Next, with the border still selected, go to the stroke paint tab and change the RGB value from pure black to pure blue (RGB values of R: 0, G: 0, B: 255, A: 255).

	![Figure 5]()

10.	For the trotec, it's important your stencil design doesn't contain any lines (or edges) that run parallel to the axis of movement. Therefore, select the entire design again (Ctrl +A), and left click once on any line of your board to change the bounding-box transform mode to rotation. Hover your mouse above one of the small white boxes located at the corners of your selected board. The cursor should change into a rotation symbol. While still holding Ctrl, click and drag the mouse to the left in order to rotate the design 45 degrees. Unless your board contains components at odd angles, your design should now look similar to Figure 6.
	>NOTE: Many of the footprints have been removed from the design in Figure 6 to allow for soldering of only a portion of the board. 

11.	After rotating, the design is now larger than the Inkscape canvas. To fix this, go to FILE -> Document Properties (Shift + Ctrl + D) and increase the Width and Height values to exceed the blue board outline by about 0.5 inch (also shown in Figure 6). 

12.	Close the Document Properties windows (**NOT the main Inkscape window**) and position the design in the middle of the canvas by selecting all (Ctrl + A) and left-click dragging.

	![Figure 6]()

13. Save the Inkscape design as a **Plain SVG** as seen in Figure 6.

14.	If it isn't already, move the plain SVG file to the 004 laptop via USB flashdrive.

15. After opening the plain SVG, send the design to the Trotec laser by going to File -> Print (Ctrl + P).

	![Figure 7](%/images/7.PNG)

16.	Ensure the Trotec Engraver is selected in the print dialog and click "Preferences." Configure the trotec window as shown in Figure 7. 
	>NOTE: in this case, it's very important that Resolution is set to 1000 dpi.

17.	If the trotec software ("JobControl") wasn't already running, it will be started and appear along the bottom windows taskbar. 
	>NOTE: for designs with lots of components or features, the trotec print drivers may take up to 10 minutes to parse the file. Be patient! 

18. While the file is being parsed, start the trotec chiller and then turn on the laser cutter.

	### Film preparation

	![Figure 9]()

19.	Keeping in mind the size of your stencil and being conciencious of the cost of polyimide, use a straight edge to cut an appropriate sheet from the roll.

	![Figure 10]()

20.	Use the contact-tape to cover the polyimide sheet and adhere it to a flat piece of Duron scrap. Ensure there is uniform contact acrross the film. Squeege out any bubbles if necessary.

	![Figure 11]()

21.	Position the Duron on the cutting-bed and focus the laser to the top of the contact-paper above the polyimide. Remember that the stencil design was rotated 45 degrees.

	![Figure 8c]()

22. In the JoeControl software, drag your design from the queue onto the honeycomb cutting area. Work back-and-forth between laser cutter and the laptop to ensure your design is aligned properly over the film. This can be tricky!

	![Figure 8b]()

23. After the design is properly aligned, double click anywhere on the honeycomb (not on your design) and configure the laser parameters according to the image above. 

	![Figure 12]()

24. Double check you did not skip a step before starting the job. Let all three passes complete (eventhough it looks like it isn't necessary, the three passes are needed for small detailed pads). As shown above, debris from the Duron will collect above the design.

25. After the laser is finished, gently brush the debris off the contact-paper with a dry paper towel before peeling the stencil off of the Duron. 

	![Figure 13]()

26. Some Duron compositions are better than others for this process. As you can see, there will be cutting residue on the bottomside of the stencil. Use a papertowel with isopropoal alcohol to remove the residue.

	![Figure 13]()

27. Carefully remove the contact-paper from the topside and continue cleaning with isopropal alcohol. A freshly cut stencil that's been (mostly) cleaned is pictured above. 

