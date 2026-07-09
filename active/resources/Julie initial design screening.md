## Over all 
- hybrid is a good option to optimize for self starting and efficiency but might not be best fit for this project 
	- hard to model?
- Darrieus if we optimized it for its self starting abilities seems the best 
	- highest peak Cp 
	- i think this would also be easier to model 
- Savonius seems like an on likely choice due to the lower efficiency 
	- does do best in low winds 
I am personally most excited about a self starting Darrieus design. I think that it has the most potential to be really optimized. I am also concerned that the benefits of doing a hybrid might not be as large when considering the potential downsides, such as wake interference. (drag vs lift issues) I also feel like they will be more complicated to design, model, simulate, and evaluate just because they are inherently more complicated so in the short time we have I think picking a simple base design and evolving it will be best. 


### Pre-existing Designs:
- va9 EN0005 Self-start Darrieus VAWT
	- 1.25 m/s self-start
	- Cp = 0.416 in the 1-4 m/s bin
	- high starting torque at low wind speed. 
		- seems like the best over all design from the pre-existing ones 
		- also well suited to the location ( high cp in the 1-4 m/s wind which is 
- vj20 hybrid VAWT 
	- Cp = 0.486 - highest low wind bin
	-  2.81 m/s cut in (not amazing)
- va3 Venturi Wind Turbine
	- low cut-in: 2 m/s 
		-  source gives yearly output values for 4-7 m/s average winds- very similar to what wind speeds we will have 
- va20 Involute Rotor with Wind Flow Modifier
	- Cp = 0.397 at 5 m/s
		- no cut-in is reported
key things to look for seem to be cut in speed and Cp values for 4-5 m/s winds 

### Parameters
- deflectors/curtains 
	- can be used to speed up the wind before it hits turbine
		- meaning then low cut in speeds could be slightly less of a concern so pairing this with Darrieus design could be good
			- would this be hard to model?

### Darrieus thoughts 
- main concern it cut in speed 
	- could be tweaked with airfoil choice, solidity, pitch, and profile optimization
- h- shaped Darrieus seems o be a better fit than helical because helical seems to have some trade offs with Cp witch would hurt performance 
- is the data we have put in enough to rule out start up as a huge problem?
	- some turbines need the wind to be above the cut in speed for a certain amount of time for them to cut in so hourly readings might not be as accurate to real cut in time 
		- checked this 96% of the measurements were at speeds above 1.25 for at least 3 straight hours - so probably not an issue 
		- and 77% for 2.8 m/s winds for the 3 hours in a row 
	- also depends on how the wind is changing with time
	- is the wind data we have accurate enough for the spot we would really put the turbine?
- Best Darrieus subfamilies for BOS. 
	- Straight-bladed H-Darrieus  
		- 
	- Helical Darrieus
	- Troposkien 
	- Eggbeater
	- 



2. Rank the best startup-improvement strategies for an H-rotor at BOS.
3. Build a shortlist of 5 specific designs consistent with this updated family choice.