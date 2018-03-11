# Display Content with Views

Views are a query builder that makes list of your content. Like a list of blog posts for example. You pass criteria to the Views list build, something like "show blog posts" or "show blog posts about cars" and the information is filtered by Views and a list is created.

The first thing defined when building a View is the Base Table which is the base pool of data from which we want to start building our list \(examples: node, user, comment.

Then we choose what the Display of the View is. It could be a page, a block that can be used wherever on the site, or something else. We can also set criteria on when who/where can see this View. For example you can show it only to a user who is logged in. You can have  multiple Display for each view. Finally you can choose how to output your list in HTML.

