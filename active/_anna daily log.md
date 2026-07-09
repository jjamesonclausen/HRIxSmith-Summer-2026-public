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
		- *hard to get diverse results out of it without drastically *
	- reorganized repo folders to be more navigable
		- added daily logs and notes to the repo
		- added folders to store CFD and CAD documentation
`15:30` met w/ Mike + Julie, discussed progress, work plans, and design goal issues (0.5 hr)
`16:00` worked with Julie, looking at logan logistics and other potential locations/data (0.5 hr)

### Thursday 07/09

`09:00` met w/ Mike + Julie to get started (0.5 hrs)



Hours: 0
**Next tasks:**
	- logan airport logistics and/or blue hill data? or third option?
		- height/distance rules surrounding runways
	- finalize project plan using llm generated options
	- start creating list of concepts to narrow down for vawt
	-
	- Dive into egr side of the project, looking towards next milestone of a report
		- Continue adding sources AND LEARNING
		- As we learn, think about WHAT data we need and HOW we want to see it
	- Improve wiki's utility for the egr side of the project
		- Qualitative assessments? - we might want to define each category
	- Constrain design space! What application are we designing for? Where will these be most useful? How can that help us narrow down metadata?
		- Boston, wind speeds

