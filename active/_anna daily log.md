## Week 01

### Monday 06/22

`09:00` met w/ Mike + Julie to get started
	**Notes:**
	- First ~two weeks will be w/ Ryan, thinking about appropriate AI usage
	- Duane and Rajeev will be back after that
	- Prob 2-3 meetings/wk w/ honda
		- Most likely tues/fri afternoons, but expect changes
	- Slack communication will be set up
	- OpenAgent AI tool? And will get access to internal Honda AI tool
	- Should document daily activities and when/how AI is used
`09:30` reviewed fluids notes and assembled photos and list of topics for Julie
`11:30` read and took notes on previous project report (3 hrs)
`16:30` check in w/ M + J
`16:40` continued reading prev report, researching VAWTs, reviewing fluids (2 hrs)

### Tuesday 06/23

`09:00` met w/ Mike + Julie, [agile project management strategy](https://www.apm.org.uk/resources/find-a-resource/agile-project-management/)
`09:15` continued reading report appendices, researching VAWTs, reviewing fluids (6.5 hrs)
`16:00` met w/ Ryan, Mike + Julie (1.25 hrs)
	**Notes:**
		- Duane > rajeev > ryan
		- Ryan: philosophy -> software engineer/data scientist, was a prof now working w students thru 99P
		- **we are externs at HRI/99P (for resume/linkedin purposes)**
		- Follow them on linkedin and request connections
		- Should slack/email for any questions and they'll answer asap, they're very open to jumping on a quick call to help problem solve something
		- Look at urbanwind vawt page on 99P labs website
		- *Initial AI use feelings: Anna: 2-3, Julie: 3-4*
			*- Rn I avoid using AI for the most part. I want to preserve (and improve) my ability to write text so I try not to use it even for editing things, and similarly with research, I want to be good at sifting through sources and identifying trustworthy ones and understanding them, not just reading AI summaries. However, I do use it to debug code and sometimes to vibe code if I'm working in a language I don't know very well. But I make sure I either think of the logic or am working through it with the AI and I still understand what we are doing.*
		- Integrating AI isn't necessarily straightforward
			- Information architecture problem
		- AI tool we are going to use: OpenCode (open source version of Claude Code)
			- Download this and start playing around with the free model
			- Need to tie it to open AI api key
			- Obsidian - open source free note taking app
			- Consensus.app - academic search AI (3 searches free / day)
			- Download intro to applied AI repo and start building LLM wiki
			- How do we search for sources (literature) and start incorporating them into the wiki?
			- Experiment and work with LLM wiki on our own
		- Want to use AI to realize the dream of open source material and to help identify our own knowledge gaps to assist our learning and critical thinking processes
			- Build an LLM for a project and put in our info, experimentation, notes, etc, and outside research/info
			- **if it doesn't work that's OK** we are literally just trying to see what we can do with it
		- Moving towards using workflows and agents instead of prompts/chats
		- How can we address the four main problems that people encounter with AI?
			- Fluency != correctness
			- Automation bias
			- Anchoring
			- Sycophancy

### Wednesday 06/24

`09:00` met w/ Mike + Julie to get started
`09:30` setting up opencode (2 hrs)
	- Download opencode, obsidian, and slack
	- Get opencode working in vscode terminal
	- Slack ryan
`11:30` LLM wiki exploration (2.5 hrs)
	- Clone intro to applied AI repo and start building LLM wiki
		- Learn - what is an LLM wiki / how can it be used
		- Read through repo
		- Read extra resources
		- Work through the workshop steps in the repo
`15:00` met w/ Mike + Julie to review progress and discuss next steps
`20:00` continued working through repo and building LLM wiki (2 hrs) 

*So far the LLM wiki seems like it could be a very useful tool, but I'm still slightly skeptical. With the rules laid out in AGENTS.md it does behave better than LLMs usually do, in that it always cites its sources, is using sources you trust, and explicitly labels unverified statements. On one hand, I don't want it to replace my information synthesis by doing the work of summarizing and pulling concepts and storing information, but I think if you engage with it and ask it to help you learn the content it becomes useful. I had it quiz me on a paper and its questions forced me to think more about the content than I would have if I had just skimmed it once and moved on, so it can kind of be a good accountability tool. And the instructions to be a harsh grader and avoid sycophancy seemed to work. It is a lot of work to find sources and evaluate the wiki though so it's an interesting trade off... I think once you have a more established wiki that you trust and has good information it will pay off the upfront cost of building it up.*

### Thursday 06/25

`09:00` worked on eval loop for LLM wiki
`10:00` met w/ Mike + Julie
`10:15` worked on merging LLM wiki's w/ Julie and figuring out how to collaborate (3.25 hrs)
	- Used VS Code Live Share to collaborate on my wiki
	- Added all sources to my wiki and had the LLM ingest them, included previous design clinic report
	- Edited agent rules to tighten procedure surrounding new sources and organization of the wiki
	- Did some testing and added rules about how it should answer questions
	- Created blank repo and pushed the current (decent) version to it
		- Added julie and ryan as collaborators
		- Used gemini to troubleshoot github issues. It worked. Thank you AI
`14:00` youtube refresher on github collaboration
`14:30` met w/ Julie again to walk through github collaboration
`15:30` check in mtg w/ Mike + Julie, stayed on w/ Julie to work out git collab issues

### Friday 06/26

`09:00` met w/ Mike + Julie to get started
	- Added sources to the wiki
	- Spent a lot of time reading them and engaging with the LLM to learn
	- Worked w/ Julie to improve source intake procedure, esp regarding figures
		- Added procedure for converting pdf to markdown
		- Included rules for extracting figures and linking them in the source as well as wiki pages like the summary and concepts
	- Built out eval question set and iteratively tested LLM wiki
`15:00` check in w/ Mike + Julie
	- Troubleshooting images, continued adding sources

## Week 02

### Monday 06/29

`09:00` met w/ Mike + Julie to get started
	- Added three sources - took FOREVER bc it wouldn't always do all of the steps it is supposed to do (esp images)
	- Troubleshooting images
		- Learned about pdf image embedding
		- Rewrote agents section with help from the LLM to make it more specific
		- Its being so inconsistent and taking soooo long to answer (and for us to troubleshoot)
	- Learning obsidian
		- Added tags to all wiki pages and sources and added groups in the graph
		- Watched tutorial video on all major tools
		- Markdown shortcuts/formatting
		- Organization: folders, tags, bookmarks, properties
		- (data)bases
		- canvas
		- Started learning DataviewJS using opencode
		- Start all wiki pages with properties table including tags, source(s), and related content
		- Might not be worth the effort to learn and set up
	- Learning from wiki
		- Reading through wiki concepts/methods and implementing various learning methods with the LLM
		- having issues getting it to run due to timeout error so went back to obsidian

### Tuesday 06/30

`09:00` met w/ Mike + Julie to get started
`09:15` stayed on and worked on LLM wiki w/ Julie (3.25 hrs)
	- Created `schema/` folder to house separate procedural documents for LLM tasks
	- Simplified `AGENTS.md` to contain only overall guidelines/rules/structure
	- Edited `schema/` documents for clarity and precision
	- Downloaded python and pymupdf library to assist pdf image extraction
		- Updated `schema/Convert PDF to MD.md` to begin w/ python steps
	- Tested changes by converting and ingesting va7
		- converted pdf to md properly but didn't use markdown formatting for headers (which would improve readability) in the source file, and equations are not readable
		- Added line in procedure to add equations as screenshots not text
		- Images worked well!
		- All wiki pages look good
		- Timed out while verifying files/links and logging actions... not sure why
		- Was using GPT 5.5 bc 5.4 mini was timing out like crazy even on small tasks, need to debug this
`13:00` cont wiki work + meeting prep
	- Updated daily log, thought through progress so far, next steps, and questions
	- Made project update for mtg w/ ryan later (2 slides max)
	- Wrote procedure for wiki maintenance
	- Worked w/ LLM to learn (and to test the wiki)
`16:00` met w/ Ryan, Mike, + Julie
`16:45` wrote up meeting notes and thought through new ideas, next steps, goals (0.15 hr)
	**Notes:**
		- LLM troubleshooting
			- See openAI status - it fluctuates, maybe the cause of some of our issues
			- Also compare models and look at window size! Can use any model that isn't pro
		- LLM consistency
			- They are stochastic so getting deterministic behavior is difficult
			- Can be a model issue, a prompt issue, or
		- Obsidian utility
			- Dataview is worth it - Ryan
			- As we learn content and think about egr we need to think about *WHAT we need to see from our data and HOW we want to see it*
			- Better wiki organization: include pages for different vawt designs and design parameters (to be able to compare in ideation stages)
			- Better metadata: work to get LLM to add useful data like Cp or efficiency to the top of those pages (and verify that it is doing so accurately)
		- General
			- Can add layers to get the LLM to generate more diverse ideas (instead of the typical mathematically average output)
			- Eg. 'personas' to include a layer of a generated opinion from a certain POV about a topic or design
			- Images are a struggle, always (open problem)
			- Consider assessing how well the LLM understands the content of the images and how well it uses that to place them in wiki docs (BUT if its putting in decently relevant things its prob fine)
			- We may need a better way to locate figures that are useful (like should they each have a markdown containing their caption and a link to the image that can be viewed in obsidian? And some useful metadata to find them?)
			- Keep in mind the balance between a large wiki w/ lots of information and your ability to use and find that information

### Wednesday 07/01

(tuesday pm)
`17:00` wrote up meeting notes and thought through new ideas, next steps, goals (0.5 hr)
`17:30` did some learning about various topics related to our next tasks (1.25 hr)
	- read + took notes on evals q&a from ryan's repo
	- Preliminary look at zookeeper https://zoo.dev/research/zookeeper
		- https://zoo.dev/research/zoo-cad-engine-overview 
	
(wednesday)
`09:00` met w/ Mike + Julie, discussed yesterday's mtg and next steps (0.5 hr) (thursday)
`07:45` - (1.25 hrs)
	- Repaired sources that were converted incorrectly - takes a long time
	- While waiting, read the papers

### Thursday 07/02

`09:00` met w/ Mike + Julie to get started (0.5 hr)
`09:30` worked w/ Julie towards goal of making wiki useful for design (3 hrs)
	- Finished repairing previous sources
	- Fixed backlinks that were not functional and corrected instructions
	- Added `wiki/designs/` and `wiki/parameters/` (and corresponding tags)
		- Moved concepts pages to new folders where appropriate
		- Added instructions in `schema/Ingest Source.md` for when and how to write and format them
		- Tested instructions on va9 and va3 with good results
`13:00` learned about vawts and played around with obsidian to inform wiki set up (2.5 hrs)
	- Reading (and/or learning w wiki) all of the sources I added (incomplete)
	- Dataview tutorial and practice
`15:30` met w/ Mike + Julie, discussed progress and work strategies/systems (0.75 hr)
`16:15` log entry about AI use progress/thoughts (0.25 hr) 

*So far I am feeling like the wiki has soo much potential. And alongside that, I am feeling the distance between the current wiki and where it could/should be in the near future. Using AI like this is totally new to me and so far has impressed me with how much it can do, and how it can (theoretically) be integrated into workflows where the human is still leading the charge and thinking critically and learning. That being said, we have this shiny, sparkly goal of what this wiki might be able to do for us in terms of our design work, and yet I still feel like I am double checking every task it does and don't quite trust it to behave reliably. It is definitely a challenge to get deterministic results from a stochastic process. At the current moment the LLM is capable of processing PDFs to Markdowns and extracting images and writing helpful wiki pages on concepts, methods, designs, and parameters, but it doesn't do any of that ALL of the time. Julie and I have spent manyyy hours correcting mistakes it has made, largely with formatting which feels like a menial task that should be easy to pass off to AI. I'm concerned about that because moving forward, A) we need it to speed up the process of ingesting papers, not add extra work, and B) formatting errors can directly affect the reliability of the information we gather from the wiki though Obsidian bases and other search-based data visualizations. I would like to feel confident handing over control of the wiki to the LLM so that I have more time to spend on design work instead of sifting through research papers or worse, double checking wiki formatting. But, to be fair, I am a bit of a control freak and am probably going to have a harder time hitting that marker than most people would.*

### Friday 07/03

(make up from Wednesday)
`09:30` lots of retroactive updates and fixes, then added more sources (5 hrs)
	- Fixed va5, va6 sources (were summarized)
	- Ingested va8, va9, va10
	- On wiki pages, labeled all images with their figure captions
		- Updated instructions
	- Separated prev design pages into one page per design
	- Fixed naming of existing design pages
	- Fixed naming of existing parameter pages
	- Double checked all links - NO `" "`
	- Fixed troposkein page which had the wrong style properties table
	- Created design and parameter pages for ALL sources
	- Added 7 sources, skimmed them during wait time

## Week 03

### Monday 07/06

`09:00` met w/ Mike + Julie to get started
`09:15` worked with Julie (2.25 hrs)
	- Discussed potential design space, looked into wind data at Boston locations
		- MIT or Logan airport seem to be decent options w/ wind data available
		- Speeds 1-8 m/s average
	- Updated `schema/Ingest Source` to include more specific instructions about metadata
		- All data should be reported as a number
		- For data that changes depending on wind speed, we asked for the max value in two buckets: 1-4 m/s and 4-8 m/s (based on boston wind data)
		- Asked for more detail in parameters and design pages
`11:30` more sources ( 4.5 hrs)
	- Converted and ingested 11 sources, double checked design/parameter pages
		- Images are still sometimes an issue, as is formatting of converted sources, but prob not worth spending time on
		- I keep noticing that the wikilinks in the properties table are showing up with quotation marks and aren't functional, but I looked at the source code and it seems like the LLM is actually putting them in correctly so I have no idea why they aren't working or how to fix it
		- Should we expand our wind speed ranges? Like maybe 1-4 and 4-10? To account for higher wind possibilities? I can't decide if this would help to include more designs or hurt by making low wind designs look bad.
		- *For va23, there were 'uncorrected' cp values and 'corrected' ones and it seems like the correction resulted in two designs switching places but, since we asked for max cp, the llm reported the higher, uncorrected values which contradict the paper's final conclusion...
		- Its having a hard time with cp sometimes bc it is often reported in graphs (figures) which it can't understand.
		- We could add a qualitative assessment about cp, like 'none/small/large improvement' to help capture studies whose results the llm doesn't see
		- In studies where one design parameter is changed I think I would like it to select the most successful variant and make that the focus of the design page, and fill out the properties for that design. It can discuss the other two on the page but it needs to recognize ONE design variant. - Particularly for the papers that it made a vaXX Reference design page, where the reference is the control turbine*
	- Worked on learning some of the content by reading papers and wiki pages during convert/ingest time
`16:30` check in w Mike + Julie, discuss timeline, today's issues, tomorrow's tasks ( .5 hrs)

### Tuesday 07/07

`08:30` reading about zoo dev, downloaded desktop version
`09:00` met w/ Mike + Julie to get started, wrote meeting slides w/ Julie (.75 hr)
`09:45` learn zoo design (5.75 hrs)
	- Read through a lot of their website to learn about all the parts of zoo design studio and zookeeper, see zoo.dev tab in All Notes
	- Download and set up
	- Practiced making simple shapes/models using normal UI, getting familiar with KCL, and using zookeeper
`15:30` meet w/ Julie to discuss zoo + update slides, also added 8-12 m/s bucket (.5 hrs)
`16:00` weekly meeting w/ HRI (1 hr)
	**Notes:**
		- Create design goal and work plan
			- Use opencode to generate several work plans from different angles, given constraints, resources, and our goal
		- Try converting sources to .json files to improve llm handling of quantitative data?
		- Regardless of how the metadata turns out, use the llm more to access information
			- Create a new folder in the repo where it can make design related documents like work plans, comparison charts, zookeeper prompts, etc
		- Rajeev is away for the next two meetings, duane will miss the second one
		- Consider showing examples, screenshots or just pull up the wiki/obsidian/zoo/etc

### Wednesday 07/08

`09:00` met w/ Mike + Julie to get started (0.5 hrs)
`09:30` worked with Julie to define design goal (3 hrs)
	- Looked at more wind data around the greater Boston area, selected Logan airport as the best location
	- motivation for the project at this location (massport net zero goal)
	- Looked into airport regulations to see if it is possible to install small vawts near runways or on the airport roof
	- Working with llm wiki to analyze some of the wind data and determine if vawts will be effective here
		- *Helpful use of the llm and wiki!*
`13:00` (2.5 hrs)
	- continued looking into logan airport logistics and wind data
	- prompted llm to generate potential work plans for the remainder of the project
		- generated several different timelines and a day by day breakdown
		- compared with Julie and discussed best ideas
		- *hard to get diverse results out of it without drastically changing prompt*
	- reorganized repo folders to be more navigable
		- added daily logs and notes to the repo
		- added folders to store CFD and CAD documentation
`15:30` met w/ Mike + Julie, discussed progress, work plans, and design goal issues (0.5 hr)
`16:00` worked with Julie, looking at logan logistics and other potential locations/data (0.5 hr)

### Thursday 07/09

`09:00` met w/ Mike + Julie to get started (0.5 hrs)
`09:30` worked w/ Julie to finalize [[Design goal]] and [[_project timeline]] (2 hrs)
	- made 8-12 m/s bins for metadata
	- cleaned up file tagging, some naming, and folder organization
`11:30` utilized wiki to compile list of [[Concept ranking worksheet | potential design concepts]] and considered criteria (2 hrs)
`14:30` met w/ Julie to compare notes, discuss final design concept list and criteria (1 hr)
`15:30` check in w/ Mike + Julie, discussed design ranking and llm use (0.5 hr)
`16:00` worked w/ Julie to rank designs according to criteria (1.5 hrs)
	- independently ranked each design, then *had llm rank them*
		- compared rankings, decided on criteria weights, *had llm compute scores*
		- *used llm to compile and rank list of other designs of the winning category (h-vawts)*,
		- *made an obsidian base list of all parameters pages that apply to h-vawts*

### Friday 07/10

`09:00` met w/ Mike + Julie to get started, discussed llm use (0.75 hrs)
	*Using the LLM for the design selection greatly sped up the process \[of design selection] but potentially at the cost of a deeper understanding of the designs on our end. It feels as if some of the slow, inefficient tasks which we are handing off to the LLM are actually where we, the humans, would otherwise be learning. The LLM wiki is a very interesting and useful resource since it is essentially an expert in the field that can instantly retrieve lots of information across the many sources we gave it, however, since we are relying on the wiki to manage this knowledge, we feel like we don't have a very deep understanding of any of it. We have only briefly skimmed the many sources in the wiki so the decisions we are making with the LLM's help feel almost a little arbitrary and we are questioning if we have enough knowledge to be asking the right questions and making the right decisions about the LLM's output. Additionally, there are still sometimes questions about the LLM's 'understanding' of the information, or lack thereof, causes it to make choices that we wouldn't make, or give answers that sound very good, and technically aren't a lie, but aren't quite right either. Using it to rank designs has been interesting since we generally trust it a lot to pull out quantitative data accurately, but sometimes it would use general background info to infer a statistic it couldn't find and if Julie and I hadn't realized that, its ranking would have appeared to be more reliable than it was.* 
`09:45` worked w/ Julie to further analyze rankings, discussed top options (1.25 hrs)
	- different weights based on personas: results-oriented expert, process-oriented beginner
	- looking into the top couple designs, verifying the rankings the llm gave (not 100% right)
	- concluded that the top two designs are pretty  much on equal footing and that we should play around with both in Zoo and read up on both and potential parameters to change
`11:00` CAD experimentation + design research (4 hrs)
	- experimented with zookeeper and prompts from llm wiki, focusing on vj20 design
		- *shorter prompts work better than too much information which often results in glaring very-ai-style errors like blades that aren't connected to anything*
			- llm referred to the short prompt as "short \[and] production-ready"
		- *it does a good job and makes a large fairly complicated design with good accuracy incredibly quickly compared to doing it manually, but then when you try to make changes it makes random errors (like missing or floating pieces) that it has a hard time fixing, and since I didn't make the original drawing, I don't know exactly how to fix it myself*
		- zoo often has trouble loading or connecting to the server which is annoying
			- every time it makes a change the view is like hella zoomed in and often takes several minutes before i can zoom out or click any buttons
		- tried to change `rotorAzimuth` and it rotated but the inner part got messed up and then it froze zoo. the next time it worked better.
		- began debugging an issue manually, read through all kcl files to understand structure and used opencode to help troubleshoot
			- *this was helpful AND i felt like I was doing something so that was nice. After reading through the code I have a general understanding of how the rotor is constructed and how to make changes, however it is still fairly complicated and I'm not familiar enough with CAD in general to always know where to look for bugs. opencode was helpful with that and I'm making progress to fix this one issue.*
	
`16:00` met w/ Julie to discuss CAD progress (2.25 hr)
	- talked about modeling progress and the merits of both designs, seems like va9 is less well defined and therefore harder to model accurately. We are leaning towards using the vj20 design as a base and exploring the effects of using the EN0005 airfoil and/or the blade end or twist features of the va9 rotor
	- read [[vj20]] and [[va9]] for better understanding of the top two designs
		- also read thru the H-vawt-related parameters pages

## Week 04

### Monday 07/13

`09:00` met w/ Mike + Julie to get started (0.5 hr)
`09:30` learning about CFD and SimScale (3 hr)
	- walked through basic flow simulation tutorial on yt using a grabcad glider
		- learned basic elements you need to set up a flow study and how to look at the results
	- read thru CFD section and appendix of [HRI2526] and noted specific things they learned and how they set up their studies
	- had Luna look through all of the sources and wiki pages and write up some notes on how to approach CFD for vawt design as a beginner
`13:00` attempted SimScale study on airfoil for validation (2.5 hrs)
`15:30` met w/ Mike + Julie, discussed simscale / cfd in general (0.75 hr)
`16:15` cont working on airfoil study w Julie (2 hrs)
	- went through HRI2526 airfoil validation procedure, tried to replicate their study
		- used llm wiki to help understand their procedure and troubleshoot our cfd results
			- mesh refinement: inflate boundary layer, growth rate 1.15
			- mesh set up: hex automatic, medium fineness
		-  did an approx 2D study
	*Simscale egr AI might actually be so helpful bc help, llm wiki was kinda helpful but not really, it just told us things we knew for the most part.*

### Tuesday 07/14

`09:00` met w/ Mike + Julie to get started (0.5 hr)
`09:30` created meeting slides w/ Julie (3 hrs)
`13:00` researched CFD (3 hrs)
	- researched history and basics of CFD (briefly) for better context and background knowledge
	- finished reading and taking notes on all CFD information in [[HRI2526]]
`16:00` Smith x HRI mtg (1 hr)
`17:00` go through meeting notes and update documentation (0.5 hrs)

### Wednesday 07/15

`09:00` met w/ Mike + Julie to get started (0.5 hr)
`09:30` building out wiki for CFD help, learning with it (4 hrs)
	- added almost all simscale documentation, got it to write a few wiki pages, *now it knows everything about how to use the simscale software!*
		- this was super fast with obsidian web clipper
	- had it teach me about all of the elements that go into a cfd simulation (took foreverrrr theres a lot)
	- ran another attempt at a naca0018 validation study
`14:00` more learning, research, messing around with settings in simscale, trying to troubleshoot airfoil study (3 hr)
*Giving the LLM all of the SimScale documentation was initially very helpful for general CFD and SimScale learning, but ultimately not enough information to get valuable troubleshooting advice. Need to add more CFD sources like SimScale forum, write ups of other CFD studies, etc.*

### Thursday 07/16

`09:00` met w/ Mike + Julie to get started (0.5 hr)
`09:30` troubleshooting airfoil studies, see CFD log (3 hrs)
`13:00` more troubleshooting airfoil studies, see CFD log (4.25 hrs)
	- re-drew airfoil in fusion, no change
	- tried 0012, no change
	- increased comp domain, no change
	- approximated 2D by shortening comp dom in z direction, big lift improvement
		- learned about tip vortices
	- learned about y+, started tracking it, changed first layer thickness to get y+ = 1, no change
	- increased fineness to 8, drag got slightly better, lift slightly worse
*Sometimes it seems like generic AI like gemini gives more helpful troubleshooting advice... probably because it is pulling from the entire internet and is therefore able to find info that is more relevant to the specific issue. But, obviously, it isn't very trustworthy, which is where our LLM wiki is far superior... but it really needs more sources.*
### Friday 07/17

`09:00` met w/ Mike to get started (0.5 hr)
`09:30` airfoil troubleshooting (7.2 hrs)
	- looking into the following, see [[Airfoil Validation Studies]] for all study details
		- ~~air temperature / conditions?~~ Re normalizes for v, U, A already
		- turbulence model, and intensity?
			- when/where does airfoil transition from laminar to turbulent flow
	- added more sources about airfoil fluid dynamics and cfd
		- *helped get better advice w more specific low Re airfoil info, plus some 0018 studies*
	- had the LLM select relevant threads from the SimScale forum and ingest them
		- *didn't really give me anything particularly enlightening but I think that was just bc of the content of the forum threads not the LLM*
	- tried [magic prompt](https://www.verbalized-sampling.com/) to get more diverse results... *it thought and generated some info but never actually responded...should try again*
*In general the LLM advice was very repetitive and it wasn't super awesome at keeping track of what changes I had made during each sim run which was a little annoying. With better sources it did have some useful insights and generally made the process feel more informed since I don't know that much about CFD or simscale.*
	- conclusion today was that I seem to have landed on a pretty good simulation set up? and my CAD airfoils are good (*yay for LLM being able to analyze .step files!*) but still need to confirm bc the 0018 failure is strange
## Week 05
### Monday 07/20

`09:00` met w/ Mike + Julie to get started (0.5 hr)
`09:30` airfoil troubleshooting (3 hrs)
	- tested 0010 and 0016 with the same settings
		- mesh non orthogonality was above recommended range but solutions converged, though prob less accurate?
		- 0010 had correct Cd and Cl 7% high
		- 0015 had Cl 0.58 (1/7 too low) and Cd 0.029 pretty good
	- Julie ran 0018 w Re = 50,000 and got good Cd, Cl too low (~0.3 instead of ~0.5)
	- Tested Fusion AI agent, used same prompt as zookeeper and got very good vj20 model in 4 min! *less than 1/3 of the time it took zookeeper and an equally good if not better model*
		- *had it make an airfoil and by the time I had typed in detailed instructions and it thought and made it I could have finished it. also it was facing the opposite direction than what I wanted even after two requests that specifically stated the direction.* 
`13:00` (4.75 hrs)
	- continued experimenting with Fusion AI, it was having errors that prevented it from running for a while but then seemed to get better again
	- got full scale and 1/11.01 scale vj20 models done
	- `15:30` met with Mike + Julie to check in
	- tried to set up vj20 cfd validation study
		- harder than anticpated, ended up researching and llming to figure out what to do. Have an LLM-written plan that I started implementing. Will finish in the morning. 
	- tried to download COMSOL, could not
*LLM misreported the cut-in speed of a turbine... this kind of erodes some of our trust in it and its ability to pull quantitative information. It seems like if you ask for a specific piece of information it will find some piece of information that generally fits the request but it may not be what you actually wanted. If, on the other hand, you ask for a response that includes a consideration of many possible answers and/or reasoning to support its answer, it will discuss multiple possible responses and examine their merits a bit which then allows you to use your judgement and get what you want out of it.*
### Tuesday 07/21

`09:00` met w/ Mike + Julie to get started (0.5 hr)
`09:30` documentation and AI experimentation (2 hrs)
	- generated summary of first four weeks and narrative-style report outline
		- included progress made and AI utility notes from each week
	- summarized CFD airfoil validation studies so far
	- test magic prompt
	- make visual decision analysis matrix
`11:30` work through vj20 vawt validation study set up with julie (1 hr)
	- used LLM tutorial from yesterday, had it make some changes to fix various errors
	- also just looked some stuff up ourselves which was refreshing tbh
	- generated mesh to check y+ and non orthogonality
`13:30`  mesh troubleshooting, meeting prep (2.5 hrs)
	- analyzed mesh (max non orthog  = 70!), started run 1
	- run 1 failed, took 3 min and did not capture forces and moments, same with 2
		- changed some mesh settings based on LLM guidance to fix, regenerated
		- run 3 didn't complete, idk why switched to mtg mode
	- made slides with julie, thinking about AI successes/failures from the week
		- *used LLM to look through daily logs for the week and come up with a list of what went well and what didn't and what questions we could ask, pretty helpful (at least a good starting point)*
`16:00` met w/ Ryan + Julie (0.5 hrs)
	- should add functionality to search the internet if the wiki doesn't have the answer (AND SAY VERY CLEARLY WHAT CAME FROM THE INTERNET)
	- can add agent skills for repeated tasks
		- might be useful for having the llm validate its own work (like quantitative reporting)

---
### Wednesday 07/22

`09:00` met w/ Julie, implemented internet search functionality for the llm wiki, responded to emails, slacked mike (1 hr)

### Thursday 07/23

`09:00` met w/ Mike + Julie
`09:30` tried more LLM assisted SimScale troubleshooting (3 hrs)
`13:00` started getting organized for and writing outline of concept selection process (1 hr)
`14:00` mtg w/ Philip for CFD help
	Notes:
		- high aspect ratio - very squished/flat, high surface area to volume ratio, or angle size (check how simscale actually quantifies it)
		- when checking mesh quality look at the ends of a bell curve, a few bad cells can crash the simulation
		- interface between boundary cells and free stream nice mesh cells
			- often near sharp corners or areas where geometry isn't well defined
		- add refinement layers = add another subdivision
			- forces more of the mesh to be nice and structured and less in the messy boundary conforming region
			- increases computational cost very quickly
		- can also simplify geometry (remove weird edges where mesher is struggling)
		- residuals should be def under e-10, ideally at e-15
`15:00` played around with mesh settings w Julie trying to match what it visually looks like to something like this ![[Pasted image 20260723154144.png]]
	- it seems like increasing the number of boundary layers and their overall relative thickness is good
	- regional refinement around entire airfoil is also good
	- global mesh fineness can be 3-4 if you do a good job around the airfoil


### Friday 07/24 - day off

## Week 06
### Monday 07/27 - day off
### Tuesday 07/28

`09:30` met w/ Mike + Julie to get started (0.5 hrs)
\---
`12:30` (3.5 hrs)
	- prepared meeting slides with Julie 
	- used LLM to catch up on the mesh changes Julie made
	- set up a new mesh to figure out the settings myself
	- worked through some of list of LLM prompts to try
		- asked for cut in speed estimation method
		- DOE / what variables to investigate
`16:00` met w/ Duane and Ryan for weekly update (1 hr)
\---
`20:30` continued troubleshooting mesh until one generated (1.5 hrs)

### Wednesday 07/29

`07:30` updated daily log and cfd documentation (0.5 hrs)
`08:00` continued working on my mesh and julie's - veryy slow (wifi?) (1 hr)
`09:00` met w/ Mike + Julie (0.5 hr)
`09:30` mesh work (1.5 hrs)
	- inspecting mesh, good non othogonality and aspect ratio, visually good
	- ran a simulation, good y+ and good mesh but bad results
		- had to extend the run several times to get residuals down
	- slacked julie about emailing phil and next steps
`11:00` worked on writing blog draft (concept selection and cad) (2 hrs)



Hours: -13.50

**Mtg notes 7/14:**
	- LLM prompt improvements
		- ask for visual decision analysis matrix to justify decisions
		- ~~magic prompt for diversity~~
	- consider asking LLM to break down tasks between two people and the LLM
	- ~~ask LLM about doable ways to estimate cut in speed~~ *see wiki/methods*
	- ~~ask LLM to ask about potential DOE and/or use similar ranking process for parameters to decide what variables to investigate~~ *see active/analysis*
	- consider using similar ranking scheme again to reevaluate how the design is doing for the design criteria
	- ~~use llm to help summarize and document all of our iterations of CAD and CFD~~ 
**Misc:**
	- add shorter time interval data to investigate wind direction fluctuations 
	- next tuesday 07/28 everyone will be back, but note that rajeev will have missed two weeks by then!
	- stop airfoil val work by EOD wednesday

MIKE SCHEDULE
wendesday, maybe morning but not rest of day 
thursday, no
friday - wednesday, available