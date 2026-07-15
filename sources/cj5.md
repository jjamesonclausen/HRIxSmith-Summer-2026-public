---
title: "Virtual Wind Tunnel - SimScale Tutorial - No nonsense"
source: "https://www.youtube.com/watch?v=WsPy_TJotv4"
author:
  - "[[Computery Things]]"
published: 2024-06-22
created: 2026-07-15
processed: true
description: "see video"
tags:
  - "clippings"
---
![](https://www.youtube.com/watch?v=WsPy_TJotv4)

see video

## Transcript

**0:00** · all right good day guys I'm going to try and show you a non-nonsense tutorial on how to use sim scale to quickly get from your CAD model to the pretty colors and the information you might want in terms of the force of lift and drag Etc so let's get into it let's jump over to sim scale right here click on start simulating

**0:24** · now now we're going to create a new project so that's up in the top right new project uh you can give it whatever title you want this doesn't matter all that much once you've created a new project from the dashboard the first thing it'll ask for is the geometry uh I'm assuming that from your 3D modeling software you know how to export your geometry as AEP file it's

**0:52** · the most common format for computerated designs and it is what solid works wants so go to import from your computer uh throw the file into there and press import that'll take a second to upload now unfortunately you can't just use the model as it is you do need to do

**1:13** · a little bit of extra work so once the model's in there you want to then edit it in CAD mode uh okay so press on that and the important things we need to do here is we need to set up the volume of air that is around the model and then we have to cut

**1:35** · the the volume that the um that the aircraft is taking up out of the air um that we're going to make now so first thing press up in the top left flow volume external and that'll add a bounding box around the thing uh you can adjust here with the numbers how big that box is um obviously it'll run faster if there's

**1:59** · less air that it has to think about as it runs the computations uh but you'll also maybe lose a little bit of accuracy uh I'm not really sure but anyway that's that uh press apply this will create your box now up in the about the middle of the toolbar you want to use a Boolean operation to cut the airplane out of the air and obviously you're choosing subtract from the drop down Boolean options there the target

**2:28** · body is your cube of air and the tool body is the aircraft which it's a bit difficult to click through things to select it so just use this list on the right um and choose your aircraft there it'll go red to show that it's the it's the thing that we're removing um you can discard the tool in

**2:47** · other words the the model is going to vanish from the file you should do that as well and press apply and that'll be all we need to do in the cad workspace and we can go back to the simulation to get back to where we were we just need to click save as copy up in the top

**3:07** · right we press that it'll bring us back to our simulation and we have now two regions we've got the aircraft that we originally imported and we have this new copy which is just the air around the aircraft go ahead and delete the aircraft because otherwise Sim scale will um complain at you if you don't do that so now select your box of air minus

**3:34** · airplane and choose create simulation for simple aerodynamics you just want to use incompressible so create simulation down the bottom right here we go all of this that's fine just press save uh now what we need to do is tell tell the simulation what material all of this is made out of and it's made out of air so just go to materials press the little plus symbol choose air and apply so now this box is

**4:06** · a box of air press save now we're going to set up some boundary conditions and what this is is uh which what each of these faces of the Box do so we want to blow air in from the front of the aircraft obviously and we want to have a way for that to escape uh and then everything else um well I'll show you as we get there so create a velocity Inlet to blow air into the cube of air choose your front side face and then uh you

**4:35** · want to choose a value of the air velocity also very important here to pay attention to which direction the air is going so if I look down here at the bottom right there's a little vew Cube I can see that the Zed arrow is pointing at the nose of my aircraft which means that my air air speed my air velocity um

**4:57** · needs to be positive Zed so I'm going to go to zed here give it a positive figure let's say 30 m a second and that will do there so we have our velocity the fluid is being pushed with that velocity from the front now we need to let the pressure out at the back so create a pressure Outlet boundary condition put that at the opposite face

**5:23** · and we want to send that down to zero pascals so we'll just gauge pressure zero press save and then all these other the other faces of the Box the other four faces we're going to make those slip walls so press add choose wall uh highlight all four of them and then up here under boundary condition wall set velocity to slip so

**5:47** · um I think how that should work is it essentially just lets the air slide kind of frictionlessly from the front to the back without interfering too much so save on that now we're almost done the last thing we want to actually get valuable graphs and uh and numbers uh we will need to tell it which

**6:11** · surfaces of this um geometry is the bounding box and which surfaces have the forces acting on them that we're interested in so because this is a an aircraft and it's floating in in the air it's completely you know suspended in fluid uh we're interested in all the surfaces so go to results control expand that out and then under forces and moments press a little plus here and add

**6:39** · forces and moments now this part is the sort of tricky part cuz we need to select all of the faces belonging to our aircraft uh and not these boundary faces so what I do here to select the faces is click on the entire model there on the top right and then you can just unselect out of there uh the six faces of the cube by re

**7:05** · clicking those individually um and now you see there's a white outline around the aircraft and there's black outlines around the cube that means you've done that all right so press uh also if you do know the center of rotation of your aircraft if it's different from where the the thing has automatically put it uh it would help you to to set that now anyways we'll just leave that as it is we press save and we are finally ready to go so down in simulation runs we'll start the

**7:41** · simulation uh you can give it a name if you like and this will take a very long time so we will come back we start restart recording when it's done okay it is now 3 months later and the calculations are complete um no it actually took 17 minutes not too bad um once that's done you press uh postprocess results okay and here we are finally in the part where we get to see the pretty colors so um by default you get a uh

**8:14** · cross-section top down cross-section plane um I'll show you how I like to set this up first thing you probably want to do is hide everything that isn't your vehicle so just click on each of the faces once and press hide

**8:36** · selection and that gets you down to just your vehicle and uh even though this so cross-section planes might be useful for some people I prefer to turn that one off and for part color I like to have um solid color which shows the

**8:57** · pressure um and so this will show you where the pressure is at down the bottom here you can adjust your color scale so I like to have a continuous scale uh use continuous scale and then also to bring in the upper and lower bounds so you get a bit more of a gradient in the areas where you're interested in um so you can see the effect of bringing that in now

**9:30** · and this will help this helps you to pronounce uh where the effects are sort of taking place so as you can see in this particular aircraft we have the very very low pressure zones here just before the the winglets or the vertical stabilizer we have very very high pressure right on the tip of the nose and on the motor mounts

**9:55** · um and of course across the entire Leading Edge is pretty high pressure then underneath you can see it's generally higher pressure than on top where it's a nice blue and green underneath is sort of a orangey color so that shows the the kind of pressure differential which leads to a lifting Force speaking of lifting Force you probably want to know exactly how much force your aircraft is going to be lifting by uh for a given um velocity so that's where

**10:27** · we go to the force plot so down bottom left here click on forces um and moments plot and it comes up with a very confusing graph basically what we're interested in because if you remember our model had the the air was moving in the positive Zed Direction the upwards is in the direction that we want to get lift was in the Y positive y

**10:53** · direction and on this particular graph this black line is pressure Force y so we can see here that we are getting and and the numbers start out crazy that's just because of how the computation uh works and eventually they should converge to a nice stable value so really you're only interested in the figures that appear kind of at the most right side of this graph they're going to be the most accurate so what I'm seeing here is we get 36.9 Newtons of

**11:24** · force in the upwards Direction so that's 36.9 Newtons of lift on this uh model aircraft go back to our run just click on that Cog uh sorry click on this post process results to get back to where we were or um solution fields from underneath run one which is our first run of the simulation to make some more of those sort of cool graphics you usually see particle Trace up here in the top left is a good one to to go for and then this little circle button here

**11:56** · is how you reposition the start part of the particle Trace uh it has to be positioned on your Inlet wall so the front or back face of the your geometry had so I'm going to have to invert visibility to bring that back and then we'll click this here in the middle

**12:15** · somewhere now you can see it creates that grid of purple dots those are the the starting points of the particle trace and if we invert visibility again you'll see that they flow through the streamlines from from that point where the velocity is first injected and

**12:34** · they go around the the model day yeah there we have it so that is how you quickly get from a plain model to the fancy colors and streamlines and figures such as your forces uh of your net pressure force of lift and so on I hope that was helpful uh if you found anything wrong with this please let me know if you're an expert at Sim scale I'm just trying to help you get uh up and started uh quickly With No Nonsense so yeah
