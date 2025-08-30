# Introduction to KiCad
## Onboarding project

Welcome all. I'm going to make a couple of assumptions which is you have no idea how to use KiCad or maybe you don't even know what KiCad is, but trust you are in good hands.

Let's start with the basics...

> [!IMPORTANT]
> In order to proceed with this tutorial you must 
> 1. Download KiCad onto your local computer (download the most updated please)
> 2. Clone this repository onto your local computer: [rsx_standard_library](https://github.com/rsx-electrical/rsx_standard_library)


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
     <p><i>Figure 1: Final 3D model of the PCB/i></p>
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

- If you run ERC again you should have no errors, but if error remain take some time to fix them


OMG you've now completed making the schematic. You should be very proud!!!


3.  Click on the **PCB Editor** in figure 2





    




        



 










