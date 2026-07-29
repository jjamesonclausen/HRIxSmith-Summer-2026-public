# Daily Work Log

Source PDF: `active/Daily Log for Honda Project - Julie & Anna.pdf`

## Week 1

### Monday 6/22

- Meeting with Mike at 9
- Start learning fluid mechanics - 9:30 (`4 hr`)
  - Used AI to see what topics I need to learn for this project and what order would be best to learn.
  - Review Anna's notes + past lecture slides
  - Watched recorded lectures on YouTube
- Read through previous capstone report - 3:00
- Met with Mike and Anna to check in - 4:30
- Continued to read though and take notes on capstone report (`2 hr`)

### Tuesday 6/23

- Continue to review past report + go though some references [[n2]] - 8:00
- Meet with Mike and Anna - talk bout milestone setting + meeting later w/ Ryan - 9:00
- Going through appendix of report + research on VAWTs (`3 hr`)
- Review of fluids content (`3 hr`)
- Meet with Ryan, Mike, and Anna - 4:00
  - Download open code visual studios and obsidian and email Ryan

### Wednesday 6/24

- Download open code - 8:30
- Meet with Mike and Anna - 9:00
- Set up open code and get it running in visual studios + email Ryan (`2 hrs`)
- Read through GitHub + play around with VS (`4 hrs`)
  - Work though the workshop
    - Download obsidian web clipper for future use
- Meeting with Anna and Mike - 3:00

### Thursday 6/25

- Finish up the workshop - 9:00
- Meet with Mike and Anna - 10:00
- Stayed on with Anna and worked on combining forces
  - Figured out GitHub and working asynchronous
  - Attempted to figure out obsidian web clipper for images
  - Got live share working to collaborate in real time
  - Added to rules page to fine tune the llm wiki
- Watched YouTube videos to learn about GitHub
- Call with Mike to give update - 3:30
- Stay on call to continue working with GitHub

### Friday 6/26

- Meet with Mike and Anna to set up plan for the day - 9:00
  - Find sources to feed to the llm
    - Both on VAWT and add in some content about fluid dynamics
  - Practice using git to collaborate
  - Together test the llm on the new material and update rules page and eval set as needed
  - Figured out how to get open code to convert pdf to md with referenced images (though adding to agents page)
  - Added some extra sources
- Meet with Mike and Anna - 3:00
  - To dos: research/import more papers, refine evals, fix images problem
  - Use smith libraries page to locate more sources
- Continue trying to fix images problem

## Week 2

### Monday 6/29

- Set up to do list + look for sources - 8:00 (`1 hr`)
  - add sources
  - continue to test
  - get images working/fix cropping problem
  - Obsidian figure out what its good for
  - Have it auto process new files
- Meeting with Mike + Anna - 9
- Continue to work on wiki (`3 hr`)
  - Add some sources
    - in last years report they did reference a few science direct pages - which there are so many articles form that i can seem to get access to - and so you think there is a way that they found them that we haven't found
  - Have it test me
    - Just thought on this it seems to be focusing a lot on small details - like build material - rather than overall concepts not sure how to fix this
  - Refine agents page
  - Work on images problem
    - Ran into more problems with it editing text directly in sources and formatting errors - taking a long time
  - Continue to work on changing pdf to md flies - experiencing a lot of issues

### Tuesday 6/30

- Make slide for meeting later
- Meet with Anna and Mike - 9:00
- Stayed on call with Anna to sort out the schema pages and fix the image issue we have been having (`3 hr`)
  - Installed python and got it working
  - Restructured the agents page
  - Fixed up some files that were not looking right
- Worked on slideshow for meeting later
- Meet with Ryan, Mike, and Anna - 4
	- [[Notes from meeting June 30th]]

### Wednesday 7/1

- Meeting with Mike + Anna - 9 am
  - Todo
    - Fix wiki pages with errors
    - Add more sources/read through them to get better understanding
    - Look at zoo keeper
- Re added all original pdfs that were deleted before we had current protocol
- Renamed all original pdfs to match the source mark down file so the llm could trace it back quickly.
- Went though and fixed all summarizations that the llm made when reading though source pdfs and converting to md files
  - And corrected strange line breaks + poor image placement
- Corrected all images that were done incorrectly before we were using python
- Added metadata to all source md files that were made before we had the schema page made
- Updated the schema page on converting pdfs to md based on a misunderstanding that the llm was having (had to clarify that if the full publish date was not available that it should put in whatever information it could find like year and not just leave blank)
- Added to the AGENTS page - information on why we are building this agent in hopes of it knowing how to best organize data for us
  - Added: "Specifically you are going to help the human in learning about and designing a VAWT. You should organize your wiki with this in mind."
    - Not sure how much this will change but i think its a good start it might need some example so help understand what would be a good organization system
- Asked it what ideas it had for more organization based on the addition to the agents page and it suggested a lot of new pages - which i prompted it to make
  - I'm thinking about what would be the most helpful in terms of keeping track of different designs, but we would have to figure out what classifies a unique design which might get to be pretty challenging.
  - Ideas around obsidian
    - I think it could be good to ask the llm to anytime it uses a word/term that it has a page in concepts/methods on to automatically link the page, for example if when talking about a particular design it mentions tip to speed ratio it should make it a link to the page explaining what is it.
      - Only concern is that some of these things might be mentioned too much for the connections to be helpful
    - Alternatively we can spend some time identifying what the key design choices are that we will make (like TSR) and ask the llm to tag that so we can see the connection in obsidian
  - Could be helpful to make and "equations" page with all equations and links to pages ??? (not sure applicable this will be yet)
- Spent some time looking into obsidian data view/practicing + reading about it to learn how it can be helpful
- Look at zoo keeper briefly

### Thursday 7/2

- Met with Mike + Anna - 9 am
- Continue to work with Anna to repair old source pages that had been summarized + add new ones
  - Fixed links that were not working
  - Added some wiki pages + organized
    - Now has two new sections + tags one for designs and one for parameters
- We were very happy with the results of this
- Think about tags to add - decided to add design type tag and parameters tag (we can search

## Week 3

### Monday 7/6

- Met with Mike and Anna - 9 am
- Stay on call with Anna to decide on location/design constraints, fix up some meta data issues and make small edits to agents and schema pages to get the parameters page looking good - `2.5 hr`
- Look for more sources + process some - `1 hr`
- Continue looking for more sources - fixing the ones processed wrong + having it process new ones - `4 hr`
  - Was having Problems ingesting sources - wouldn't add pictures or equations + was summarizing + missing meta data
    - Switched to gpt 5.4 and then got it working just a little slower
- Meeting with Mike + Anna, discuss project timeline, issues from today, and tomorrow's tasks - `0.5 hr`
- Finish uploading more sources - `0.5 hr`

### Tuesday 7/7

- Finish ingesting some sources - 8:30
- Met with Mike + Anna - 9 am
- Stayed on call with Anna to set of slides for later - `0.75 hr`
  - Left a place holder for questions about zoo keeper
  - Meeting note
    - Qualitative vs quantitative - having it rank the effective news vs having it in put a number - can we trust its ranking - can we trust the numbers if some are missing
- Download and mess around with zoo keeper - `4 hr`
  - Connected to GitHub
  - Did tutorial
  - Messed around with zoo keeper - trying to have it re create va5 design
  - Watched some YouTube tutorials on kcl
	  - [KCL: Parametric design with functions](KCL: Parametric design with functionshttps://youtu.be/JtCk20aTTOU?si=56fikWPQFCBU-tVx)
  - Toyed around making basic shapes + windmill shapes with tools
  - Potential questions
    - What are the collaboration options/how will that look
- Finish uploading final five sources to wiki - `1 hr`
  - Quick call with Anna to finish up slides
- Meeting with whole team - `1 hr`
  - + [[Notes on meeting July 7]] - `0.5 hr`

### Wednesday 7/8

- Met with Mike + Anna - 9am
- Stayed on call with Anna - `3.75 hr`
  - Picked out location + find [data on the airport ](https://mesonet.agron.iastate.edu/request/asos/1min.phtml)
    - Looks great has wind speed wind direction wind gust direction + speed
  - Look into airport regulation (air space)
  - Extract all data + convert to a json file + md file (and make folder)
  - Upload vj28
  - Think about design constraints now that its at an airport
    - No noise consideration
    - Height limitation
    - Visibility problems?
    - Scale - how many could we put?
  - Consulted the llm on the location and wind data
    - Made histogram of wind speeds
    - Asked for advice on what to focus on
    - Gave pros and cons of the location + what would be good to optimize for
    - Thought for a while about start up speeds
- Creating a workflow/plan

### Thursday 7/9
- Met with Mike + Anna - 9am
	- mike will contact brother about [ airport regulation](https://www.ecfr.gov/current/title-14/chapter-I/subchapter-E/part-77) 
	- gave this to the llm
- stayed on call with anna to finalize plan 
	- rename wind data 
	- clean up files that aren't needed 
	- write up final plan 
		- refine with llm edits 
	- lock in on location
	- create [[design goal]] md file
- spent some time learning + asking questions to come up with designs/concepts worth perusing 
	- [[Julie initial design screening]] 
	- added another paper on h-type Darrieus VAWT 
	- looked into wind data 
- call anna 
	- get minute by minute data!!!!
		- look at direction change 
		- consistency of speed for cut in prediction 
- call mike and anna 
- stay on with anna 
	- rank all designs 
		- come up with weights +categories 
		- compare to each other + LLM 
			- had it do ranking of h type, and all designs 
- decided on h-type!!!
### Friday 7/10
- Met with Mike + Anna - 9am
	- talk about how anna and I are feeling about our learning process and the LLM application generally 
		- we were about to select top two designs to iterate on in about 1.5 hours which we both agree is pretty insane. the LLM was super useful for quickly comparing information and we found making weighted decision tables to be super helpful. we created several personas - such as a experience professional who wants to make the best possible VAWT, someone who has no engineering experience or CAD software experience who wants to make a good vawt with their limited skills, and we also personally came up with rankings and compared the top five results from each test. 
		- we do feel like we might be missing some learning though using these tools. since we are using the llm to rank the technical details of each design we are not forced to struggle with all the concepts in the same way the previous team did (which is were learning is done)
		- at the same time though we might have a better full picture understanding of these concepts because the LLM can synthesize all the information across a ton of trusted sources. we have essentially created an expert in the field who can pull up any information on command that we can question at any time. this i feel is the main gain of the LLM wiki, I can ask any sort of question just to see if the idea could be found. 
		- anna and i separately discussed the zoo keeper agent. she said in her perspective that when doing CAD software you want to perfect and spend along time on the base of the model so that future edits go smoothly. I do have slight concern that although zoo keeper feels very promising because of its ability to quickly model a whole turbine, that the actual structure might not be that solid. 
- anna and I stayed on the call to finalize the design that we will select
	- we made some additional rankings and saw the same two on top and so we will move forward with va9 and vj20 designs. 
	- created a page to track what prompts the LLM will make for zoo keeper to model off of 
- spend some time playing around with zoo keeper 
	- export convo to save how it was made - add to cad log folder in active 
- spend some time reading through va9 and vj20 and questioning the LLM on the designs to learn more 
- tried to make initial model in zoo keeper 
	- having issues with it editing parts that are okay when i prompt it to change other elements 
	- felt frustrated that i couldn't manually edit things so i told it to any time it made a change tell me what line of code it touched and what edits i could tweak manually 
## Week 4

### Monday 7/13
- play around with new models - terra and Luna - to learn more about parameters (2hrs)
	- make a page called [[VAWT_basics]] comparing the Cp + cut in for vj20 and va9
		- also has reports of some information i was asking for to learn more about VAWTs in general 
- Met with Mike + Anna - 9am (.5 hr)
- stay on call with anna (2hrs)
	- play with sim scale - tutorial 
	- make a [[Decision Making Process]] page to better document the choices made 
- watch videos on sim scale (1.75 hr)
- play with zoo keeper to make simple things to test in sim scale 
- attempt to run a simulation (2hr )
- call mike to update on the day (.75hr)
	- got brief introduction to the theory behind sim scale 
- stayed on call with anna (2.5hr)
	- ran through three simulation together 
	- had issues with verifying the results 
		- used the LLM to trouble shoot our results - didn't have a ton of success 
	- confused about last years reporting of their set up 
	- tried to make a diy 2d simulation (really thin boundary layer) 
- total hours - 11.5
### Tuesday 7/14
- some work before meeting (2 hrs)
	- made slides for presentation watched a you tube video in a [Savonius vawt cfd sim scale](https://www.youtube.com/watch?v=bgOTUX5E-f0) 
	- ran a simulation on a random airfoil to practice the set up 
	- found an example of a cfd for a VAWT
- Met with Mike + Anna - 9am (0.5)
- meeting with anna to make slides (3hr)
	- practice presenting on teams 
	- put in screen shots of 
- continue to learn about sim scale + add some speaker notes to the slides (2hr)
	- [helpful video on CFD set up](https://www.youtube.com/watch?v=WsPy_TJotv4) 
- meeting with the team (1hr)
	- [[Notes Meeting July 14]]
- keep working on sim scale / notes on meeting/ reflections/ implement their advice (0.5hr)
- total hours - 9 
### Wednesday 7/15
- update daily log, write some notes on yesterdays meeting (1hr)
- Met with Mike + Anna - 9am talked about plan + yesterdays meeting (0.5hr)
	- notes from mike for future meetings 
		- pause more between concepts and try to solicit more questions so that the meetings are more conversational and less presentation like 
		- slow down more 
		- include more thoughts about the process and learning about learning 
	- this week we should orient slightly more toward learning as opposed to strictly project goals 
		- how to use LLM to learn hot to do CFD
	- deliverables for this project are to have a "user" manual for a team in the future on how to best use and LLM or other ai tool to learn and aid their project 
		- we want documentation on best practices not necessarily and amazing final turbine 
			- in other projects learning is somewhat more forced like being forced to learn how to use fusion, but with ai tools you have to be more intentional to not take a back seat in your own project. have the tools you made help you, have them quiz and teach you. in this project though the force learning is learning how to use all these tools. learning how to set up a wiki and use obsidian and vs code. learning all the ways it can aid you and how to set it up to be tailored to your needs. you learn how to learn form it. 
	- suggestions from yesterdays meeting 
		- have the LLM make a visual decision matrix so we can follow its thought process better 
		- ask for serval diverse answers 
		- orient the LLM to CDF this week 
	- 
- stay on call with anna to start setting up the CFD part of the wiki (4 hrs)
	- edits to schema pages for naming scheme 
	- anna adds all documentation form simscale on how to use 
	- i find some papers on CDF testing of VAWT 
	- use obsidian web clipper to add you tube tutorials 
		- keeps timing out but overall terra is quite fast 
		- messing up pictures tho 
	- had the LLM walk me through a set up of a simscale simulation 
	- spent some time looking through public VAWT simscale simulations to see what kind of results they focused on 
	- had the LLM quiz me on the concepts of CDF in general, what its good at vs not, what information you get out of a simulation, and what is reliable or not. 
	- got plan from mike 
		- got live share working 
		- working on coping an airfoil i found on the one from hri 
- trouble shooting airfoil (4hr)
	- review the results of the simulations 
	- question LLM about ai in simscale 
		- doesn't seem to know much about that 
- total 9.5 hr 
### Thursday 7/16
- ran other simulation on the NACA0018 airfoil (1 hr) 
	- asking LLM for help with settings 
- Met with Mike + Anna - 9am (.5 hr)
	- talk about todays plan, how yesterday went, and discussed contacting Ryan for support on how to add in online forums 
- stay on call with anna (4 hrs)
	- gave llm the link to he simscale forum and asked it to read through 
		- said it read through the parts that it thought would be best 
	- added another source on airfoil validation 
	- switched to trying to validate NACA0012 instead of 0018 (so that i could use the smooth airfoil i found online (anna is still working on NACA0018)
	- two more simulation runs changing AOA and lift directions 
	- many iterations biggest aid was modeling a 2d plane - idea from a simscale validated study of naca 0012 
	- this brough drag to 0.05 and lift to 0.6 (from 0.6 and 0.19) huge improvement
- played with mesh setting to see any further improvements none found (1 hr)
	- call with anna to talk about next steps (2hr)
		- y+ issues?
		- try reducing first boundary layer 
		- success with drag when making it 2d but then lift is even lower at 0.48. 
- total 8.5 
weekly total: 38.5
1.5 extra hours needed 
### Friday 7/17
day off
## Week 5

### Monday 7/20
- Met with Mike + Anna - 9am (0.5 hr) 
- discussed annas progress + next moves 
	- try a new airfoil 
	- try a new Reynolds number 
	- look in forum 
	- try COMSOL as last option 
		- get vpn 
- stay on call with anna (3 hrs)
	- anna runs new airfoil
	- i run with new Reynolds number of 500,000 
		- not much change - lift was too low 
		- LLM calculated the wrong velocity so settings were messed up - re did myself and re ran which didn't change much 
	- tried to download COMSOL 
	- got vpn 
	- anna tested out fusions ai tools - said they were just ass good as zoo keeper but faster 
		- played around with fusions ai and it seems to be a bit faster 
	- download fusion 
- try to validate the vj20 hybrid in simscale with anna (3 hrs)
	- anna got the cad done in fusion to use for the simulation 
	- i ready through vj20 to see what settings they used 
		- while reading through the paper I saw that the LLM had been reporting the cut in speed wrong. it had miss read the paper and used the reported cut in speed from another design and reported it as real 
		- i verified by finding another paper where they cited vj20 and reported the cut in speed at 1.5 not 2.9 
			- this kind of throws our design selection out of the window bc we just trusted the llm to read through and pull out the raw numbers and use them to rank the designs. Vj20 was loosing some rankings because of its "higher" cut in speed that wasn't even real. this is bad for the obvious reason but also means that the design we chose is even better?
	- anna having issues with fusions ai tool really slowing down 
- call with Mike and anna (0.5 hr)
### Tuesday 7/21
- Met with Mike + Anna - 9am
	- made a to do list for today and tomorrow
		- try magic prompts 
		- ask llm to make a visual decision matrix 
		- work on documentation 
		- make slides for Ryan 
		- work on simulation 
- stay on call with anna 
	- slack ryan 
	- individually work on documentation 
		- have llm read through daily log and make organized bullet list of what we did 
		- have llm pull out and reflections i wrote about the llm/wiki in a new doc 
		- have llm read through the cad 
	- try out the visual decision matrix 
		- prompt: I am really stuck with my cfd, I am trying to simulate the NACA 0018 airfoil and validate it using published data I found but I keep getting incorrect data, I have used the same settings to correctly validate the NACA 0010 and 0012 airfoils so I feel stuck. I have asked the LLM for tips on what to do with no success. what would you recommend i do now. (your recommendations can go beyond setting adjustments) please make a visual decision matrix for your result
		- wasn't super helpful, found a lot of the steps were quite vague and the final step was just to have a human check it 
- make slides for meeting with ryan 
- watch some you tube tutorials on how to set up a simulation for VAWT 
	- the one that anna and i set up failed and the reported forces were just zero 
		- might be an issue with the mesh 
- [[interesting convo with LLm abt vj20]]
- meeting with Ryan -4 pm
	- his advice:
		- make an evaluation  prompt 
		- be explicit in ranking 
		- you might need to use python 
		- is there something to add to agents file to reduce errors 
		- make skills in opencode (read abt this in the opencode website)
		- have the llm search the internet for you 
		- ask simscale people for help 
		- ask llm to continuously log all cdf for you 
### Wednesday 7/22
- Met with Anna - 9am
- added the internet access to agents page 
- email Phillip 
### Thursday 7/23
- Met with Mike + Anna - 9am
- Stay on with anna (3hr)
	- talk about what the meeting will look like with Phil 
		- had llm make a summary doc of our work to explain to phil 
	- trouble shoot some more sim scale 
	- respond to Phil 
	- email about what the report style will look like 
	- email Ryan about medium 
- simulations (1 hr)
	- re-ran the settings that worked for the naca 0012 on the naca 0018 but changed the boundary layers from 3 to 6 set the overall thickness to .2 and the first layer thickness to 0.001 - not successful/no change 
	- did some questioning with Gemini and it recommended changing the simulation type from steady state to transient so i tried that and got worse numbers for lift and drag
- writing for blog (0.5hr)
	- had llm go through daily log and make an outline of what we did to set up the wiki 
	- also had it make me reflection prompts 
- meeting with Phil about simscale (1 hr)
	- use filter tool to visually inspect the worst cells 
		- to fix the bad ones add local refinements (refinement layers) - you can set minimum levels 
			- careful of making the mesh size really big 
		- sometimes simplifying the geometry is the answer (probably not for the airfoil though)
		- increasing number of boundary layers or thickness 
		- ask ai "You can say, I want like a script to run in simscale or in simscale to, to check my mesh quality and it will probably give you like some nice commands or some. Or maybe a nice script that you could run on the mesh here to try to find these things"
		- maybe decrease overall mesh size from 5 to 4 but needs much more refinement at the airfoil 
		- change the iso range so that some of the small cells near the transition are highlighted 
		- could be a non-orthogonality problem 
		- you want the residuals for k and omega to be around 1e-15 
		- y+ <1 
- work on airfoil (1hr) 
- meet with mike to update (.25 hr)
- update daily log + take notes from meeting (1 hr) 
### Friday 7/24
- Met with Mike - 9am (0.5hr)
	- talked about day plan and what we talked about with phil 
- worked on mesh in simscale (5 hr)
	- all edits are logged in [[Airfoil Validation Studies]]
		- i was using a combination of gemmi to check how the airfoil was looking visually and the llm to recommend changes 
		- i also found someone else's airfoil mesh settings in simscale and told it to the ai and asked what parts i should borrow - minimal success 
		- mad around 20 editions of the mesh, getting a lot closer but i ran a simulation to see what the residuals were looking like and they were just as bad 
		- having some troubles with the mesh refinement boxes, i think some settings are clashing with each other 
		- overall the mesh is looking a lot better but is not all the way there 
			- i am thinking that this is one of the places ai is not as applicable because it can't see all the settings and output all at once which leads it to make suggestions that are already applied, could overrule current settings or repeat suggestions 
## Week 6

### Monday 7/27
- tried again to install COMSOL with the advice from email - it worked!! (0.5 hr)
- things is could do today 
	- start slides 
	- write for blog post 
	- continue fixing the mesh 
- work on mesh settings - continued to log (3.5 hr)
	- either my home wifi or the increased mesh size is causing this to go somewhat slowly 
- note: phil said in our meeting that the residuals for the simulation were way to high and we would want k and omega to be around 1e-15 (they were about 1e-5) but i have looked into this and can't find any source that says that would be achievable, and most have been saying that 1e-7 is very good 
- switched to work on some writing for the blog post (1 hr)
- back to airfoil - am finding that the llm is getting hard to work with because it doesn't have the ability to look at the mesh visually so it recommends running a simulation after every change - and it need that feedback to evaluate the change, however Phill told us explicitly not to waste time doing this and to just change the mesh and look at its improvement (1.5 hr)
		- shorter 

### Tuesday 7/28
- meeting with Mike and Anna (0.5 hr)
- started the slide show for later (0.25 hr)
- chatted with Gemini about the airfoil (.5 hrs)
- read through some simscale documentation on what boundary layers should look like (1 hr)
- experimented with using ray - simscale ai chatbot- to trouble shoot and check over settings (2 hrs)
	- you do have to tell it how everything is setup but once you tell it can give suggestions 
	- links documentations pages and gives supporting images on where settings are and how things should be looking which is helpful 
- called with anna  (2.5 hrs)
	- wrote the slides for team meeting at four 
	- discussed our timeline for the next few days (want to finish airfoil val by eod Wednesday and finish VAWT set up by Tuesday)
	- continue fixing the mesh 
		- should email Phill a picture and ask what the issues are bc we have tried everything 
	- i think that the problem might be the reference data we are using, maybe we should shift to using wind tunnel data instead of xfoil 
- call with team (1 hr)

### Wednesday 7/29
- no call with mike today 
-  work on simulations (1 hr)
	- compare mesh with anna 
	- try different re numbers 
	- look into viscosity differences 
	- read through a naca 0012 simscale airfoil val and note differences 
- write email to phil/ gather info to send to him (0.75 hr)
- work on writing the blog (1 hr)
	- anna is working on decision making process and i am working on setting up the wiki 
- Phil emailed back working on mesh (2hr)
	- fixing growth rate?
	- can you have two inflate boundary layer settings? 
	- 10 layers first size of 0.001 overall size of 2.5 and growth rate of 1.5
- emailed phil back with more changes 
- work more on blog writing 
### Thursday 7/30

### Friday 7/31

## Week 7

### Monday 8/3

### Tuesday 8/4

### Wednesday 8/5

### Thursday 8/6

### Friday 8/7

## Week 8

### Monday 8/10

### Tuesday 8/11

### Wednesday 8/12

### Thursday 8/13

### Friday 8/14
