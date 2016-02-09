<div id="toc">

<div class="wrapper">

# Contents

</div>

</div>

<div id="mainContainer">

# Accessibility

<div class="entry">

## What's Up, DOCTYPE?

The absence of a DOCTYPE is a crime punishable by death. You may have relied on the following DOCTYPE in the past, but it's important to know that this is now being superceded by a leaner and meaner snippet.

<script type="syntaxhighlighter" class="brush: xml;  toolbar: false; gutter: false;"><![CDATA[ <!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd"> ]]></script>

Ideally, the HTML5 DOCTYPE should be used. It's supported in all modern browsers, and throws IE6 and IE7 into standards mode. [Source](http://ejohn.org/blog/html5-doctype/).

<script type="syntaxhighlighter" class="brush: xml;  toolbar: false; gutter: false;"><![CDATA[ <!DOCTYPE html> ]]></script></div>

<div class="entry">

## Write Valid Semantic Markup

Writing websites with clean, semantic HTML is something we wish we could always do. Sometimes we find ourselves limited by the way pages were setup by our predecessors, or sometimes we're coding a HTML email. The validity of the HTML should never be compromised, even if to solve a browser specific bug.

Headings should be heirarchically created from `<h1>` onwards, paragraphs should always be in `<p>` tags and so on and so forth. If you write semantic HTML, the resultant page will be cleaner, lighter and easily parsed by search engine spiders. This is one of the simplest SEO fixes you can undertake.

### Which do you think looks cleaner, this?:

<script type="syntaxhighlighter" class="brush: xml;  toolbar: false; gutter: false;"><![CDATA[ <span class="sectionHeading">A Heading</span> <br /> <br /> Lorem ipsum dolor sit amet. ... <br /> <br /> ]]></script>

### Or this?

<script type="syntaxhighlighter" class="brush: xml;  toolbar: false; gutter: false;"><![CDATA[ <h1>A Heading</h1> <p> Lorem ipsum dolor sit amet. ... </p> ]]></script></div>

<div class="entry">

## Use Microformats

Microformats are a way of making contact information machine readable. hCard classes (not vCard) are used to define the type of content contained within elements. These are then extracted or highlighted by the browser.

<script type="syntaxhighlighter" class="brush: xml;  toolbar: false; gutter: false;"><![CDATA[ <span class="tel"> <span class="type">home</span>: <span class="value">+1.415.555.1212</span> </span> ]]></script>

If you were to navigate to a page that uses this, you would notice that a program like Skype will easily detect what numbers on the page are phone numbers. Mobile Safari does something similar on iOS devices.

For more information: [http://microformats.org/wiki/hcard](http://microformats.org/wiki/hcard)

</div>

<div class="entry">

## Images Need ‘Alt’ Text

The `<img>` tag requires `alt` text to both validate and meet accessibility guidelines. The text in the `alt` attribute should be descriptive of what the image shows, or is trying to achieve, unless of the course the image is not critical.

If the image is of a list bullet or other trivial icons, it is recommended to simply leave the `alt` attribute empty, but still present. A screenreader will then ignore it, as opposed to having to read out "bullet" 20 times.

<script type="syntaxhighlighter" class="brush: js;  toolbar: false; gutter: false;"><![CDATA[ <img src="dog.gif" alt="Fido and I at the park!" /> <!-- good, descriptive --> <img src="bullet.gif" alt="bullet" /> <!-- bad, as silly as it seems --> <img src="bullet.gif" alt="" /> <!-- good --> ]]></script></div>

<div class="entry">

## Use Tables for Tabular Data Only

Tables should only ever be used for the presentation of tabular data. The only exception is when composing HTML email, in which a table is almost the only thing supported by soul crushing email clients.

For accessibility, table headers should always be presented using `<th>` elements. In .NET datagrids, this can be enabled by setting `showAccessibleHeader` to true. Remember to also set `cellpadding`, `cellspacing` and `border` values to `0` as these are more consistently controlled by CSS.

<script type="syntaxhighlighter" class="brush: xml;  toolbar: false; gutter: false;"><![CDATA[ <table cellpadding="0" cellspacing="0" border="0"> <thead> <tr> <th> Cell Header </th> </tr> </thead> <tbody> <tr> <td> Cell Item </td> </tr> </tbody> </table> ]]></script></div>

<div class="entry">

## Use jQuery & jQuery UI Widgets

jQuery and jQuery UI are constructed to look and behave as close to identical as possible on different browsers. jQuery UI is designed to be WAI WCAG 2.0 and WAI ARI compliant, so using the framework removes any uncertainty about plugins or scripts running on your site.

</div>

# JavaScript

<div class="entry">

## Whitespacing & Formatting

Any discussion about formatting, whitespacing and the placement of braces is going to be hotly debated. I guess the simplest rule is that, unless you're willing to completely format a whole document, **respect and maintain the formatting of an existing document**. That means: see same-line braces throughout a JS file, continue to write code with same-line braces. Your code should fail the code review process if it doesn't maintain consistency with the rest of the document.

Consistent formatting makes code more readable, and also means the code can be easily modified with find and replace commands. The coding habits we have picked up are thankfully very similar to what jQuery officially encourages. There are a few minor discrepencies, but again, these are personal issues or things that we think cannot be maintained. [Further Reading](http://docs.jquery.com/JQuery_Core_Style_Guidelines)

### Character Spacing

<script type="syntaxhighlighter" class="brush: js;  toolbar: false; gutter: false;"><![CDATA[ // Bad if(blah==="foo"){ foo("bar"); } // Good :) if (blah === "foo") { foo("bar"); } ]]></script>

### Same Line Braces

<script type="syntaxhighlighter" class="brush: js;  toolbar: false; gutter: false;"><![CDATA[ // Bad if (foo) { bar(); } // Good :) if (foo) { bar(); } ]]></script>

### Always Using Parenthesis

<script type="syntaxhighlighter" class="brush: js;  toolbar: false; gutter: false;"><![CDATA[ // Bad if (foo) bar(); // Good :) if (foo) { bar(); } ]]></script>

### String Handling

**Strings should always use double quotes**. Some people are very fond of their C style strings (single quotes), but this leads to conflicting styles within a script. C style string handling dictates that empty and single character strings should be wrapped in single quotations, while phrases and words should be wrapped in double quotations.

</div>

<div class="entry">

## Commenting

Javascript code requires regular commenting in order to make it easily understandable. The general rule of thumb for javascript is to use single line comments where possible to quickly and concisely describe what a particular line or block of code is meant to do. If you need to be a little more descriptive eg, describing what a function is meant to do, then the long comment syntax is better.

<script type="syntaxhighlighter" class="brush: js;  toolbar: false; gutter: false;"><![CDATA[ var zeroAsAString = "0"; // Checks if zeroString is 0 and then runs function doHeapsOfStuff() if (zeroAsAString === 0) { doHeapsOfStuff(param1, param2) } /* Initiated When: zeroAsAString === 0 Parameters: param1, param2 */ function doHeapsOfStuff() { } ]]></script></div>

<div class="entry">

## Always Use === Comparison

The use of the == equality operator allows for frustrating bugs to slip through almost undetected. It allows for weak typing that is best explained by [Javascript Garden](http://bonsaiden.github.com/JavaScript-Garden/#types.equality). The use of the strict equality operator === does not run type coercion and therefore strictly evaluates the difference between two objects. Again, consult [Javascript Garden](http://bonsaiden.github.com/JavaScript-Garden/#types.equality) for more information

<script type="syntaxhighlighter" class="brush: js;  toolbar: false; gutter: false;"><![CDATA[ var zeroAsAString = "0"; if (zeroAsAString == 0) { // gets in here lolwut } if (zeroAsAString === 0) { // never gets in here } ]]></script>

### The Exception

Double equals comparison is allowed when comparing to null, because it will detect both null or undefined properties. If you don't fully understand this, I still suggest you use triple equals.

<script type="syntaxhighlighter" class="brush: js;  toolbar: false; gutter: false;"><![CDATA[ var foo = null; // foo is null, but bar is undefined as it has not been declared if (foo == null && bar == null) { // still got in here } ]]></script></div>

<div class="entry">

## Always Specify the Second ‘radix’ Parameter When Using .parseInt()

When parsing a string to an integer, it is considered good practice to specify the second 'radix' parameter - which determines to what base the string should be converted to. It is, by default, octal/binary - so you will run into some problems.

<script type="syntaxhighlighter" class="brush: js;  toolbar: false; gutter: false;"><![CDATA[ alert( parseInt("08") ); // alerts: 2 ]]></script>

It is suggested you always send a value of `10`, as base 10 is generally what we'll be using.

<script type="syntaxhighlighter" class="brush: js;  toolbar: false; gutter: false;"><![CDATA[ alert( parseInt("08", 10) ); // alerts: 8 ]]></script></div>

<div class="entry">

## Avoid Comparing to true and false

Direct comparison to the values of true and false is unnecessary. Sometimes it might be good for clarity, but it's just extra code.

<script type="syntaxhighlighter" class="brush: js;  toolbar: false; gutter: false;"><![CDATA[ if (foo === true) { // good that they're using triple equals, bad as it's ambiguous } if (foo) { // yay! } if (!bar) { // the opposite } ]]></script></div>

<div class="entry">

## Avoid Polluting the Global Namespace

An over-reliance on global variables is something all of us, myself especially, are guilty of. Arguments as to why globals are bad are fairly straight forward: the chance of script and variable conflicts is increased, and both the source file and the namespace itself become littered with countless ambiguously named variables.

[Douglas Crockford](http://yuiblog.com/) believes that the quality of a JavaScript application can be assessed by the number of global variables it uses; the less the better. Given that not everything can be a local (but let's be honest, that one you're thinking about right now, it can, don't be lazy) you need to find a way of structuring your variables to prevent clashes and minimise the bloat. The easiest way is to employ a single variable or a minimal amount of modules on which the variables are set. Crockford mentions that <abbr>YUI</abbr> uses a single global, `YAHOO`. He discusses this in more detail in his blog post ["Global Domination"](http://yuiblog.com/blog/2006/06/01/global-domination/).

Considering that, in the case of small web apps, globals are generally used to store application-wide settings: it's generally better to namespace your project or settings as objects.

<script type="syntaxhighlighter" class="brush: js;  toolbar: false; gutter: false;"><![CDATA[ // polluted global name space var settingA = true; var settingB = false; var settingC = "test"; // a settings namespace var settings = { settingA: true, settingB: false, settingC: "test" } ]]></script>

But if we're avoiding globals to reduce the chance of conflicts, isn't standardising the namespaces to be the same going to increase chance of one app's settings overwriting anothers? Well, it would make sense. It is instead suggested that you namespace your globals to your own specific app name, or reassign your namespace much in the same way that jQuery uses `$.noConflict()` mode.

<script type="syntaxhighlighter" class="brush: js;  toolbar: false; gutter: false;"><![CDATA[ var myAppName = { settings: { settingA: true } } //accessed as myAppName.settings.settingA; // true ]]></script></div>

<div class="entry">

## Camel Case Variables

Shouldn't have to explain this one:

<script type="syntaxhighlighter" class="brush: js;  toolbar: false; gutter: false;"><![CDATA[ var MOUSE_TIMEOUT = 30; // bad var mouseTimeout = 30; // good :) ]]></script></div>

<div class="entry">

## Readable Milliseconds

A handy way of writing milliseconds in a readable format.

<script type="syntaxhighlighter" class="brush: js;  toolbar: false; gutter: false;"><![CDATA[ // is this 3, 30 or 300 seconds? var timeout = 30000; // an extra calculation, but easier to read and modify var timeout = 30 * 1000; ]]></script></div>

<div class="entry">

## Loop Performance - Cache Array Length

Looping is arguably the most important part of JavaScript performance to get right. Shave a millisecond or two off inside of a loop, potentially gain seconds overall. One such way is to cache the length of an array so it doesnt have to be calculated every time the loop is iterated through.

<script type="syntaxhighlighter" class="brush: js;  toolbar: false; gutter: false;"><![CDATA[ var toLoop = ["1000 items"]; for (var i = 0; i < toLoop.length; i++) { // BAD - the length has to be evaluated 1000 times } for (var i = 0, len = toLoop.length; i < len; i++) { // GOOD - the length is only looked up once and then cached } ]]></script>

### The Exception

If you're looping through an array to find an remove a particular item, this will alter the array length. Any time you change the array length by either adding or removing items from inside the loop, you will get yourself into trouble. Consider either re-setting the length or avoid caching it for this particular situation

</div>

<div class="entry">

## Loop Performance - Use ‘break;’ & ‘continue;’

The ability to step over and out of loops is really useful in avoiding costly loop cycles.

If you're looking for something inside of a loop, what do you do once you find it? Say the condition you're looking for is matched halfway through a 1000 item loop. Do you execute whatever you intend to do, and allow the loop to continue to iterate over the remaining 500 items, knowing that there's no chance it will hit an if statement? Nope! You break out of your loop, literally!

<script type="syntaxhighlighter" class="brush: js;  toolbar: false; gutter: false;"><![CDATA[ var bigArray = ["1000 items"]; for (var i = 0, len = bigArray.length; i < len; i++) { if (i === 500) { break; } console.log(i); // will only log out 0 - 499 } ]]></script>

Another problem is skipping over a particular iteration and then continuing on with the loop. While things like odds and evens are better managed by replacing `i++` with `i + 2`, some conditions need to be specifically listened for, to then trigger the skip. Anything that prevent's running through an entire iteration is pretty handy.

<script type="syntaxhighlighter" class="brush: js;  toolbar: false; gutter: false;"><![CDATA[ var bigArray = ["1000 items"]; for (var i = 0, len = bigArray.length; i < len; i++) { if (condition) { continue; } doCostlyStuff(); } ]]></script></div>

<div class="entry">

## Don't Send Too Many Function Parameters

This is a pretty bad idea, more for readability than anything:

<script type="syntaxhighlighter" class="brush: js;  toolbar: false; gutter: false;"><![CDATA[ function greet(name, language, age, gender, hairColour, eyeColour) { alert(name); } ]]></script>

It's a much better idea to construct an object before-hand or to pass the object inline

<script type="syntaxhighlighter" class="brush: js;  toolbar: false; gutter: false;"><![CDATA[ function greet(user) { alert(user.name); } greet({ name: "Bob", gender: "male" }); ]]></script></div>

<div class="entry">

## Remap ‘this’ to ‘self’

When writing object-oriented (OO) JavaScript, the scope of `this` must be understood. Regardless of what design pattern you choose to structure your pseudo-classes, a reference to `this` is generally the easiest way to refer back to an instance. The moment you begin integrating jQuery helper methods with your pseudo-classes is the moment you notice the changing scope of `this`.

<script type="syntaxhighlighter" class="brush: js;  toolbar: false; gutter: false;"><![CDATA[ Bob.findFriend("Barry"); Person.prototype.findFriend = function(toFind) { // this = Bob $(this.friends).each(function() { // this = Bob.friends[i] if (this.name === toFind) { // this = Barry return this; } }); } ]]></script>

In the above example, `this` has changed from a reference to `Bob`, to his friend `Barry`. It's important to understand what happened to the value of `this` over time. Inside of the prototyped function, `this` refers to the instance of the pseudo-class (in this case `Bob`). Once we step inside the `$.each()` loop, `this` is then re-mapped to be item `i` in the parsed array.

It's not incredibly difficult to understand how the scope of `this` changes. I believe the solution is to remap the value of `this` to `self`. This opinion is re-inforced by the jQuery source code, which frequently remaps `this` throughout its functions.

In the following example I will better utilise the parameters made available with the `$.each()` helper, as well as re-mapping the value of `this`.

<script type="syntaxhighlighter" class="brush: js;  toolbar: false; gutter: false;"><![CDATA[ Bob.findFriend("Barry"); Person.prototype.findFriend = function(toFind) { // the only time "this" is used var self = this; $(self.friends).each(function(i,item) { if (item.name === toFind) { return item; } }); } ]]></script></div>

<div class="entry">

## CanIHaz Boolean?

Booleans should be named with the prefixes of `is`, `can` or `has`.

<script type="syntaxhighlighter" class="brush: js;  toolbar: false; gutter: false;"><![CDATA[ isEditing = true; obj.canEdit = true; user.hasPermission = true; ]]></script></div>

<div class="entry">

## Feature Sniff, Don't Browser Sniff

Does the client's browser support geolocation? Does the client's browser support web workers? HTML5 video? HTML5 audio? The answer used to be:

<script type="syntaxhighlighter" class="brush: js;  toolbar: false; gutter: false;"><![CDATA[ if ($.browser.msie) { // no it doesn�t } ]]></script>

But things are rapidly changing. The latest version of IE is almost a modern browser, but as usual it's making front end development a pain. Earlier versions of IE were generally as equally sucky as their predecessors, so it enabled lazy JavaScript developers to simply detect `if (ie)` and execute some proprietary Microsoft slops syntax. Now IE9 has done away with these functions, but that old `if (ie)` chestnut is throwing a spanner in the works.

So what if you could detect support for individual features without sniffing the (unreliable and cloakable) user-agent?

If you answered _"that would be ghetto"_, then you are correct.

In steps [Modernizr](http://www.modernizr.com), a JavaScript library developed in part by industry dream-boat Paul Irish. With wide adoption, tiny file-size and plenty of [documentation](http://www.modernizr.com/docs/#s1): implementing it is a no-brainer. It creates a `Modernizr` object that contains the results of it's detection tests, so checking feature support is as simple as the following:

<script type="syntaxhighlighter" class="brush: js;  toolbar: false; gutter: false;"><![CDATA[ // old way of detecting canvas support if (!!document.createElement('canvas').getContext) { ... } // with Modernizr if (Modernizr.canvas) { ... } ]]></script></div>

# jQuery Specific

<div class="entry">

## Chain Like a Sick Bitch

One of the best parts of jQuery is it's function chaining. You've probably used it a bit, maybe a few simple calls... but have you ever traversed the DOM like a sick bitch? Take some time to familiarise yourself with the [.end()](http://api.jquery.com/end/) function. It is critical for when you begin stepping up and down the DOM tree from your original selector.

<script type="syntaxhighlighter" class="brush: js;  toolbar: false; gutter: false;"><![CDATA[ $(".quote") .hide() .find("a").text("Click here").bind("click",doStuff).end() .parent().removeClass().addClass("testimonial").draggable().end() .fadeIn("slow"); ]]></script>

In the example above, the [.end()](http://api.jquery.com/end/) function is used once we have finished doing things with a particular DOM object and want to traverse back up the DOM to the original object we called. We then load back up and dive back into the DOM.

</div>

<div class="entry">

## ‘.stop()’ Collaborate & Listen

Binding jQuery animations to mouse events is a key part of modern web-based user interaction. It's also something that you see done poorly on even the most famous of web sites. [This article](http://www.learningjquery.com/2009/01/quick-tip-prevent-animation-queue-buildup) provides a straight forward example of built up animations and demonstrates how visually jarring they can be. Thankfully it's easily fixed with a single function prefix or a parameter added to `$.animate` calls.

When using `$.animate`, `queue: false` can be added to the parameters to prevent chaining. Animation shortcuts such as `$.fadeIn` or `$.slideDown` do not take `queue` settings. Instead you have to pre-empt these animations with the `$.stop` method of pausing currently executing animations. Certain scenarios require the animation to stop dead in it's tracks, or to jump to the end of the transition. It is recommended you familiarise yourself with the [documentation](http://api.jquery.com/stop/) of the parameters `clearQueue` and `jumpToEnd`, because god knows I can't help you there.

<script type="syntaxhighlighter" class="brush: js;  toolbar: false; gutter: false;"><![CDATA[ $("selector").stop(true,true).fadeOut(); $("selector").animate({ property: value }, { duration: 1000, queue: false } ]]></script>

Tangentially, I find it odd that what I can only assume is an American authored library uses such a profoundly British word as `queue`.

</div>

<div class="entry">

## Optimise Your Selectors

jQuery is pretty chill. It can do pretty much everything but make you coffee, and I hear that's in the roadmap for 2.0\. One thing you have to be careful about is abusing the power that is the [sizzleJS](http://sizzlejs.com/) selector engine. There are two strategies to overcome this: _caching the selectors results_ and _using efficient selectors_.

### Caching Selector Results

Do a costly DOM query every time you want to change something, or store a reference to the element? Pretty clear choice.

<script type="syntaxhighlighter" class="brush: js;  toolbar: false; gutter: false;"><![CDATA[ // before $(".quote a").bind("click", doStuff); // DOM query eww // now $(".quote a").addClass("quoteLink"); // DOM query eww // later $(".quote a").fadeIn("slow"); // DOM query eww ]]></script>

Ignoring chaining, this is better:

<script type="syntaxhighlighter" class="brush: js;  toolbar: false; gutter: false;"><![CDATA[ // before var $quoteLinks = $(".quote a"); // the only DOM query $quoteLinks.bind("click", doStuff); // now $quoteLinks.addClass("quoteLink"); // later $quoteLinks.fadeIn("slow"); ]]></script>  

### Using Efficient Selectors

So jQuery/sizzleJS can use CSS3 selectors like a boss, but what's the real cost? Behind the scenes the browser is hopefully using `document.querySelector()`, but there's also a fair chance it will be breaking down your selector string and querying the DOM manually.

<script type="syntaxhighlighter" class="brush: js;  toolbar: false; gutter: false;"><![CDATA[ // an ID search is the quickest possible query, then it just takes a list of the childNodes and matches the class $("#quoteList").children(".quotes"); // looks for the "foo" class only in the pre-defined bar element $(".foo",bar); ]]></script></div>

<div class="entry">

## A ‘for’ Loop is Always Quicker Than a ‘each()’ Loop

No matter what happens in the next few years of browser development, a native `for` loop will always be quicker than a jQuery `$.each()` loop. When you think of what jQuery really is (a library wrapped around native JS functions) you begin to realise that the native underlying JavaScript is always going to be quicker. It's a tradeoff of run speed versus authoring speed.

It is vital that a native `for` loop is always used for performance critical functions that could fire potentially hundreds of times per second. Examples include:

*   Mouse movement
*   Timer intervals
*   Loops within loops

</div>

# CSS

<div class="entry">

## Whitespacing

Whitespacing of CSS can be difficult as we chop and change between single and multi line CSS arguments. I'm not going to get into that.

### Proper Spacing

<script type="syntaxhighlighter" class="brush: css;  toolbar: false; gutter: false;"><![CDATA[ /* BAD */ .selector {display:none;background:#ff0000;color:#000000;} /* GOOD - SINGLE LINE */ .selector { display: none; background: #ff0000; color: #000000; } /* GOOD - MULTI-LINE */ .selector { display: none; background: #ff0000; color: #000000; } ]]></script>

### Same Line Braces

<script type="syntaxhighlighter" class="brush: css;  toolbar: false; gutter: false;"><![CDATA[ .selector { display: none; background: #ff0000; color: #000000; } ]]></script>

### Indenting Child Elements

Purely optional, and personally only employed when in a document with single line declarations.

<script type="syntaxhighlighter" class="brush: css;  toolbar: false; gutter: false;"><![CDATA[ .selector { display: none; background: #ff0000; color: #000000; } .selector a { text-decoration: none; } .selector span { font-weight: bold; } ]]></script>

### Grouping & Indenting Vendor Prefixes

<script type="syntaxhighlighter" class="brush: css;  toolbar: false; gutter: false;"><![CDATA[ .selector { background: #FFF; border: 1px solid #000; color: #EAEAEA; -webkit-border-radius: 3px; -moz-border-radius: 3px; border-radius: 3px; } ]]></script></div>

<div class="entry">

## CSS Shorthand

### Grouping Properties

Grouping properties together is one of the single most effective methods to greatly reduce the size of a CSS file. It's important to understand how properties are ordered (clockwise - top, right, bottom, left) and how they can be further shortened (top and bottom, left and right).

<script type="syntaxhighlighter" class="brush: css;  toolbar: false; gutter: false;"><![CDATA[ /* LONG CODE IS LONG */ padding-top: 1px; padding-right: 2px; padding-bottom: 1px; padding-left: 2px; /* BETTER */ padding: 1px 2px 1px 2px; /* BEST */ padding: 1px 2px; ]]></script>

### From 0px to Hero

Assigning a unit type to a properties value of zero is redundant. It is not important to know whether an element should be `0px` from the left or `0 elephants` from the left, just that it's bang on the left.

<script type="syntaxhighlighter" class="brush: css;  toolbar: false; gutter: false;"><![CDATA[ /* BAD */ padding: 0px 10px; ]]></script> <script type="syntaxhighlighter" class="brush: css;  toolbar: false; gutter: false;"><![CDATA[ /* GOOD */ padding: 0 10px; ]]></script></div>

<div class="entry">

## Clearing floats

Clearing a `<div>` used to mean extra DOM, because it involved adding an extra clearer element. The better way is to set a specific width on the parent element (it doesn't work if it's "auto") and an overflow value of either auto or hidden. "Hidden" obviously degrades better, but there are some IE compatibility versions where auto works better.

### The HTML:

<script type="syntaxhighlighter" class="brush: xml;  toolbar: false; gutter: false;"><![CDATA[ <div class="parentElement"> <div class="childElement"> I'm floated left! </div> I'm normal text that wraps around the float </div> ]]></script>

### The CSS:

<script type="syntaxhighlighter" class="brush: css;  toolbar: false; gutter: false;"><![CDATA[ .parentElement { width: 100%; overflow: hidden; } .childElement { float: left; } ]]></script></div>

<div class="entry">

## Feature Sniff, Don't Browser Sniff

In the earlier discusison of JavaScript feature detection, applying properties if a browser is _any version_ of IE is increasingly problematic. Man-of-steel Paul Irish pioneered the use of [IE version sniffing](http://paulirish.com/2008/conditional-stylesheets-vs-css-hacks-answer-neither/) to address this problem, but [Modernizr](http://www.modernizr.com) has since come to the rescue. Modernizr places classes on the root `<html>` element specifying whether features are supported. Bleeding edge styles can then easily cascade from (or be removed from) these classes.

<script type="syntaxhighlighter" class="brush: css;  toolbar: false; gutter: false;"><![CDATA[ .my_elem { border: 1px inset #666; } .borderimage .my_elem { border: none; border-image: url(fancy-border.png) 5 5 5 5 round; -moz-border-image: url(fancy-border.png) 5 5 5 5 round; -webkit-border-image: url(fancy-border.png) 5 5 5 5 round; } ]]></script></div>

<div class="entry">

## You're Not !important

A reliance upon the `!important` tag is a dangerous thing. The cases that warrent its use are rare and specific. They revolve around the necessity to override another stylesheet which you do not have access or permission to edit. Another scenario is hard coding an element's styles to prevent inline JavaScript styles from taking precedence. Instead `!important` is used a lazy shortcut to set the priority of your style over another, causing headaches further down the line.

The use of the `!important` tag can be mostly avoided via the better understanding of CSS selector precedence, and how to better target elements. The more specific the selector, the more likely it will be accepted as the applicable style. The following example from vanseodesign demonstrates the specificity at work.

<script type="syntaxhighlighter" class="brush: css;  toolbar: false; gutter: false;"><![CDATA[ p { font-size: 12px; } p.bio { font-size: 14px; } ]]></script>

[Their article](http://www.vanseodesign.com/css/css-specificity-inheritance-cascaade/) on style precedence does a better job explaining inheritence than I ever could, so please give it a go.

</div>

<div class="entry">

## Aggressive Degredation

It's worth noting that this is a personal opinion, and best suited to very specific situations. The stance of aggressive degradation will not be well received in large commercial projects or enterprise solutions relying upon older browsers.

Aggressive degradation dictates that if a particular (older) browser cannot render a certain effect, it should simply be omitted. A CSS3 button is a good example. Effects such as `border-radius`, `box-shadow`, `text-shadow` and `gradients` will be displayed in cutting edge browsers. A graceful fallback of a `.PNG` would be provided for slightly older browsers, and the most graceful of all solutions would include a PNG-Fix for IE6 or the use of `filter` arguments to replicate gradients and shadows. However, aggressive degradation in this situation instructs you to neglect the older browsers and present them with a flat, satisfactory object.

Put simply, aggressive degradation boils down to: **if your browser can't render a gradient or a box shadow, tough luck**.

While not ideal for every situation, it ensures the timely delivery of projects and that the root product is still usable and not reliant on (validation breaking) hacks.

</div>

# CSS3 & HTML5

<div class="entry">

## Feature Sniff with Modernizr

I think I've gone on enough about this already. Use [Modernizr](http://www.modernizr.com) to detect the availability of specific HTML5 and CSS3 features.

</div>

<div class="entry">

## @font-face Use and Abuse

Before you consider embedding a custom font, is important that you inspect the <abbr>EULA</abbr> and check if web embedding is allowed. Foundries are understandably reluctant to allow designers and developers the ability to place font files directly on a server which can then be copied by a savvy end user. Particular foundries also prohibit the embedding of particular file types, such as `.TTF` and `.OTF`.

If, after careful consideration, you believe the desired font is web embeddable: head on over to the Font Squirrel [@font-face Generator](http://www.fontsquirrel.com/fontface/generator). It utilises Fontspring's [bulletproof @font-face structure](http://www.fontspring.com/blog/further-hardening-of-the-bulletproof-syntax) and automatically generates all the required file formats.

</div>

<div class="entry">

## Degredation

Thankfully browser handling of unsupported HTML5 and CSS3 is already that of a graceful nature. New additions to the list of `<input />` types such as "email", "search" etc. will generally degrade to normal `<input type="text" />` when not natively supported. Similarly, CSS3 properties that aren't supported will simply not appear. Responsive layouts controlled by height and width media queries are simply not applied.

**Subtle CSS3 effects should be employed as a reward for users who run a modern browser.**

The resources section below includes a few libraries to help normalise HTML5 and CSS3 functionality across a range of older browsers.

</div>

# Resources

<div class="entry">

## Support and Suggestions

The following resources are vital for the standardisation of code and interaction in a modern web page. They ensure that CSS3 and HTML5 features are made accessible across a range of browsers that previously lacked support.

*   [jQuery](http://www.jquery.com) JavaScript helper library
*   [jQuery UI](http://www.jqueryui.com) does for UX/UI what jQuery does for JavaScript
*   [Modernizr](http://www.modernizr.com) feature sniff, don't browser sniff!
*   [RespondJS](https://github.com/scottjehl/Respond) brings responsive layouts to older browsers
*   [@font-face Generator](http://www.fontsquirrel.com/fontface/generator) font embedding for all!
*   [RaphaelJS](http://www.raphaeljs.com) easy cross browser canvas drawing

</div>

<div class="entry">

## Support and Suggestions

This document was prepared by Tait Brown ([@taitems](http://www.twitter.com/taitems)).

Questions, corrections and suggestions can be lodged on the [GitHub repository](https://github.com/taitems/Front-End-Development-Guidelines/) for this page. You can also fork your own branch and add your own company/product specific guidelines.

</div>

</div>

<script type="text/javascript">SyntaxHighlighter.all()</script>
