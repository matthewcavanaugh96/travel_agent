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
- Take his feedback and make adjustments
- Once approved, send to the traveler for their approval

It sounds simple on paper, but becomes complicated in practice. Often new details come to light - a traveler may be arriving from some place other than their home, or may have to leave early for another engagement. Due to the interlocking nature of our logistics, changing one detail could mean having to change everything else. As planning progresses, information gets scattered across several email threads, making it difficult to keep track. Human error can also occur, such as searching the wrong dates or typing the wrong price in an email asking for approval.  

My goal is to build an agent that will handle the hard work.

The agent will be given access to a list of upcoming events, including location, date, time, and all travelers who will need to get there. It will have .MD files on each traveler, listing their location, preferred airports, comfort level with driving, and more.

Before the search begins, it will ask the user important questions regarding logistics, including: 
- What is the arrangement for ground transporatation? Is it provided by the client, is the client providing reimbursement for rideshare, or will we be responsible?
- Is the client paying for the hotel? Will they book it themselves?

It will search for flights within the parameters we have set (such as if we want to avoid certain airlines, avoid lower class fares, etc). It will consider airline and airport preference, weighing airline status which may confer free checked bags. It will look at the seat map and weigh the

If a drive will be required from the airport, it will furthermore seek flights that will allow travelers to arrive at similar times. Eventually, it will also research rental cars, considering factors such as how many cars will be needed, the cost of a minivan as opposed to two smaller cars, etc, but this will likely be added only after the flight function is polished.

Sometimes, we will have travelers drive directly to a show if they live within a reasonable distance. 

Once a potential itinerary has been suggested, it will engage with the user as a chatbot would. It will take user input, such as if a detail has changed, and adjust the search accordingly. Understanding that these travel situations are almost never perfect, it will explain the advantages and drawbacks (whether financial, logistical or otherwise) of the scenario it has found, with proposed alternatives.

Once management has approved the selection of flights, I would like the agent to automatically email each traveler with their suggested flight, and automatically track the traveler's response. An advanced version, ideally, could use NLP to detect tone, distinguishing between ambivalence, grudging acceptance, and outright denial of the proposed arrangement. (These are musicians we're talking about, after all.) Management will sometimes override a traveler's veto for financial or logistical reasons, and the agent must be prepared to handle this as well.

For the major airlines (mainly Delta, American, United, Southwest), prices are easily tracked through tools such as Google Flights, so that is likely where the agent will search. Some airlines, such as Frontier and Allegiant, obscure their prices behind complex add-ons and packages. We try to avoid these airlines, but sometimes they are the most convenient option. In this case, the agent should be able to navigate the websites to find the true cost. 

I have previously set up a rudimentary agent which was capable of directly interacting with a web browser, including navigating drop-down menus, selecting seats, and entering traveler information, so I have proof-of-concept that this is possible. If this proves impractical for multiple travelers, I could look at using APIs. However, this doesn't necessarily need to be done in minutes - I could give the order overnight, and have results in the morning.

Due to the interconnected nature of logistics, each agent will likely be assigned not to an individual traveler, but to a specific segment of the trip. Flights probably first. Once those are assigned, it will then consider when pairs or groups of travelers are arriving, and find a car. It may also have access to status with rental agencies that could provide discounts. 

The orchestrator would have to manage results from each individual agents and be prepared to send updated instructions to another agent. For instance, three travelers and all their bags they will not fit into a single sedan. If a single minivan will prove vastly cheaper than two sedans, the Car agent could notify the orchestrator, which would then ask the Flight agent to look at moving one traveler's flight to match up with the other two. If this will increase the cost of flights, or raise some other logistical problem, the orchestrator will keep track and ask the user.

Selecting band members will not be part of the agent's responsibilities; that decision will lie with management. Nor will I initially give the agent the ability to actually book the flights. Booking itself takes me very little time once the flights have been selected.
