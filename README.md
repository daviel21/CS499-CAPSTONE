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




## **Category One Enhancement: Software Design and Engineering**
For my Category One enhancement, I chose to improve the mobile application I originally developed in CS-360 Mobile Architecture and Programming at the beginning of 2025. The reason I selected this artifact is because it was one of the first hands-on mobile development projects I built from the ground up, and I knew it had real potential for improvement.
The enhancement I planned was to implement a Favorites feature. Originally, the app allowed users to create and view events in a grid layout, but it didn’t give them a way to mark certain events as important or preferred. Adding the ability to "favorite" an event and view a filtered list of only those favorite events felt like a practical and valuable upgrade that could also help me showcase skills in database integration, UI interaction, and activity navigation.
To start, I modified the Event model to include a boolean isFavorite property and updated the event layout to display a star icon. I made sure users could toggle this icon to mark or unmark an event as a favorite. Then, I worked on storing that favorite state in the SQLite database. This required updating the schema to include a new is_favorite column and creating helper methods like setFavorite() and getFavoriteEventsList() in my AccountDatabaseHelper class.
One of the biggest challenges I ran into was that my original event data was hardcoded in the app and wasn’t actually being written to the database. That meant even though the favorites logic was in place, nothing would show up on the favorites screen because the database was essentially empty. To fix this, I refactored the code to load events directly from the database and insert new ones as the user added them.


## **Category Two Enhancement:**
The artifact I enhanced is a dashboard I originally built for CS-340, Advanced Programming Concepts. It’s a web app created using Python with Dash and JupyterDash, and it connects to a MongoDB database to pull and display animal shelter data. The original version let users filter rescue animals by category, view them in a table, it was supposed to also show the location of each rescue animal, but the code was broken that ended up being caused by missing or invalid coordinate data. I added safeguards and checks in the update_map function to handle edge cases where data might be missing or misaligned, and that stopped the callback crashes.
One of the new features I added displays live benchmark results comparing Python’s built-in sort function to my custom quicksort. I used the timeit module to calculate the time it takes to sort the same dataset with both methods and show the difference directly on the dashboard. Another big addition was the priority display using heapq. I created a callback that builds a heap from the dataset and displays the youngest animals below the main data table. I also enhanced it by adding a custom quicksort function to sort data manually and a priority queue system that uses a min-heap to surface the top 5 highest-priority animals from age, youngest.
The process of enhancing the artifact taught me a lot. I had to troubleshoot a few things, and I couldn’t see my benchmark or priority queue results in the dashboard. That was because I accidentally left the new layout elements outside of the app’s layout container. Once I fixed that, the new sections showed up like they were supposed to. What I learned most from this enhancement was how important defensive coding is when working with live data, and how to bridge custom logic into a reactive web framework like Dash. It’s one thing to write a quicksort in a script but integrating it into a running dashboard and making it visually meaningful is a different story.


## **Category Three Enhancement:**
Enhancing..
