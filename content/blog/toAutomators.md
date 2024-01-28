---
external: false
draft: false
title: "To; Automators : Just Take a coffee break, before you break your IDE "
description: "A to series for 3 AMIGO's"
date: 2024-01-05
---
Choosing which test cases to automate is essential for a successful testing approach in the field of automation testing. With an emphasis on optimizing Return on Investment (ROI), this post will go over important factors to take into account when prioritizing and selecting test cases for automation.

**Priority-based Selection:**

-   Prioritize test cases based on their importance and impact on the application. Classify test cases into categories such as P0 (Critical), P1 (High), P2 (Medium), and P3 (Low) based on their priority.
-   Begin automation with P0 and P1 test cases to ensure critical functionalities are covered thoroughly.
- _Example:_ 
	- Your e-commerce website crashes when customers try to make a purchase (P0). 
	- That's like your coffee machine deciding to go on strike just when you need that morning boost.
	-  Fix it first before tackling the less urgent issues like changing the color of the "Buy Now" button (P3).
	- In this e-commerce scenario, You will be better off automating user based scenario's like buying something instead of getting on niches like change of button colors 

**ROI-driven Automation:**

- Perform a comprehensive study to determine the test scenarios that will yield a high return on investment (ROI). Pay particular attention to automating high-impact test cases that enhance the application's overall stability and quality.
-   Prioritize the test cases that will yield real benefits in terms of reliability, efficiency, and time savings rather than automating every one of them.
- _Example:_ 
	- Returning to the example of e-commerce. Your ROI might be greatly enhanced by automating the checkout process. 
	- Every click you save when making a payment may be equivalent to a dollar saved; it would be like discovering cash hidden in the couch cushions each time a consumer makes a purchase. That is the ideal of automation!

**Value Addition:**

-   Ensure that each automated test case adds value to the testing process. Assess whether automation brings improvements in terms of repeatability, speed, and accuracy.
-   Consider automating repetitive and time-consuming test cases, leaving more room for manual testing of complex scenarios that require human intuition.
- _Example_:  
	- Again keep things like adding to cart in automation but things like User experience, in manual. 

**Strategic Test Case Selection:**

-   Strategically select test cases that cover a diverse range of functionalities, ensuring comprehensive test coverage. This approach helps in identifying and addressing potential issues across different aspects of the application.
-   Choose test cases that cover critical paths, error-prone areas, and frequently used features by end-users.
- _Example_ : 
	- Ideally should be automating always faulty things 
	- Let's say in a e-commerce application the color of the button changes (Very vague example ) always after every build. 
	- Now in this scenario automating this very case makes sense 

**Continuous Evaluation:**

-   Regularly review and update the test case selection for automation as the application evolves. New features, changes in requirements, or updates may impact the relevance of previously selected test cases.
-   Maintain a balance between automated and manual testing, adapting the test suite to reflect the current state of the application.
- Once you have automated all the above criteria, you should look 

## To automator's ;
> The ability to automate cases is not a skill; chatGPT can now perform this! 
Determining what needs to be automated is a talent. Because, in the end, we don't want artificial intelligence to take our position. One thing that will set you apart is your capacity for situation assessment. The capacity to choose, "OK fine this scenario is been tested out alot in our manual flow, might as well get an automation suite doing this." Or alternatively "These things break often cause of some random reason, let;s put this in our automation suite" These kinds of observations are only feasible if you are present in person. For example, when should the suite be run? You should put more of your attention on learning how to run (that is, in parallel).
Another thing to keep in mind is that an automation suite won't pay for itself. The time you would save on physical labor is where the return on investment is found. That being said, you might as well avoid some cases if you have a suite (not always true). Your ROI is in developing a testing strategy to go along with your automation. Additionally, developing these procedures is an iterative process; automation rarely yields significant returns on investment right away. It takes time to see benefits when automation is incorporated into testing strategies and procedures. Otherwise, you'll be in a chaotic situation with nothing more than a functional framework. An automated increment cycle appears when you display x cases. With no returns at all  

2 cents from your's truely,

_Bosco Correa_