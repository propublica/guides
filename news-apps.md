# ProPublica News Apps Manual of Style

News applications are large interactive databases. This style guide includes the typographic and technical best practices that we've built up over the years. Most of the rules here also apply to online graphics, a category that [shares a lot in common](#versus) with news applications.

This is not meant to be a design standards bible or a coding style guide, though you should probably have both of those. Also, overdependence on rules can hamper progress. News apps are a new and growing and dynamic field and rethinking the rules can be a good thing. Nothing in this document should be taken as a discouragement to be weird.

This is a living document. Please feel free to [propose changes](README.md).

## Accuracy

The most important thing by far is to be accurate and never to use data to mislead.

A full discussion on how to maintain accuracy is beyond the scope of this document, but two best practices we follow:

1. We pull random samples of records and spot check them against known-good sources.
2. We document our processes and publish our methodology.

For more see TK NICAR BEST PRACTICES?

## Browsers

We support the current and prior major release of Chrome, Firefox, Internet Explorer and Safari on a rolling basis. If earlier releases represent more than 2.5% of our audience, we'll continue to support them. This varies only slightly from [Google's Policy](http://googleappsupdates.blogspot.ca/2012/09/supporting-modern-browsers-internet.html).

If we use technology that has no cross-browser equivalent and is essential to an interactive technique, we provide gracefull fallback on other browsers.

We also support the built-in browsers in the latest revision of the iOS and Android SDKs.

All of our hover and click events must have analogous touch and swipe events on touchscreens.

When feasible, our apps use [Responsive Web Design](http://www.abookapart.com/products/responsive-web-design), with breaks for desktop, tablet, and handset. However, some apps require so much horizontal space that responsive design would be impractical. We take a "no heroics" stance in those cases: we make sure that handsets and tablets can see and use those apps in "overview mode."

## Bylines

Every news app should have a byline that follows ProPublica's style for stories. It should never be omitted.

The byline should be at the top of the first page of the app, under the headline. It should list the developers and reporters who made significant contributions to the app. At ProPublica we're very generous with bylines, though there should be sensible limits on the number of people listed.

## Charts

tk needs to be fleshed out and explained.

Avoid pie charts at all costs, with one exception: They can be used to show the relationship between a part and a whole. Never use a pie chart with more than two elements. Never use a pie chart where the perception of fine-grained differences is important.

Use a bar chart to show discontuous data or to compare relative values of different categories of data.

Use a stacked bar chart to show the relative values of categories and subcategories of data.

Use a fever-line chart to show continuous variables such as time series.

Use a scatterplot to show a correlation between

Avoid 3-D charts.

## Colors

Check colors for color blindness issues (we use Color Oracle)

Generally speaking, use Color Brewer colors when posssible.

Use a single hue and vary lightness when showing single-vector differences.

Use multiple hues when showing variations in kind.

Have a color palette and stick to it across apps as much as possible.

## Corrections

Our correction policy mirrors ProPublica's Corrections policy (link tk) with the following addition:

When data is incorrect, we place the correction language on every page that once showed the incorrect data point. That may mean that a correction will appear on thousands of pages. That's okay.

When an app's data is refreshed and the corrected data has itself been superceded, the correction language should be removed to avoid confusion.

## Dates

We follow AP style for dates and times, with one exception: Unlike AP style, we include the year in dates, even when the event described happened during the current year.

tk describe date and time ap style

## Headlines

The main page of every news app should have a headline.

## Interpolated Variables

It's good to write sentences that include interpolated variables, but the fact that you've done so isn't particularly interesting to the general public. Don't change typographic style to highlight interpolated variables.

## Maps

Avoid bubble maps, for two reasons: First, people cannot easily perceive differences in the relative size of circles, not least because the area of a circle grows exponentially in relation to its diameter. Secondly, bubble maps appear to show the geographic bounds of a phenomenon and not the intensity of that phenomenon at the geographic center of the circle. In other words, they always look like nuclear blast radius maps.

All maps must be distinguishable from population maps and should control for population or other denominator.

We use an Albers projection for a map of the entire U.S. and state-plane maps for individual states.

Slippy maps use the Mercator projection.

## Meta Tags

Every page in an app should have a unique title tag, a unique meta description tag and social tags specific to that page. Social tag style is here: TK

<a name="versus"></a>
## News Applications vs. Graphics

News applications and graphics share a lot of common characteristics. Both tell stories with data. Both are an amalgam of design, programming and journalism. So what's the difference? Here are two criteria. One is more technical and so less open to debate, but neither are perfect:

1. Graphics tend to tell a single story while news applications can tell many -- specifically, news applications let readers find the data that lets them see how they're personally affected.
2. Graphics tend to run in the browser while news applications tend to require  multiple trips to a backend or a runtime on a server.

## Numbers

Always assume that the primary function of numbers in a news application is to help readers understand scale and order of magnitude, and compare them against other numbers. Apply the following rules to numbers in tooltips, tables, labels, sentences, etc.

Except where special precision is required, use one significant digit after the decimal. Use typical rounding rules. Never use 'ceiling' or 'floor' functions for floats and be vigilant when a programming language does so by default.

Except where special precision is required, for any number over 1,000, truncate the number after the highest thousands place and append a word or abbreviation indicating order of magnitude word. Don't Abbreviate "thousand" because it's too difficult to discern thousand from trillion or the "th" cardinal number appendix.

    E.g.,
    10,302,321 -> 10.3 million or 10.3M
    5,242,000,014 -> 5.2 billion or 5.2B
    901,212 -> 901.2 thousand or 0.9M

## States

Use AP abbreviations for states, except when the space is so constrained that only postal abbreviations fit.

## Social

Every app must have at least Facebook and Twitter share buttons. Ideally they should use the standard ProPublica share tab.

## Sources

Under every display of data, graphical tabular or otherwise, should show data sources. We typically do not list sources in the guff except in special circumstances.

## Top Matter

Under the byline should be top matter (at ProPublica we call it "guff") consisting of a paragraph no more than four or five lines of copy, which should accomplish three things: give the reader enough background to be able to understand the purpose of the app; let the reader know how to start using any interactivity; and how to find the story, if any, related to the app or graphic.

## Updates

_Tk move update stuff to here_

TK how do we decide to keep an app up to date?

Unlike a ProPublica article, when we update an app with new data we typically don't append a note explaining every change, as that note would be quite lengthy and not very useful.

However, when an app's data changes the date in the byline should be updated to show when the data was updated. If an app updates dynamically, the updated date should change dynamically. When an app launches the date in the byline can follow ProPublica's standard. When an app is subsequently updated, the date in the byline should say, for example, "Updated May 3, 2012"

We do not need to show both the original publication date and the most recent updated date. Our readers don't really feel the historical weight of this quite like we do. We simply show the latest date.

When the decision is reached to stop updating an app, we put a prominent note on as many pages of an app as are practical that says the date the app stopped being updated and if possible, where to find more recent data.

