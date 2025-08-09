# Events and Debugging Assessment

Time to assess how well you have learned to use the debugging tools in Chrome Dev Tools, and writing click event listeners. This application is to show kids with illnesses and the memories the would like to make. Celebrities sign up to help kids make memories.

> 🧨 Make sure you answer the vocabulary and understanding questions at the end of this document before notifying your coaches that you are done with the project

## Event Listeners to Create

1. When the kid name is clicked, it should display their wish.
1. When the celebrity name is clicked, it should display their sport.
1. The pairings list should should contain the pairing in the following format.
   ```html
   {child name} will be making memories with {celebrity name}, a {celebrity
   sport} star, by {child wish}
   ```

Below is an animation showing how the application should look when complete and how the event listeners should work.

<img src="./images/debugging-events-assessment.gif" width="700px">

## Setup

Your instruction team will provide a link for you to create your assessment repository. Once your repo is created, clone it to your machine.
S
Make sure your Developer Tools are open at all times while working on this project. Use the messages provided in the Console to determine what code needs to be fixed or implemented, and use breakpoints in the Sources tab to step through your code as you debug.

## Vocabulary and Understanding

Before you click the "Complete Assessment" button on the Learning Platform, add your answers below each question and make a commit.

1. When a child is clicked on in the browser, which module contains the code that will execute on that event happening? Can you explain the algorithm of that logic?
   > The Kids.js module handles the click. Each child is rendered as an <li> with data attributes (data-id,data-type, data-name, data-wish). A document.addEventListener("click", …) checks if the clicked item’s data-type is "child". If so, it gets the data from itemClicked.dataset and shows it in a window.alert.
2. In the **Pairings** module, why must the `findCelebrityMatch()` function be invoked inside the `for..of` loop that iterates the kids array?
   > findCelebrityMatch(kid, celebrities) must run for each kid so it can find the match whose celebrityId belongs to that specific child. That’s why the call must be inside the loop over the kids array. If it were called outside, it would only run once and not produce correct matches for all kids. The function also uses return celebrity as soon as a match is found, so it needs to be called again for every kid.
3. In the **CelebrityList** module, can you describe how the name of the sport that the celebrity plays can be displayed in the window alert text?
   > We add the sport as a data attribute to each <li> in the CelebrityList module, for example <li data-sport="${star.sport}"> Then, in the click event we get this value with itemClicked.dataset.sport Finally, we show it in the alert like this window.alert(`${itemClicked.dataset.name} is a ${itemClicked.dataset.sport} star`)
4. Can you describe, in detail, the algorithm that is in the `main` module?
   >

What main does, step by step:

Import the UI builders: Kids, Celebrities, pairings.

Select the root element: #container.

Build one big HTML string that includes headers/sections and calls the modules (${Kids()}, ${Celebrities()} …).

Render it by setting mainContainer.innerHTML = applicationHTML.

That’s it. It’s the entry point that lays out the page and injects the lists; the actual behavior (click handlers) lives in the other modules.
