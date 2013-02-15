# ProPublica News Apps Manual of Style

This style guide comprises the typographic and technical best practices used by ProPublica's News Applications desk. Most of the rules here also apply to our online graphics, a category that [has a lot in common](#versus) with news applications. It's not meant to be a design spec or a [coding style guide](code.md), though you should probably have both of those.

Remember that overdependence on and lawyerly appeals to rules can hamper progress, and that a foolish consistency is the hobgoblin of little minds. News apps are a new and dynamic field and rethinking these rules for your own newsroom is a good thing. These rules are not an excuse to avoid change, and nothing in this document should be taken as a discouragement to be weird. This is just a set of decisions we've decided work really well for us, and that we try to stick to.

Finally, this is a living document. Please feel free to [propose changes](README.md).

## Accuracy

The most important thing by far is to be accurate.

A full discussion on how to be sure you're accurate is beyond the scope of this document. Read "[Bulletproofing your data-based stories](data-bulletproofing.md)." Now.

## Browsers

We support the current and prior major release of Chrome, Firefox, Internet Explorer and Safari on a rolling basis. If earlier releases represent more than 2.5% of our audience, we continue to support them. This varies only slightly from [Google's Policy](http://googleappsupdates.blogspot.ca/2012/09/supporting-modern-browsers-internet.html).

If we use technology that has no cross-browser equivalent and is essential to an interactive technique, we provide graceful fallback on other browsers.

We also support the built-in browsers in the latest revision of the iOS and Android software development kits. All of our hover and click events should have analogous touch and swipe events on touchscreens.

When feasible, our apps use [responsive web design](http://www.abookapart.com/products/responsive-web-design), with breaks for desktop, tablet, and handset. However, some apps and graphics require so much horizontal space that responsive design would be impractical. We take a "no heroics" stance in those cases: we make sure that handsets and tablets can see and use those apps in "[overview mode](http://developer.android.com/guide/webapps/targeting.html)."

## Bylines

Bylines are important measures of credit and responsibility. Just as every story has a byline, every news app and graphic has a byline.

The byline on a news apps or graphic follows the same style as stories. It should never be omitted, and should not appear on the bottom of the page or only on a "credits" screen. In a multi-page app, the byline should be at the top of the first page, under the headline.

The byline should list the developers and reporters who made significant contributions to the app. At ProPublica we tend to be generous with bylines, though there should be sensible limits on the number of people listed.

## Charts

We avoid pie charts, with one exception: They can be used to show the relationship between part and whole. We never use a pie chart with more than two elements. We never use multiple pie charts together to show fine-grained differences. In most cases beside showing part vs. whole, we prefer bar charts to pie charts.

We use a bar chart to show discontuous data or to compare relative values of different categories of data.

We use a stacked bar chart to show the relative values of categories and subcategories of data.

We use a line chart (sometimes called a fever chart) to show continuous variables such as time series.

We use a scatterplot to show a correlation or lack thereof between two variables.

We avoid 3-D charts at all costs. Human have enough problem perceiving relative area. Adding a third dimension doesn't help.

## Colors

When you select colors, we check to be sure people with color blindness can read and understand the data. We use [Color Oracle](http://colororacle.org/) to do this.

Generally speaking, we use [Color Brewer](http://colorbrewer2.org/) to select colors when posssible, and not just for maps.

We use a single hue and vary lightness when showing single-vector differences.

We use multiple hues when showing variations in kind.

## Corrections

Our correction policy mirrors ProPublica's Corrections policy, with the following addition:

When data is incorrect, we place the correction language on every page that once showed the incorrect data point. That may mean that a correction will appear on thousands of pages. That's okay.

When an app's data is refreshed and the corrected data has itself been superceded, we remove the correction language to avoid confusion.

## Data: Singular or Plural?

We think it's singular. We say "the data is" and not "the data are," because if "bacon" is singular even when you're referring to lots of it, then so is data.

## Headlines

The main page of every news app should have a headline.

## Interpolated Variables

It's good to write sentences that include interpolated variables, but the fact that we've done so isn't particularly interesting to the general public. We don't change typographic style to highlight interpolated variables.

## Maps

We generally avoid bubble maps, which represent the rate of a phenomenon at various locations using differently sized circles. This is for two reasons: First, people cannot easily perceive differences in the relative area of circles. Second, bubble maps appear to show the geographic bounds of a phenomenon and not the rate of that phenomenon at the geographic center of the circle. This is another way of saying that they always look to us like nuclear blast radius maps.

All maps must be distinguishable from population maps and so the underlying data should control for population or other denominator. If you make a U.S. state choropleth map and the darkest states are New York, Texas and California, re-read this paragraph.

We use the Texas Centric Albers Equal Area projection (EPSG:3083) for a map of the continental U.S. and state-plane maps for individual states. We use the Mercator projection for tile maps (sometimes called slippy maps).

## Meta Tags

Every page in an our apps should have a unique title tag, a unique meta-description tag and social media tags ([here's ours](social-tags.md)) specific to that page.

<a name="versus"></a>
## News Applications vs. Graphics

News applications and graphics share a lot of common characteristics. Both tell stories with data. Both are an amalgam of design, programming and journalism. So what's the difference? Here are two criteria. One is more technical and so less open to debate, but we admit they're both imperfect:

1. Graphics tend to tell a single story while news applications tell many -- specifically, news applications let readers see how they're personally affected.
2. Graphics tend to run in the browser while news applications tend to require multiple trips to some backend or a runtime on a server.

## Methodology

We typically document our methodology, and post a link to it prominently in our apps and graphics. Our methdology section (or "nerd box") should spell out the sources of the data, the steps we took to clean the data and the exact analysis we ran on the data.

## Numbers

We think that the primary function of numbers in a news application or graphic is to help readers understand scale and order of magnitude, and compare them against other numbers. We think of them more like words than like minutely precise coordinates (unless of course they are actual coordinates).

We apply the following rules to numbers wherever they appear in our apps and graphcs:

Except where special precision is required, stick to whole numbers. Don't portray precision that doesn't really exist.

If the number is whole we only use zero padding in columns of numbers where the other numbers in the column have a signficiant digit after the decimal point. We round numbers and never use 'ceiling' or 'floor' functions for floats. Be vigilant if your programming language does this by default.

Except where special precision is required, abbreviate any number over 1,000. Truncate each number after the highest thousands place and append a word or abbreviation indicating order of magnitude. Use one significant digit after the decimal point. For example:

    10,302,321 -> 10.3 million or 10.3M
    5,242,000,014 -> 5.2 billion or 5.2B
    901,212 -> 901.2 thousand or 901.2K or 0.9M

## States

We use [AP abbreviations](http://en.wikipedia.org/wiki/List_of_U.S._state_abbreviations) for states, and avoid postal abbreviations except when the space is so constrained that we have to use them.

We use the [nytimes-style gem](https://rubygems.org/gems/nytimes-style) to help us abbreviate states correctly.

## Sources

Under every display of data, whether it's a map, chart, table or something else, we show the data's sources. We typically do not list sources in the [guff](#guff) except in special circumstances.

## Time

We follow AP abbreviation style for dates, with one exception: Unlike AP style, we include the year in dates, even when the event described happened during the current year.

Months are abbreviated like this: Jan., Feb., March, April, May, June, July, Aug., Sept., Oct., Nov. and Dec. We don't abbreviate months when used alone, or with a year alone, unless space constraints requires it.

When including the time in a graphic or news app we abbreviate the meridian in AP Style: a.m. and p.m., with a space between the number and the meridian. We do not show minutes at the exact hour. For example:

    7:31 p.m.
    9 a.m.

We use the [nytimes-style gem](https://rubygems.org/gems/nytimes-style) to help us format time correctly.

<a name="guff"></a>
## Top Matter

At the top of the first page of our apps, under the byline is typically top matter that we call "guff," consisting of no more than four or five lines of copy, which should accomplish three things:

1. give the reader enough background to be able to understand the purpose of the app.
2. Let the reader know how to start using any interactivity.
3. How to find the story, if any, that's related to the app or graphic.

We avoid re-telling a whole news story in the guff and find that they get read most when they're really short.

## Updates

Unlike an article, which tends to be a frozen description of a moment in time, news applications tend to be durable resources, and may need to be updated from time to time as new data becomes available.

When we update an app with new data we typically don't append a note explaining every change, as that note would be quite lengthy and probably very boring.

However, when an app's data changes, we update the date in the byline to incudate when the data was last updated. If an app updates dynamically, the date in the byline changes dynamically as well.

We don't show both the original publication date and the most recent updated date in the byline. Our readers don't really feel the historical range of our work quite like we do. We simply show the date of the latest update (though we change the typical ProPublica date format to start with "Updated," of course.

When the decision is reached to stop updating an app, we put a prominent note on every page of the that says the date the app stopped being updated, and if possible, where to find more recent data.

