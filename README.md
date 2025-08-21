# CS499-CAPSTONE

Hello, my name is Daviel Machet and I’m currently pursuing a Bachelor’s degree in Computer Science with a concentration in Software Engineering at Southern New Hampshire University. I’ve been in the Computer Science program for about four years. Since I’m active-duty military, I’ve typically taken two classes per term to balance my responsibilities. It hasn’t always been easy managing both school and service, especially during field ops and temporary assignments, but I’ve stayed consistent and committed. This journey has taught me a lot about time management, perseverance, and the value of education

While in the program I learned that this field is all about solving problems, figuring out what’s needed, breaking things down, and making sure whatever you build is functional and efficient from start to finish.

Some of the main skills I aim to show are problem solving, writing efficient and clean code, and being able to work with both front end and back-end development. I want to demonstrate that I can take a project from the planning phase all the way to deployment, using what I’ve learned about version control, testing, debugging, and integrating different technologies. My goal is to show that I can think through a problem, figure out the best way to build it, and get it done in a structured and reliable way.

These skills go hand in hand with what I want to do in my career. I’m aiming for a role where I can work on real-world applications and contribute to software development teams, especially in full stack roles. Knowing how to structure code properly, write scalable applications, and work with databases and APIs is key for that.This directly supports my focus in software engineering. I want to specialize in building reliable, user-focused applications. By improving my understanding of full stack development and the development cycle, I’m preparing myself to step into a role where I can confidently take on software projects from start to finish, whether that’s in a team setting or on my own.

This ePortfolio showcases some of the projects and assignments I’ve completed throughout the program.

## [**Code review for my Artifacts**](https://go.screenpal.com/watch/cTi2qNnlHUP)
For each category, I broke down which project I was going to use, what files I would go over, and what enhancements I planned to make. I started with bullet points and turned them into full scripts that I can follow during the recording. That way, if I forget something, I can quickly glance at my notes and keep going.

-For Category One, I talked about my mobile app from CS 360 and explained each file and how they all work together.

-For Category Two, I focused on the algorithms side and explained how I’ll be adding a custom quicksort and priority queue to my CS 340 dashboard.

-For Category Three, I planned out how I’m going to improve my database structure, add advanced queries, and refactor the data layer using a repository class.




## [**Category One Enhancement: Software Design and Engineering](https://github.com/daviel21/CS499-CAPSTONE/blob/main/Milestone%20Two%20Enhancement%20One%20Software%20Design%20and%20Engineering%20Narrative.docx)**
For my Category One enhancement, I chose to improve the mobile application I originally developed in CS-360 Mobile Architecture and Programming at the beginning of 2025. The reason I selected this artifact is because it was one of the first hands-on mobile development projects I built from the ground up, and I knew it had real potential for improvement.
The enhancement I planned was to implement a Favorites feature. Originally, the app allowed users to create and view events in a grid layout, but it didn’t give them a way to mark certain events as important or preferred. Adding the ability to "favorite" an event and view a filtered list of only those favorite events felt like a practical and valuable upgrade that could also help me showcase skills in database integration, UI interaction, and activity navigation.
To start, I modified the Event model to include a boolean isFavorite property and updated the event layout to display a star icon. I made sure users could toggle this icon to mark or unmark an event as a favorite. Then, I worked on storing that favorite state in the SQLite database. This required updating the schema to include a new is_favorite column and creating helper methods like setFavorite() and getFavoriteEventsList() in my AccountDatabaseHelper class.
One of the biggest challenges I ran into was that my original event data was hardcoded in the app and wasn’t actually being written to the database. That meant even though the favorites logic was in place, nothing would show up on the favorites screen because the database was essentially empty. To fix this, I refactored the code to load events directly from the database and insert new ones as the user added them.

&#8594; History of changes made:

*Added the ability for users to mark events as “favorites” using a heart icon in the event_item.xml layout
*Created a new screen (FavoriteEventsActivity) to display user-specific favorite events
*Added a favorite column to the SQLite events table and updated the database schema
*Implemented toggling logic for favorites using an ImageButton and SQL update queries
*Updated the database schema to support storing a username per event
*All queries (retrieval, insert, delete) now respect the current logged-in user context
*Users can now see only their own events and their own favorites
*Added a DatabaseRepository class to centralize all database logic
*Shifted from tightly coupled SQL calls in activities to method-based access via the repository pattern
*Made the app more maintainable and scalable through separation of concerns


## [**Category Two Enhancement:](https://github.com/daviel21/CS499-CAPSTONE/blob/main/Project%202%20Dashboard%20CS460%20Enhancement.zip)**
The artifact I enhanced is a dashboard I originally built for CS-340, Advanced Programming Concepts. It’s a web app created using Python with Dash and JupyterDash, and it connects to a MongoDB database to pull and display animal shelter data. The original version let users filter rescue animals by category, view them in a table, it was supposed to also show the location of each rescue animal, but the code was broken that ended up being caused by missing or invalid coordinate data. I added safeguards and checks in the update_map function to handle edge cases where data might be missing or misaligned, and that stopped the callback crashes.
One of the new features I added displays live benchmark results comparing Python’s built-in sort function to my custom quicksort. I used the timeit module to calculate the time it takes to sort the same dataset with both methods and show the difference directly on the dashboard. Another big addition was the priority display using heapq. I created a callback that builds a heap from the dataset and displays the youngest animals below the main data table. I also enhanced it by adding a custom quicksort function to sort data manually and a priority queue system that uses a min-heap to surface the top 5 highest-priority animals from age, youngest.
The process of enhancing the artifact taught me a lot. I had to troubleshoot a few things, and I couldn’t see my benchmark or priority queue results in the dashboard. That was because I accidentally left the new layout elements outside of the app’s layout container. Once I fixed that, the new sections showed up like they were supposed to. What I learned most from this enhancement was how important defensive coding is when working with live data, and how to bridge custom logic into a reactive web framework like Dash. It’s one thing to write a quicksort in a script but integrating it into a running dashboard and making it visually meaningful is a different story.

&#8594; History of changes made:

*Replaced default sorting logic with a manually coded quicksort algorithm in Python
*Used quicksort to sort animal records by attributes such as intake date or urgency
*Built a priority queue using Python’s heapq module
*Prioritized animals based on factors such as age, health, and time in shelter
*Enabled shelter staff to retrieve and process high-priority animals first
*Used the timeit module to compare the performance of the custom quicksort against Python’s built-in sorted() function
*Collected benchmark data and displayed results in the dashboard for transparency.

## [**Category Three Enhancement:**](https://github.com/daviel21/CS499-CAPSTONE/blob/main/Milestone%20Four%20Enhancement%20Three%20Databases%20Narrative.docx)
For my Category Three enhancement, I focused on improving the database structure and overall functionality of my Android mobile application originally developed in CS-360. The goal was to move beyond simple data storage and retrieval and build a more robust, normalized database schema. I redesigned the SQLite database to support three related tables: Users, Events, and Categories. This allowed me to implement advanced SQL queries using joins, aggregate functions, and filters to extract meaningful insights from user data. For example, the app can now display statistics such as the most used event category or total number of events created in a given month. These insights are shown in a dedicated "Insights" screen within the app.I created a new DatabaseRepository class that centralizes all SQL operations, improving maintainability and separation of concerns in the code. One challenge I faced during this enhancement was ensuring the proper linkage between categories and events using foreign keys and correctly updating the UI to reflect those relationships. I also implemented query functions to retrieve events by category, keyword, or date. Throughout this process, my top priority has been ensuring the code is functional, and with time, I’ll continue to refine the user interface to improve the experience. This enhancement allowed me to demonstrate a solid understanding of relational databases, normalized schemas, SQL query design, and how to integrate that into a mobile application workflow. It reflects my growth in working with complex data structures and backend logic in mobile development, and it aligns directly with my concentration in software engineering.

&#8594; History of changes made:

*Redesigned the database schema with three normalized tables
Users: stores user credentials.
Categories: holds all possible event categories.
Events: linked to users and categories via foreign keys.

*Enforced data integrity through foreign key constraints
*Most used event category per user using GROUP BY and COUNT
*Total number of events this month using strftime('%m')
*Created a dedicated InsightsActivity screen that visualizes these stats
*Moved all database logic out of UI components and into DatabaseRepository.java
*Abstracted queries like getMostUsedCategory(String username) and getMonthlyEventCount(String username) for reuse
*Improved consistency and debugging across the app
*Added spinner/dropdown in the event creation screen to select categories dynamically loaded from the Categories table
*Insights screen pulls real-time data using SQL queries from the repository.

&#8594; Professional Self-Assessment:

Looking back at my journey through the Computer Science program, I’ve learned a lot, not just about programming or databases, but about myself too. When I started, I had a general interest in tech, but now I’m walking away with real skills, confidence, and a clearer idea of what I want to do professionally. This capstone helped me pull everything together. It gave me the chance to apply what I’ve learned over the years and put it all in one place where I could show what I’m actually capable of.
One thing I’ve focused on from the beginning of this course is making sure my code works. Functionality has always been a priority for me. Sometimes that meant not having the fanciest-looking interface, but I knew the logic behind the app was solid, and that's what I wanted to make sure I demonstrated. I do plan to take more time down the line to improve the look and feel for users, but for now I wanted to make sure the core features were working as intended.
Throughout the capstone, I enhanced one main project to show my growth across three different areas, software design and engineering, data structures and algorithms, and databases. Each enhancement brought its own challenges, but I learned a lot each time. Whether I was implementing a favorites feature, improving how I sort and manage data, or redesigning my database to follow a more normalized structure, I could see how far I’ve come since I started this degree. There were definitely moments where I hit roadblocks, especially trying to get things like sorting or advanced filtering fully working, but each time I figured it out or got closer, it built up my confidence.
Overall, this ePortfolio is my way of showing everything I’ve built and learned. It highlights the skills I’ve developed in programming, database design, algorithmic thinking, and secure coding.

