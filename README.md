# travel_agent
An agent that searches for transportation and lodging accomodations for complex travel situations, balancing the needs of clients and travelers while optimizing savings.

I supervise travel logistics for my father, a traveling musician, along with his band members, crew, and management. My responsibilities entail researching and booking transportation.

Unlike artists signed to major record labels, my father doesn't embark on months-long tours with organized logistics, with trucks and buses to take the band and equipment to the next show. His schedule is sporadic - he may travel to a show the day before, then go home the day after.

Some aspects of the work are cumbersome for a human to do alone. For one thing, the logistics are complicated because travelers are coming in from different places. An eight-man crew (six musicians, manager, sound engineer) could originate from as many as six different states.

Furthermore, many gigs take place in cities with either no airport or an extremely small one with flights beyond our budget. This necessitates flying into a larger city and driving. To keep costs down, we try to find flights that will allow pairs of travelers to arrive around the same time and share a car. These costs must be weighed against the costs of the cars themselves.

In the midst of all this, we also seek to maintain a level of comfort for travelers to keep them in performance shape. Some have preferences for specific airlines, and in some cases status that will allow them to save on bags.
not forcing them to travel extremely early if not necessary. Finally, we must also weight the risks of connecting flights, sometimes opting to take a nonstop flight even if it is more expensive.

My workflow usually looks something like this:
- Manually search for flights
- Send them to my manager for his approval
- Take his feedback and
- Once approved, send to the traveler for their approval

It sounds simple on paper, but becomes complicated in practice.

A new detail may come to light, such as that one traveler will need to return home early for another engagement, or that they will be arriving from someplace other than their home. Due to the interlocking nature of our logistics, changing one detail could mean having to change all others.

As planning progresses, information gets scattered across several email threads, making it difficult to keep track.  

My goal is to build an agent that will handle the hard work.

The agent will be given access to a list of upcoming events, including location, date, time, and all travelers who will need to get there. It will have .MD files on each traveler, listing their location, preferred airports, comfort level with driving, and more.

Before the search begins, it will ask the user important questions regarding logistics. (Will have to add these later)

It will search for flights within the parameters we have set (such as if we want to avoid certain airlines, avoid lower class fares, etc).

If a drive will be required from the airport, it will furthermore seek flights that will allow travelers to arrive at similar times. It will also research rental cars, considering factors such as how many cars will be needed, the cost of a minivan as opposed to two smaller cars, etc.

Once a potential itinerary has been suggested, it will engage with the user as a chatbot would. It will take user input, such as if a detail has change, and adjust the search accordingly. Understanding that these travel situations are almost never perfect, it will explain the advantages and drawbacks (whether financial, logistical or otherwise) of the scenario it has found, with proposed alternatives.

Once management has approved the selection of flights, I would like the agent to automatically email each traveler with their suggested flight, and automatically track the traveler's response. An advanced version, ideally, could use NLP to detect tone, distinguishing between ambivalence, grudging acceptance, and outright denial of the proposed arrangement. (These are musicians we're talking about, after all.)

Selecting band members will not be part of the agent's responsibilities; that decision will lie with management. Nor will I initially give the agent the ability to actually book the flights.
