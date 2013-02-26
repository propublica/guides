# ProPublica News Apps Desk Coding Manifesto

_by Jeff Larson and Scott Klein, ProPublica_

There are many style guides for code, most are silly. Some are better than others, and some rules are more important than others. We don't adhere to any typographic rules for their own sake. Our rule is simply this: Code has two audiences -- the compiler and your fellow developers. Recognize that your code will eventually need to be understood by other developers. To the maximum extent possible and within the bounds of reason and your deadline, prefer code that's easy for other developers to understand over code that accomplishes the same task in a more concise but obscure way.

More important than a typographic style for code is coding standards for security, compatibility and performance. We write code that is secure, tested and optimized. Here are some best practices we follow:

Everything we write is served by a Varnish cache that is much faster than almost any code we could write. We apply a special level of scrutiny to apps that cannot take advantage of Varnish. Best security practices must be followed.

We don't write code that guesses at future functionality. We avoid gilding the lily and rely more on caching than on sub-second refactoring. That being said, all of our HTTP requests should take less than a second to complete, and we strive for requests completing in 50-100ms. Total page size, including all assets, shouldn't top 1.5 megabytes, and even that's higher than it should be.

Early and often, we check important platforms other than the one we develop on. Some platforms require special attention:

If an app doesn't work IE 8 and up, it is broken.

If an app crashes a mobile device or doesn't work because it relies on hovers for basic functionality, it is broken.

If an app isn't responsive or adaptive to multiple screen sizes, it might be broken. Sometimes tiny screens are too small.

All objects in our code should have a single responsibility and encapsulate internal state. Imagine every [object as a tiny machine](http://worrydream.com/EarlyHistoryOfSmalltalk/) that is responsible for one idea, and only communicates with other objects via simple interfaces. Objects with a simple forward facing api allow software to be soft.

In JavaScript, we prefer events that other objects can subscribe to over direct method calls when possible.

We work on feature branches and merge to master as features are completed and deployable.

Every app must have a README in the root level that explains how to bootstrap the app. Those instructions should be directed at an experienced developer who knows our deployment system but who might not know anything about the app, and must include how to bootstrap data and dependencies in development and production, any special post-deploy instructions, etc. When creating this, imagine your reader as a weary, freaked-out sysadmin recovering from a system meltdown. When possible, make a setup script that expresses dev bootstrap instructions as comments in a shell script that [will actually do the bootstrapping](http://robots.thoughtbot.com/post/41439635905/bin-setup). You can also [use make](http://bost.ocks.org/mike/make/).

We [don't repeat ourselves.](https://github.com/propublica/nerdblog/blob/master/style-guide-wip/news-apps.md)

Too many tests are a code smell. We aren't affiliated with the churches of BDD, TDD, Kanban or any other doctrine. We test the parts of our code that should be tested, but our deadlines are more important to us than test coverage for its own sake.

