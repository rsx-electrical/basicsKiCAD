# Introduction to KiCad
## Onboarding project

Welcome all. I'm going to make a couple of assumptions which is you have no idea how to use KiCad or maybe you don't even know what KiCad is, but trust you are in good hands.

Let's start with the basics...

> [!IMPORTANT]
> In order to proceed with this tutorial you must 
> 1. Download KiCad onto your local computer (download the most updated please)
> 2. Clone this repository onto your local computer: [rsx_standard_library](https://github.com/rsx-electrical/rsx_standard_library)
> - If you have no idea how to do the previous 2 steps refer to: [KiCad_library_setup](https://github.com/rsx-electrical/basicsKiCAD/blob/main/Kicad_library_setup.md)

### What is KiCad?
It is a software for developing printed circuit boards (PCBs). If those words went over your head let's start with an analogy--designing a PCB is analogous to playing with legos. 

There are three important sections in PCB that will be highlighted through builidng a lego house
1. Schematic: This is where you choose your components: resistor, LEDs, etc. So this is where you choose the legos to design your lego house. 
2. PCB Layout: This is where you structure how your components will be wired together. So this is where you design how the legos will eventually fit together. 
3. Assembly. This is where you build you PCB by soldering. So this is where you finally get to stack the legos together to build a house. 

Of couse in this tutorial you won't actually get to this step 3, as KiCad only allows for steps 1 and 2. 

### A Simple Design
#### Introduction to the Desgin
So now let's get onto using KiCad. Today you are tasked with creating a PCB that allows for an LED to turn on. Fun right!

<div align="center">
     <img src="images/Onboarding3dModel.png" width="800">
     <p><i>Figure 1: Final 3D model of the PCB</i></p>
</div>


If we look at the photo, you'll see the following labels D1, R1, and J1--these are footprint references. 
- D1: LED
- R1: Resistor
- J1: Screw terminal. (There is also a 1 next to the screw terminal. This is a footrprint text used for distinguishing the two terminals) 

#### Steps to this Simple Design
1. Make a new project: 

- File -> New Project 
- Give it a name: *Onboarding*
- Put it in a folder (for reference I put it in this folder: Documents/RSX/Onboarding)

<div align="center">
<img src="images/KiCadHomepage.png" width="800">
<p><i>Figure 2: The KiCad homepage</i></p>
</div>

- You should see something that looks figure 2

------------------------------

2. Click on the **Schematic Editor** in Figure 2
- We are getting to the section where we can choose the legos to build our house. How exciting!!!

<div align="center">
<img src="images/AddSymbol.png" width="300">
<p><i>Figure 3: Adding a new schematic symbol</i></p>
</div>

- Following figure 3 go to the right-hand side toolbar and click on the add symbol icon. You should see your mouse change into this icon
- Click anywhere on your screen and new tab should up as shown in figure 4

<div align="center">
<img src="images/ChooseSymbolTab.png" width="800">
<p><i>Figure 4: Adding symbol tab</i></p>
</div>

There are three symbols you need to add: LED, resistor, and screw terminal
- LED: find the symbol library **rsx_LED**, and doulbe click on the symbol name **LED_B**

> [!TIP] 
> To rotate a symbol Press **R**

- To place the symbol down click at the desired location on your schematic editor
- Resistor: find the library **rsx_resistor**, double click on **200R_2W**, and click again to place
- Screw Terminal: find the library **rsx_header_screw**, double click on **Screw_Terminal_2x2.54**, and click again to place
        
<div align="center">
<img src="images/PlacedSymbols.png" width="800">
<p><i>Figure 6: Adding a wire</i></p>
</div>

> [!TIP]
> A quicker way to find symbols is to search for the symbol name directly

Connecting symbols

<div align="center">
<img src="images/AddWire.png" width="300">
<p><i>Figure 7: Adding a wire</i></p></div>

- Click on the add wire icon on the right-hand side toolbar
- Connect the symbols together

> [!TIP]
> How to connect symbols
> - Click once to start placing the wire
> - Click twice to change the direction of the wire
> - Click on the edge of a symbol to stop placing the wire

<div align="center">
<img src="images/SymbolsConnected.png" width="800">
<p><i>Figure 7: Symbols connected together</i></p>
</div>


Add the power symbol 
- Click on the power symbol icon

<div align="center">
<img src="images/AddGround.png" width="300">
<p><i>Figure 8: Adding a power symbol</i></p>
</div>

- Find the symbol **GND** and **+3V3**, and place it like in figure 9

<div align="center">
<img src="images/SchematicWithError.png" width="800">
    <p><i>Figure 9: Final Schematic</i></p>
</div>

Running the Electric Rules Checker (ERC)
- Click on the ERC at the top toolbar and a new tab should open 
<div align="center">
<img src="images/ERC.png" width="800">
<p><i>Figure 10: Electric Rules Checker</i></p>
</div>

- Click on the bottom **Run ERC** , in an ideal world and what you should aim to do is to have zero errors
<div align="center">
<img src="images/ERCError.png" width="800">
    <p><i>Figure 11: Result after clicking Run ERC</i></p>
</div>


- Ohhh no, some errors seem to have occured, if you look carefully there are no drivers to our power pins. What this means is that the ERC is freaking out because there is no way for our LED to be powered--there's no external power source connected to our PCB!
- To fix this error click on the power symbol icon (figure 8), and find the symbol **PWR_FLAG**

<div align="center">
<img src="images/FinalSchematic.png" width="800">
<p><i>Figure 12: Actual Final Schematic</i></p>
</div>

- If you run ERC again you should have no errors, but if errors remain take some time to fix them
- OMG you've now completed making the schematic. You should be very proud!!! Now we get to move onto designing how the lego pieces will fit together.
------------------------------

3. Click on the **PCB Editor** in figure 2
 

Let's start by moving the components from our schematic on the PCB Editor
- On the top toolbar click on the Update PCB from schematic icon

<div align="center">
<img src="images/UpdatePCB.png" width="300">
<p><i>Figure 13: Update PCB from Schematic </i></p>
</div>

- A new tab should open, press the button **Update PCB**
- Three components should appear, click anywhere on the screen to place them down 

<div align="center">
<img src="images/PCBThreeObjects.png" width="300">
<p><i>Figure 14: PCB with three components</i></p>
</div>



<div align="center">
<img src="images/Layers.png" width="200">
<p><i>Figure 15: PCB Editor Layers</i></p>
</div>

From figure 15 you can see the layers that make up our PCB. There are a couple important layers I want to draw your attention to. 
1. F.Cu: front copper layer
2. B.Cu: back copper layer 
3. F.Silkscreen 
4. B.Silkscreen
5. Edge.Cuts

<div align="center">
<img src="images/3dModelTop.png" width="800">
<p><i>Figure 16: PCB top layer</i></p>
</div>

- If you observe figure 16 you'll see lines connecting the component together, there are called **traces**. The traces care created on the copper layers, either the top or the bottom. In this project all traces are on the top copper layer. 
- The footprint reference values: D1, R1, J1 are all found on the silkscreen layers, either the front or the back. The silkscreen is an ink layer where text and graphics can be displayed on a PCB. 
- Lastly, Edge.Cuts is used to define the size of your PCB. 
- There are other layers, but for the purpose of this tutorial only these 3 kinds of layers are important. 


Let's start by defining the PCB size
<div align="center">
<img src="images/DefiningPCBSize.png" width="300">
<p><i>Figure 17: Defining the PCB Size</i></p>
</div>

- Press into the Edge.Cuts layer and click on the draw line icon
- Create a square as shown in figure 18 which is 20x20mm in size

<div align="center">
<img src="images/CreatingSquare.png" width="500">
<p><i>Figure 18: Creating a Square</i></p>
</div>

Now let's add the ground layer
- Press into the F.Cu layer and click on the filled zone icon

<div align="center">
<img src="images/AddFilledZone.png" width="300">
<p><i>Figure 19: Filled Zone Icon</i></p>
</div>

- Click on the top left corner of the square

<div align="center">
<img src="images/PlacingGround.png" width="500">
<p><i>Figure 20: Click on the top left corner </i></p>
</div>

- A new tab should open
- make sure you select the B.Cu layer and GND (ground), then click OK
- create another square and press B on your keyboard, the zone should turn blue

<div align="center">
<img src="images/CopperZoneProperties.png" width="800">
<p><i>Figure 21: Ground Layer Properties</i></p>
</div>


<div align="center">
<img src="images/Ground.png" width="500">
<p><i>Figure 21: Ground Layer </i></p>
</div>


Let's arrange the components onto the ground plane

> [!TIP] 
> After clicking on the component, to rotate it press **R**

<div align="center">
<img src="images/ComponentsPlacedOnPCB.png" width="500">
<p><i>Figure 22: Components placed on the PCB </i></p>
</div>

- ensure the light blue lines do not cross over each other, follow the example in figure 22

- Now let's add some wires that will connect the components together, these wire are called **traces**
- on the righthand side tool bar click on the Route Tracks icon 

<div align="center">
<img src="images/RouteTracks.png" width="300">
<p><i>Figure 23: Components placed on the PCB </i></p>
</div>

> [!TIP] 
> For placing the traces
> - click once to start the trace
> - click on empty space to turn the trace
> - click on the next component to end the trace

- connect all the components together like in figure 24

<div align="center">
<img src="images/WithTraces.png" width="500">
<p><i>Figure 24: Traces Connecting the Components  </i></p>
</div>

- Press **B** on your keyboard, this allows for the ground plane to reset, if you look closely at the screw terminal you can the ground plane wrapping around the pads, but for the ground pad the ground plane extends itself such that ground is connected to ground

- You might be wondering why we left the ground unnconnected, I mainly want to show you the method that usually used which is with a **via**
- start a new trace on the LED's ground pad and click again the empty space to the left

<div align="center">
<img src="images/Via1.png" width="500">
<p><i>Figure 25: Connecting to the ground plane using a via</i></p>
</div>

- On the righthand side toolbar find the **Add Via** icon 
- click on the side of the trace not connected to any component

<div align="center">
<img src="images/Via2.png" width="500">
<p><i>Figure 26: Placing a via</i></p>
</div>

- now the ground pad of the LED is connect to the ground plane
- A via can be thought of as a hole, that allows for a trace (which in on the top copper layer) to be connected to the bottom copper layer
- Press **B** on


> [!TIP] 
> Pressing B is common practice after making changes to a PCB

We are now done the PCB, but wait we need to verify if everything is connected correctly
- On the top toolbar click on the **Design Rules Checker Icon**

<div align="center">
<img src="images/DRC.png" width="500">
<p><i>Figure 27: Design Rules Checker</i></p>
</div>

- A new tab should open, click on the botton **Run DRC**
- You should see no errors, but four warnings that tell you the reference texts are too small. 

<div align="center">
<img src="images/Warnings.png" width="500">
<p><i>Figure 28: Warnings from the Design Rules Checker</i></p>
</div>

- You should see yellow arrows pointing to the exact error 
- To fix go to: Edit -> Edit Text and Graphic Properties


<div align="center">
<img src="images/ChangingFontSize.png" width="500">
<p><i>Figure 29: Changing the Text Size</i></p>
</div>

- Follow figure 29, in scope check off Reference designator, Other footprint, and change the text width and text height to be 0.8
- click apply 
- if you run the DRC again you'll see silk screen errors


<div align="center">
<img src="images/SilkscreenWarning.png" width="500">
<p><i>Figure 30: Silkscreen Warnings </i></p>
</div>

<div align="center">
<img src="images/OverlapSilkscreen.png" width="500">
<p><i>Figure 31: Silkscreen Warnings More Detail </i></p>
</div>

- if you look at figure 31, you can see D1 overlapping the yellow line
- to fix drag D1 up

<div align="center">
<img src="images/FixedSilkscreen.png" width="500">
<p><i>Figure 32: Silkscreen fixed </i></p>
</div>

- do this for all other texts blocks 

<div align="center">
<img src="images/SilkscreenAllFixed.png" width="500">
<p><i>Figure 33: Silkscreen all fixed </i></p>
</div>

- run DRC again and you should see no errors!!!

<div align="center">
<img src="images/DRCNoErrors.png" width="500">
<p><i>Figure 34: DRC has no errors </i></p>
</div>

You are now down with the PCB layout. YAY!!!

As a final bonus, if you want to see the 3D model of your PCB...
- on the top toolbar click on 3D Viewer 


<div align="center">
<img src="images/3DViewer.png" width="300">
<p><i>Figure 35: 3D Viewer Icon </i></p>
</div>

- And you should be brought to a new page and see the image as shown with figure 1


Hope you enjoyed. This is the end. 





    




        



 










