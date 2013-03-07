# ProPublica News Apps Style Guide

_by Scott Klein, ProPublica_

This style guide comprises the typographic and technical best practices used by ProPublica's News Applications desk. Most of the rules here also apply to our online graphics, a category that [has a lot in common](#versus) with news applications. It's not meant to be a design spec or a [coding style guide](code.md), though you should probably have both of those.

Using rules consistently can make your job easier and can prevent readers from having to struggle with new interfaces on every project, but remember that overdependence on rules can hamper progress, and that "a foolish consistency is the hobgoblin of little minds." News apps are a new and dynamic field and [forking these rules](README.md) for your own newsroom is a good thing. These rules are not an excuse to avoid change, and nothing in this document should be taken as a discouragement to be weird. This is just a set of decisions we've decided work really well for us, and that we try to stick to.

Finally, this is a living document. Please feel free to [propose changes](README.md).

## Accuracy

The most important thing by far is to be accurate.

A full discussion on how to be sure you're accurate is beyond the scope of this document. Read "[Bulletproofing your data-based stories](data-bulletproofing.md)." Now.

## Axes

Always label axes except where the label would simply duplicate the headline or top matter.

## Browsers

Support the current and prior major release of Chrome, Firefox, Internet Explorer and Safari on a rolling basis. If earlier releases represent more than 2.5% of our audience, continue to support them. This varies only slightly from [Google's Policy](http://googleappsupdates.blogspot.ca/2012/09/supporting-modern-browsers-internet.html).

If you must use a library or technology that has no cross-browser equivalent, provide graceful fallback on other supported browsers.

Support the built-in browsers in the latest revision of the iOS and Android software development kits. All hover and click events should have analogous touch and swipe events on touchscreens.

When feasible, use [responsive web design](http://www.abookapart.com/products/responsive-web-design), with breaks for desktop, tablet and handset. However, if an app or graphic requires so much horizontal space that responsive design would be impractical, make sure that handsets and tablets can see and use those apps in "[overview mode](http://developer.android.com/guide/webapps/targeting.html)."

## Bylines

Bylines are important measures of credit and responsibility. Just as every story has a byline, every news app and graphic should have a byline.

The byline on a news apps or graphic follows the same style as stories. It should never be omitted, and should not appear on the bottom of the page or only on a hidden "credits" screen. In a multi-page app, the byline should be at the top of the first page, under the headline.

The byline should list the developers and reporters who made significant contributions to the app. Be generous with bylines.

## Charts

Avoid pie charts, with one exception: Use them to show the relationship between [part and whole](http://www.excelcharts.com/blog/optimal-number-categories-pie-chart/). Never use a pie chart with more than two elements. [See also](http://pinterest.com/pin/171066485815925388/).

Use a bar chart to show discrete quantities.

Use a stacked bar chart to show the relative values of categories and subcategories of data.

Use a line chart (sometimes called a fever chart) to show continuous variables such as time series.

Use a scatterplot to show a correlation or lack thereof between two variables.

Bubble charts are acceptable where the accurate perception of fine differences between the circles is not important (see Maps). Circles in bubble charts should vary in area and not diameter or radius.

Avoid 3-D charts at all costs. Human have enough problem perceiving area accurately. Asking them to perceive 3-D volume makes matters worse.

Avoid donut charts at all costs.

Don't show interpolated or predicted data without saying you're doing so.

In annual trend data don't include partial years.

## Colors

When you select colors, check to be sure people with color blindness can read and understand the data. We use [Color Oracle](http://colororacle.org/) to do this.

Use [Color Brewer](http://colorbrewer2.org/) to select colors when possible, and not just for maps.

When showing differences in rate of a single variable, stick to a single hue and vary value/lightness. For example, don't fade from blue to pink. The one exception is fading from red to green to show "bad" to "good" (and remember to check your reds and greens for color blindness accessibility).

When showing variations in kind, alter hues.

## Corrections

News apps and graphics should follow your newsroom's standard corrections policy. Observe the following additions:

When data is incorrect, place the correction language on every page that once showed the incorrect data point. That may mean that a correction will appear on thousands of pages.

When an app's data is refreshed and the corrected data has been removed or superceded, remove the correction language to avoid confusion.

## Data: Singular or Plural?

Singular. Say "the data is" and not "the data are," just as you say "bacon is delicious" not "bacon are delicious."

This rule is not without controversy. The AP classifies data as a collective noun that takes the singular when treated as a unit but the plural when referring to individual items ("The data is sound," but "The data have been carefully collected.").

## Dashes

Use spaces around en-dashes, em-dashes and double-hyphens when used in place of em-dashes and en-dashes. Browsers are really bad at spacing lines properly when they contain two long words joined by a dash.

## Geocoding

When making maps of geocoded addresses, use the Google Geocoding API and only show addresses that have accuracies of "ROOFTOP" or "RANGE_INTERPOLATED" in the location_type field. Don't display partial matches.

Do spot checks to make sure everything geocoded, and as with all things, [bulletproof your data](data-bulletproofing.md).

## Guff

(see [Top Matter](#topmatter))

## Headlines

The main page of every news app should have a headline.

## Hovers

It's ok to require readers to hover their mouse over an element to see further detail. However, don't use hovers when seeing more than one of them at the same time is needed to understand the app or graphic.

When requiring hovers in blocks of text (as opposed to in a map or graphic), provide a symbol that lets readers know that the hover is available.

## Interpolated Variables

It's good to write sentences that include interpolated variables, but the fact that you've done so isn't particularly interesting to the general public. Don't change typographic style to highlight interpolated variables.

## Lead-in

(see [Top Matter](#topmatter))

## Legends

It's preferable to label items in a chart directly, but in cases in which that's not possible you should always use a legend that is visible on the reader's computer screen when the chart is visible. Legends should be in the same sequence as the charts they describe.

## Maps

Maps are best when showing data in which geography is an important variable. [Read "When Maps Shouldn't Be Maps" before making any maps](http://www.ericson.net/content/2011/10/when-maps-shouldnt-be-maps/).

All maps must be distinguishable from population maps. To accomplish this, the underlying data should control for population or other denominator. If you make a U.S. state choropleth map and the darkest states are New York, Texas and California, re-read this paragraph.

Use the Texas-Centric Albers Equal Area projection ([EPSG:3083](http://spatialreference.org/ref/epsg/3083/html/)) for a map of the continental U.S. and state-plane maps for individual states. Use the Mercator projection only for tile maps (sometimes called slippy maps).

Avoid bubble maps, which represent the rate of a phenomenon at different locations using differently sized circles. This is for two reasons: First, people cannot accurately perceive differences in the area of circles. Second, bubble maps appear to show the geographic bounds of a phenomenon and not the rate of that phenomenon at the geographic center of the circle. This is another way of saying that they look too much like nuclear blast radius maps.

## Meta Tags

Every page in an app should have a unique title tag, a unique meta-description tag and the correct [social media tags](social-tags.md) specific to that page.

<a name="versus"></a>
## News Applications vs. Graphics

News applications and graphics share a lot of characteristics. Both tell stories with data. Both are an amalgam of design, programming and journalism. So what's the difference? Here are two criteria. One is more technical and so less open to debate, but we admit they're both imperfect:

1. Graphics tend to tell a single story while news applications tell many -- specifically, news applications let readers see how they're personally affected.
2. Graphics tend to run in the browser while news applications tend to require multiple trips to some backend or a runtime on a server.

## Methodology

Document any methodology and present it to readers clearly. Post a link to it prominently in the app or graphic. The methodology (or "nerd box") should detail the sources of the data, the steps you took to clean the data and the exact analysis you ran on the data.

## Money

Use the appropriate currency symbols when showing currency. Avoid showing fractional currency like cents. In most cases, currency for multiple years should be adjusted to current year.

## Numbers

The primary function of numbers in a news application or graphic is to help readers understand scale and order of magnitude, and compare against other numbers. Think of them more like words than like minutely precise coordinates (unless of course your numbers are literally coordinates).

Apply the following rules to numbers wherever they appear in your apps and graphics:

Except where special precision is required, stick to whole numbers. Don't portray precision that doesn't really exist.

Round numbers and never use 'ceiling' or 'floor' functions for floats. Be vigilant if your programming language does this by default.

Except where special precision is required, abbreviate any number over 10,000 by truncating each number after the highest thousands place and appending a word or abbreviation indicating order of magnitude. Use one significant digit after the decimal point. For example:

    10,302,321 -> 10.3 million or 10.3M
    5,242,000,014 -> 5.2 billion or 5.2B
    901,212 -> 901.2 thousand or 901.2K or 0.9M

For numbers with more than three digits, always separate each thousands place with a comma.

Use AP style when using numbers in copy. That is, spell out numbers under 10 except in the following circumstances:

    Use figures for ages, sums of money, time of day, percentages, house numerals, years, days of the month, degrees of temperature, proportions, votes, scores, speeds, time of races, dimensions and serial numbers. ([via](https://websso.wwu.edu/down/index.shtml))

"Not available" and "not applicable" are abbreviated like this: N/A

## States

Use [AP abbreviations](http://en.wikipedia.org/wiki/List_of_U.S._state_abbreviations) for states and avoid postal abbreviations except when the space is so constrained that you have to use them.

We use the [nytimes-style gem](https://rubygems.org/gems/nytimes-style) to help us abbreviate states correctly.

## Sources

Under every display of data, whether it's a map, chart, table or something else, show your data's sources. Do not list sources in the [guff](#guff) except in special circumstances.

## Time

Follow AP abbreviation style for dates, with one exception: Include the year in dates, even when the event described happened during the current year.

Months are abbreviated like this:

    Jan., Feb., March, April, May, June, July, Aug., Sept., Oct., Nov., Dec.

Don't abbreviate months when used alone, or with a year alone, unless space constraints require it.

When including the time in a news app or graphic, abbreviate the meridian in AP Style: a.m. and p.m., with a space between the number and the meridian. We do not show minutes at the exact hour. For example:

    7:31 p.m.
    9 a.m.

We use the [nytimes-style gem](https://rubygems.org/gems/nytimes-style) to help us format time correctly.

<a name="topmatter"></a>
## Top Matter

Put explanatory copy at the top of the first page of your app or graphic, under the byline. This copy goes by many names: "Lead-in," "top matter," etc. At ProPublica we call it "guff." It should be very short -- aim for no more than four or five lines. Avoid re-telling a whole news story, but do make sure you accomplish three things:

1. Give the reader enough background to be able to understand the purpose of the app or graphic.
2. Let the reader know how to start using any interactivity.
3. Explain how to find the related story, if any.

## Total

Only use "total" as an adjective when it's not clear what you're totaling. Never use the redundant "total amount" -- just use "total."

## Updates

Unlike an article, which tends to be a frozen description of a moment in time, news applications tend to be durable resources, and may need to be updated from time to time as new data becomes available.

When updating an app with new data, don't append a note explaining every change, as that note would be quite lengthy and very boring. Simply update the date in the byline to indicate when the data was last updated. If an app updates dynamically, the date in the byline should change dynamically as well.

Don't show both the original publication date and the most recent updated date in the byline. Your readers don't relish the archival history of our work quite like you might. Simply show the date of the latest update (after the word "updated," of course).

When the decision is reached to stop updating an app, put a prominent note on every page of the app that says when the app stopped being updated, and if possible, where to find more recent data.

