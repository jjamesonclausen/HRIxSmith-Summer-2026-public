---
title: "SimScale Simulation Part 1: Savonius Semi Circular VAWT"
source: "https://www.youtube.com/watch?v=bgOTUX5E-f0"
author:
  - "[[Catchment of Resources]]"
published: 2025-07-14
created: 2026-07-15
processed: true
description: "#windturbine #vawt #SavoniusDiscussing basics of CFD and FEA on a Savonius VAWT using SimScale free version. To subscribe:  https://www.youtube.com/@catchmentofresourcesTo follow:Facebook: htt"
tags:
  - "clippings"
---
![](https://www.youtube.com/watch?v=bgOTUX5E-f0)

#windturbine #vawt #Savonius  
  
Discussing basics of CFD and FEA on a Savonius VAWT using SimScale free version.  
  
To subscribe:  
https://www.youtube.com/@catchmentofresources  
  
To follow:  
Facebook: https://www.facebook.com/CatchmentofResources  
Website: https://catchmentofresources.com/  
Email: info@catchmentofresources.com  
  
SimScale CFD and FEA Website: https://www.simscale.com/  
  
How to use SimScale for a quick test for functionality:  
https://www.youtube.com/watch?v=WsPy\_TJotv4  
  
Royalty Free Music: Bensound.com  
License code: ZM024SGQ1BY8PLS7  
Artist: : Benjamin Tissot

## Transcript

**0:00** · In order to model this salmonious vault in same scale, first of all need to generate an IGES or ST file in any CAD program.

**0:12** · So I've already previously generated a vertical axis when you combine Sonius with a semicircular profile.

**0:20** · So once you go to the website, I've already posted the website address on the description. And I also posted a video which could help with a quick way to understand sim scale and use it for your own analysis. In order to understand what sim skill can do before you can actually use sim skill online, you'll need to register and the developers are also going to provide you some helpful tips on how to use it.

**0:48** · You may not have so much time to read everything because you are just testing. for that video tutorial will really help you to understand how to go about testing sim scale for this vertical combine exercise. So the first thing is to import the IGS or the step file which I already have here from a CAD program. So it's just basically the body parts that important to you that you use for the import.

**1:20** · Because it's important, you need to edit it. In this case, I've not done any major editing besides what was done in that previous video.

**1:30** · So, what was edited is the air foil, the air flowing around this harmonious vault.

**1:40** · So, you can watch it on the screen now.

**1:50** · So this is creating a boundary for the air pressure that is flowing around the vault system itself.

**2:00** · So once this air pressure the boundary has been created. You be able to know how far the air is going from one point to another.

**2:09** · And let me just give you a hint. It's possible to actually validate this on site by for example you're using a wind tunnel.

**2:19** · If you actually apply pressure or wind to a subs you will see the point where the wind is largest at the wake. You can then take your sensors to pick up the value at that point to know whether it ties with the value in CFD because when the wind hits one part of the wind turbine

**2:43** · it diverted the wind to a certain direction but there's a point in that direction that is maximum once we get to that area in this video I'm going to point it for you to see how practical CFD can be made in the field or in the winter lab.

**3:10** · So there are times where you have some conflict with the drawing that was generated in which case I was having some conflict with the bottom part. So I have to delete it directly so that it doesn't cause any issues because some of these parts in the real sense they are not moving. They are static parts and these static parts can be designed for movement and stresses as a static element.

**3:35** · So it doesn't necessarily require lift and drag in the elaborate sense in the way that the sabonus profile will require.

**3:48** · We define the external body and accept certain values and move ahead to boolean operation which is to subtract in order to obtain the air that is flowing around the V.

**4:13** · \[Music\]

**4:36** · So here we're going to perform the boolean operation.

**4:53** · in which case we're going to subtract.

**5:04** · Click on apply. Once it applies, if there's no error, then you need to go ahead and delete those singular.

**5:16** · So once there's no error and the intersection has has been done, you need to go and delete all of those model parts because you're going to get an error if it is not done. The flow region has been subtracted contains both the air volume and the air foil the profile of the sabonius vault together.

**5:40** · You can see that highlighting the flow volume flow region is actually showing the sabonius vault inside even though you deleted the individual profiles of the vault. So that will prevent you from having any errors.

**5:58** · So we see once you see it it takes you down to this page where you select create simulation.

**6:05** · So once you create simulation you can then select it as an incompressible fluid.

**6:12** · Um I wanted to select other option but let's make it simple just incompressible fluid and the fluid is air which is flowing around the sous vault.

**6:34** · So the help file that will be sent by the developer will help you to be able to utilize to the max same scale. So you utilize all of its functionalities. But yeah, this is just a quick tutorial so that one knows how to use sim skill for simulating CFD and FA.

**7:00** · So the materials for the incompressible fluid is A. You select A and apply.

**7:07** · The next thing is going to be the wind speed. the boundary conditions.

**7:14** · So the boundary conditions are the wind speed at the inlet and at the outlet.

**7:29** · So the inlet is positive x direction.

**7:39** · So these are the values we used for this simulation.

**7:44** · \[Music\] 11 m/s.

**7:57** · So once the once the velocity has been included the next thing is the pressure the pressure of the wall at the back which we are going to highlight. And so once the velocity has been imputed at the inlet of this flow volume at the outlet you're going to have a pressure volume.

**8:23** · So once the inlet velocity has been specified at the outlet you're going to specify a pressure of zero similar to that tutorial. So let's just follow it accordingly and see the outcome for this analysis.

**8:38** · You can always go back once you have a full understanding of same scale. You can then go ahead and run a more elaborate analysis.

**8:48** · So I'm making all the other ones to be sleep walls.

**8:54** · priority analysis. So once all of this is accepted is then possible. You can always adjust the mesh but it will take time. So but this is because this is a quick tutorial adjusting the mesh. I adjusted the mesh earlier during some trials and it took quite a long time. So we just take the default in the system and then we'll go ahead and run this analysis.

**9:46** · Okay. Specify forces and moments.

**9:50** · that you require in terms of the outputed results and the forces and moments are going to be computed.

**10:04** · So that's for FEA. So in which case you're having CFD on one side and FE on the other side. So these are selection of the settings.

**10:38** · Next, we're going to run the simulation.

**10:40** · You can give it any name. So, you see here 6 to 22 minutes. long. It's going to take

**11:11** · \[Music\] So at the end of the simulation you can then postprocess the results.

**11:32** · Once you click on postprocessing, the first information that comes up are different cutting planes in different directions.

**11:40** · It will be X, Y or Z. So they started out as Y. So I switched it to Z so that you can have an information of how the wind speed spreads in a horizontal plane.

**11:57** · So this power this values now at the wind speed how it flows over the profile.

**12:06** · \[Music\] So you can see how you can see how the wind builds up from 11 m or 12 m/s and going all the way to about 14 m/s in some cases. So there's usually a build up.

**12:25** · So I remove the external boundary of the air volume so that we can see the object of analysis much clearer. Again, that can be found in the tutorial.

**12:47** · So this is the Z direction of the wind speed. So you can see how the wind diverts in which case I'm saying that from this you'll be able to understand where the wind is going to be largest behind the vaults so that you can then test it in the field or in the wind tunnel to validate what has been done in CFD. You should be getting similar values compared to what you have here on the CFD. So that's what I explained at the beginning of this video.

**13:36** · So changing the part color from velocity to pressure is how you'll be able to see the pressure effect on the wind turbine profile. So you can see here the pressure on it close to the edges and at the midsections you have heavy stresses acting on this um wind turbine profile.

**14:08** · So from here just as it was done in that tutorial we're going to see how the flow volume of air relates or interacts with this Sonia's vault profile.

**14:21** · We're going to see how it was done in this case.

**14:28** · So because this is um an internet based application, sometimes the internet um makes it slow a bit. So it depends on how fast your internet um services are. But for mine, it was a little challenge during this um video editing session.

**15:12** · So this is just analyzing the different forces that are acting on this semicircular profile.

**15:23** · So you can see forces, you can see pressure in the different direction X, Y and Z direction.

**15:30** · \[Music\] You can see all these values here.

**15:35** · \[Music\]

**16:15** · So here now is particle tracing. to see how the air profile flows around the surround profile.

**16:35** · So you have to pick it from the length of air into this air ball.

**16:42** · But initially when I did it the first time, I picked a point that was at the outlet of the flow volume.

**16:51** · So once I hid all the other objects, I was not able to see the airflow around the so I had to switch it around. I turned the model around to the right X direction. And when I use this particle tracing again, it showed the airflow around the harmonious profile.

**17:16** · So you can see it it's not showing any air flow around the wind turbine system.

**17:21** · So when I now checked with the cross-sectional pressures, that's when I realized that the wind speed was dropping before the wind turbine system. Hence it confirmed that the orientation of the wind turbine system was not what was being expected meaning that the inlet was on the other side.

**17:43** · So it was switched back and then the particle tracing was tried again in which case you'll be able to see the outcome.

**18:10** · \[Music\]

**18:32** · So after hiding the external fuel volume, you can then see the air pressure and the air interaction with the vertical axis when turbines. Thank you for watching this video. This is catchment and resources where we create a for
