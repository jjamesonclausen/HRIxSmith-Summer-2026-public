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

- Continue to review past report + go though some references - 8:00
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

**Notes:**

- Ai issues can be external problems - look at website that shows whats going on
- Look at the window/context size this can slow model down - it lets it look at more info at once
  - Part of the skill is being specific to the model knows what to do
- Look into data view in obsidian - this will take some learning about VAWT to know what you want to structure it as
  - Once we know more we can ask for better structure/organization of the wiki pages and better tags
- New idea: add in 'personas' - create people who have specific views - such as cost vs effect vs longevity and have the llm answer questions from these perspectives (also can re make the wiki pages from this perspective)
  - This is helpful because the llm is generating the most broad or general answer for the most general audience so this will have it create more unique answers.
- Images - we are not having it make figure captions but seems like this might be more complicated than its worth - do go check that images are being used well in the concept pages
  - Consider the organization of these images - can we have the llm generate tags for them - which tags would be use full

**Personal thoughts**

- We should add into the agents page more about this specific project - think if we include that it wont just be used for learning about VAWT and that we will be using it to design and organize ideas it will generate more useful wiki pages - for example one for each type of design
- I need to look into metadata/tags for obsidian and we should think carefully about what tags would be most helpful

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
  - Picked out location + find data on the air port
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

### Friday 7/10

## Week 4

### Monday 7/13

### Tuesday 7/14

### Wednesday 7/15

### Thursday 7/16

### Friday 7/17

## Week 5

### Monday 7/20

### Tuesday 7/21

### Wednesday 7/22

### Thursday 7/23

### Friday 7/24

## Week 6

### Monday 7/27

### Tuesday 7/28

### Wednesday 7/29

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
