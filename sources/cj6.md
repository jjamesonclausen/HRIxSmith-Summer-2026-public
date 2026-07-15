---
title: "Simscale Wind Simulation (How to use)"
source: "https://www.youtube.com/watch?v=yXk2W4x5t5I"
author:
  - "[[Sean Yu]]"
published: 2021-05-27
created: 2026-07-15
processed: true
description: "Enjoy the videos and music you love, upload original content, and share it all with friends, family, and the world on YouTube."
tags:
  - "clippings"
---
![](https://www.youtube.com/watch?v=yXk2W4x5t5I)

## Transcript

**0:01** · hi everyone um welcome back to another insurance tutorial um this tutorial we will try to analysis win um to use a sim scale as the um web-based um application to you can um import your 3d models to analysis the wind velocity also the wind pressure

**0:34** · green space as well so that's some result i have been done on previous projects so let's begin to set up the new one

**0:54** · so i will just draw a simple geometry to represent as the building maybe a bit too big um smaller yes and also some geometry over it to see the wing um how to behave

**1:24** · so let me put as a ghost so that is the whole environment and then my building is sit in the middle just remember we need to have um really high um high head space for that so it can be more accurate because the wind accelerates on top a lot and you may

**1:51** · don't want to miss it if the box doesn't capture the space um the outside of that won't be simulated so let's reference that as a \[Music\] reference the box first

**2:13** · and then we set another breath um the whole representing the whole area the air so um what we need to do is we need to

**2:34** · subtracting between those geometries use some solid difference so it's a v don't preview it yet see how it looks subjection \[Music\] nope that wasn't what we want to see

**3:03** · maybe just like um change it um sorry we got some error but because um the boxes is wasn't intersecting

**3:20** · any so we just need to drag it along to the ground plane just a bit further so that will be the whole object we're gonna put in the simulation um what we need to do we just need to back it also group it it's always nice to have

**3:43** · done period then we could select that to export select once we exported that geometry as a rhino 3dm model

**4:04** · we go to same scale open up a new project it's a bit um you need to set it up um it's a new project this is wind dash one um can create i have to five characters so the arc seven chip of five

**4:46** · so once we created um project required to import the geometry so we just need to import the one we just been created

**5:10** · just hit import because it's relatively um really simple um geometry so it won't take too long um create a simulation we choose incompressible that's what we try to analysis the wind throw let's create the simulations

**5:40** · and then they already selected the geometry for us and then what we need to do we need to set the materials as an air um yep like um rotate it a bit to get a little bit more better to see we can change the view here so i decided the box

**6:09** · and click okay that's the whole thing as the air and then at least have the country condition let's clear the list and it is signed so we try to analysis the wind come from the top to the bottom the ring in that will be that one

**6:45** · we didn't try to select pretty well okay for selection yeah many was okay we've got a tick um some still got some input missing it will have a red red circle so we try to we need to set it up as some pressure outlet for the

**7:13** · four faces three faces four faces in the rest of the thing so we got the one in that and the red should be the outlet for the air pressure out uh also in this set of war geometry which could be the ground plane and also the boxes um

**7:51** · so we can assign the geometry us the whole thing and then click okay and then we're gonna side the air also the whole boxes okay

**8:19** · so we imagine the whole thing inside the boxes is filled with air and then the velocity inlet should could be in the front pressure outlet will be in the rest of the faces except for the ground plane

**8:47** · in the water geometry it will be the ground plane and then the building itself sign yep so that is basic setup

**9:11** · so to get the velocity um from the x directions i mean for the uy direction we could um look for your location like melbourne room rose to find out where the predominant win in your area i will select

**9:48** · melbourne and then get the roses

**10:27** · so we have the rimrose um also could be generated from a ladybug tool um with the epw file um so it's i separate two data from winter and summer um

**10:47** · we maybe use the winter data it's not because only predominant wind from south to north is also the winter winds could be um drop down the surface temperature a lot and because the human feeling of the um

**11:08** · of the utci stuff is really drifting by um wind speed so we kind of use the 626 as um the average velocity velocity of um winter situations so we just try to get the 6.26 and then got the inlet done

**11:39** · and then we should able to run the simulation
