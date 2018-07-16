# Homework Week 3

```
Topics discussed this week:
• Closures
• Scope
• Callbacks
```

>[Here](https://github.com/HackYourFuture/JavaScript3/tree/master/Week1) you find the readings you have to complete before the first JavaScript3 lecture.

## Step 1: Space game: recreating what we saw in class

_Deadline Tuesday_

At the end of this lesson, we fired lasers from the spaceship. Working from the code you have, adapt it so your code supports firing lasers as well. 

**Hint:** if you get stuck, all the steps are online. Look in the [space game project](https://github.com/HackYourFutureBelgium/JavaScript2/tree/master/Projects/space-game) for all the code (we've done step 3 and 4 together in class).

## Step 2: Read

* Closures, from JavaScript is Sexy: [Understand JavaScript Closures with Ease](http://javascriptissexy.com/understand-javascript-closures-with-ease/)
* [Understand JavaScript "this" with ease](http://javascriptissexy.com/understand-javascripts-this-with-clarity-and-master-it/)

If you're still unclear on closures, you can read this VERY popular [StackOverflow article](http://stackoverflow.com/questions/111102/how-do-javascript-closures-work) (The fact that it's popular shows that a *lot* of people are struggling with it :smile:)

## Step 3: Todo App: Filters

_Deadline Saturday_

Make the _All / Active / Completed_ filters work.

You can work from your own code, or this [week 3 branch](https://github.com/HackYourFutureBelgium/todo-app/tree/week3) of the official todo app.

**3.1** Examine the [working version](http://todomvc.com/examples/vanillajs/) (this is just to see the functionality, the code is quite different). Create some items, check off some items, and check that they appear in the correct list. Note that checking / unchecking an item will move it from active to completed and vice versa.

**3.2** Add three event listeners for our three buttons. You can use `bind` to connect the three buttons to the _same_ `onChangeFilter` button, but you can also just make three filters.

**3.3** In your `onChangeFilter` function, you need to change a global variable (I call mine `FILTER`) that knows what to filter on, and then call the `update` function.

**3.4** The second function of the `onChangeFilter` function is to set the `selected` class on the selected filter (and remove it from the unselected filters!). 

**3.3** In `update`, we should no longer work with the full list of items (`for item in TODOS`) but instead we should _filter_ the list first, conditionally (an `if` condition is easiest), and create a `filteredItems` variable that contains either _all items_, only the _active items_ or the _completed items_. Use the `filter` function for that (specifically, use it three times, one in each branch of the `if` condition).

Getting this right is tricky! I myself struggled the most with finding an elegant way to turn the buttons on or off (the `selected` class). Don't feel bad if your code has a lot of repetition at first!

## Step 4: (Optional) Todo app: editing items

Being able to edit items is quite important; otherwise if we make a mistake, we have to remove that item and re-add it again. Editing items happens by *double-clicking* the item.

**4.1** Again, examine the [working version](http://todomvc.com/examples/vanillajs/) Create some items, double-click an item, change the text and press enter (or click somewhere on the page) to confirm.

**4.2** I keep a global variable at the top of my script called `EDITING_ID`. I set it to `null` initially, indicating I'm not editing any item.

**4.3** I add a double-click listener to the list item. Note that the name of the event is called [`dblclick`](https://developer.mozilla.org/en-US/docs/Web/Events/dblclick). We bind this to a new method, which you could call `onStartEditing`. Don't forget to `bind` it to the id!

**4.4** This function should just set the `EDITING_ID` and call `update`.

**4.5** Most of the work happens in `update`. First step is to add a class `editing` to the `li` tag. This is needed to hide the regular text element.

**4.6** When we're at the element that we're editing we create a text `input` field. Set its class to `edit` to get the correct CSS styling. Listen to the `change` event and call a `onEndEditing` function with the `id`. 

**4.7** We called `onEndEditing` with bind, but we still get the extra event argument as well! So our function signature should look like `onEndEditing(id, e)`. Use the event to get the value of the target element (the input field). Find the correct todo item, change its title attribute, and call `update` again.

## Step 5: Read before next lecture

_Deadline Sunday morning_

Go trough the reading material in the [README.md](https://github.com/HackYourFuture/JavaScript3/tree/master/Week1) to prepare for your next class


### How to hand in your homework:

You should have the repo for the todo list app already. Just commit your changes and push there: we will see them in our dashboard.

Before committing, go over your homework one last time:

- Does every file run without errors in the console?
- Have you used `const` and `let` and avoided `var`?
- Do the variable, function and argument names you created follow the [Naming Conventions](../../../../fundamentals/blob/master/fundamentals/naming_conventions.md)?
- Is your code well-formatted (see [Code Formatting](../../../../fundamentals/blob/master/fundamentals/naming_conventions.md))?
- Have you resolved all issues flagged by ESLint and the spell checker (no wavy red and green underlines in VSCode)?

If the answer is 'yes' you're ready to commit and push!
