# ProPublica News Apps Desk Coding Manifesto

_by Jeff Larson and Scott Klein, ProPublica_

There are many style guides for code. Most are silly. 

Some rules are more important than others and are worth following. For instance, we like this rule: Code has two audiences -- the compiler and your fellow developers. Recognize that your code will eventually need to be understood by other people. To the maximum extent possible and within the bounds of reason and your deadline, prefer code that's easy for other developers to understand over code that accomplishes the same task in a more obscure way. But if your app piles hacks on hacks on hacks, it's broken.

More important than establishing a shared style is establishing shared standards for security, compatibility and performance. Write code that is secure, tested and optimized. Here are some best practices to follow:

If possible, use Varnish. Everything served by the Varnish cache is much faster than any code you can write. You will save a lot of time by not refactoring code that's only going to be seen by one user before Varnish caches it anyway. Use thie time to apply a special level of scrutiny to routes that cannot be cached. 

That being said, all of your HTTP requests should take less than a second to complete. Total page size, including all assets, shouldn't top 1.5 megabytes, and even that's higher than it should be.

Follow all security best practices. Apply patches without procrastinating.

Don't write code that guesses at future functionality. 

Avoid gilding the lily. You're on deadline. You're not writing code for the ages.

Early and often, check important platforms other than the one you develop on. Assume that your users don't have beautiful Apple monitors. Use a Cheap Dell Monitor (CDM) as a second screen and check everything you make on it.

Some platforms require special attention:

If an app doesn't work IE 8 and up, it is broken.

If an app crashes a mobile device or doesn't work because it relies on hovers for basic functionality, it is broken.

If an app isn't responsive or adaptive to multiple screen sizes, it might be broken. Sometimes tiny screens are too small.

All objects in your code should have a single responsibility and encapsulate internal state. Imagine every [object as a tiny machine](http://worrydream.com/EarlyHistoryOfSmalltalk/) that is responsible for one idea, and only communicates with other objects via simple interfaces. 

Objects with a simple forward-facing API allow software to be soft.

In JavaScript, prefer events that other objects can subscribe to over direct method calls, when possible.

Work on feature branches and merge to master as features are completed and deployable.

Every app should have a README in the root level that explains how to bootstrap the app. Those instructions should be directed at an experienced developer who knows your deployment system but might not know anything about the app. It should include how to bootstrap data and install the app's dependencies in development and in production, as well as any special post-deploy instructions. When creating this README, imagine your reader as an exhausted, freaked-out sysadmin recovering from a system meltdown. Don't make her think. When possible, make a setup script that expresses dev bootstrap instructions as comments in a shell script that [will actually do the bootstrapping](http://robots.thoughtbot.com/post/41439635905/bin-setup). Or just [use make](http://bost.ocks.org/mike/make/).

[Don't repeat yourself.](https://github.com/propublica/guides/coding-manifesto.md)

Do not join any code churches and don't subscribe to doctrines that make your decisions for you. Too many tests are a code smell. Test the parts of your code that should be tested, but your deadlines are more important than getting a good grade on test coverage.

