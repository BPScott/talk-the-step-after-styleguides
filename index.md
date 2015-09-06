---
layout: index
title: The Step After Styleguides
description: The Step After Styleguides
author: Ben Scott
size: [1024, 768]
---

<section markdown="1">
# The Step After Styleguides

<small>Ben Scott / [@BPScott](http://twitter.com/BPScott)</small>
</section>


<section markdown="1">
## Who?

* Principal web developer @ [bbc.co.uk/programmes](http://www.bbc.co.uk/programmes)
* If you don't like these principles, I have others
* Dislikes unnecessary repetition

<aside class="notes" markdown="1">
We're the permanent archive of everything that has been
broadcast on the BBC for the past 8 years, with selected programme info going
back even further than that. For instance we've got every episode of Desert
Island Discs back to 1942 categorised and the oldest playable piece of media
we have is an episode of a radio adaption of The Sword in the Stone, originally
broadcast in June 1939. But that's not at all relevant, I just think it's
cool - turns out you quite like the idea of publicly accessible archives if
your mum's a librarian.

Somewhat unsurprisingly, as a programmer I'm not a fan of unneeded repetition.
I'm not just talking about the Don't Repeat Yourself "write DRY code" thing,
but also in language and how we communicate.
</aside>
</section>

<section markdown="1">
## Jargon <small>(n)</small>

> Special words or expressions used by a profession or group that are difficult for others to understand.

<aside class="notes" markdown="1">
Jargon is traditionally a negative term and when used poorly can
exclude people.

So booo! to Jargon.
</aside>
</section>

<section markdown="1">
## Jargon

#### Boooo!

<aside class="notes" markdown="1">
However when used properly, when everybody knows what those
pieces of jargon mean (or can easily look them up) it is a tool to enable
efficient and streamlined communication between teams, thus reducing the time
needed to express ideas and reduce the scope for mistakes.

So actually yay for Jargon.
</aside>
</section>

<section markdown="1">
## Jargon

#### Yay!

<aside class="notes" markdown="1">
This is essentially the ideology behind Design Systems.
</aside>
</section>

<section markdown="1">
## Design Systems

<aside class="notes" markdown="1">
You and your team agree
upon a standard way that you want your brand to be presented - what colours
you use, what typefaces, what font sizes, how you want to represent you common
domain objects - such as a "Programme object" to a show a programme on
aggregation pages like A-Zs in the /programmes world. You talk all these ideas
and give them names and by giving them names you gain power over them, you no
longer have to talk about what something looks like, you talk about what it IS.

</aside>
</section>

<section markdown="1">
## Style that thing

#f54997

<aside class="notes" markdown="1">
For instance if I told you that this a block of text should be the color
#f54997 you'd shrug and go "whatever", but if I told you a block of text is
iplayer-pink you'd know what I'm talking about.
</aside>
</section>

<section markdown="1">
## Style that thing

<span style="color:#f54997;">iPlayer Pink</span>
</section>

<section markdown="1">
## Style that thing

* From 0px: font: 15px, line-height: 18px
* From 320px: font: 16px, line-height: 20px
* From 600px: font: 14px, line-height: 18px

<aside class="notes" markdown="1">
If I told you some text should have a bit of responsive typography: 15px
font-size and 18px line-height as a base. Growing to 16px font-size and 20px
line-height when the viewport is wider than 320px. And finally 14px font-size
and 18px line-height when the viewport is wider than 600px you'd look at me
boggle eyed and think "what a load of very specific crap that I've got to remember". But if I told you this text is the **BBC default text size** you
might be a bit happier.
</aside>

</section>

<section markdown="1">
## Style that thing

GEL Text Base Sizing

<aside class="notes" markdown="1">
Because don't need to remember the exact values of these items all the time, you know that they can be looked up when needed.

This also works with larger items beyond colors and text sizing.
</aside>
</section>

<section markdown="1">
## Style that thing

Words words words words words words words words words words words words words
words words words words words words words words words words words

<span class="fragment">Sod it, here's a picture</span>

<aside class="notes" markdown="1">
Imagine somebody trying to describe a whole page layout to you, all the pieces
of data to be displayed, their positioning in relation to each other, all the
font sizes. It'd be overwhelming to the point where they say "oh sod it here's
a picture."
</aside>
</section>

<section markdown="1">
## Style that thing

TODO Picure of programme objects being laid out from some collection page
e.g. http://www.bbc.co.uk/programmes/p01gyd7j?page=2

<aside class="notes" markdown="1">
But if somebody told me that a page should be 24 programme objects laid out in
a three column grid at the large breakpoint I'd be pretty happy implementing
that.
</aside>
</section>

<section markdown="1">
## Style that thing

24 programme objects in a grid, three per row

<aside class="notes" markdown="1">
I know what a programme object looks like and that it contains a title a synopsis and the other stuff and I know what the standard BBC grid is.

I don't need a full image mockup to envision that, the words are enough.
</aside>
</section>

<section markdown="1">
## Design Systems

### Standardise Patterns

<aside class="notes" markdown="1">
These things become standard ideas and they help enforce consistency. If
somebody shows me a mockup with a different shade of pink I'd ask them if there
was a reason they weren't using the standard iplayer pink. Same for if there
was was some non-standard sized text.

Sometimes there are good reasons for deviating from your standard design
system and it's OK to break away from it, but having it there in the first
place helps you ask that question "This is different, Why?".

It the deviation is justified then great! Add that new variant to your design system for future use. But mostly I've found people say "oh yeah, that doesn't need to be different, use the already existing guidelines".

We found this throughout /programmes' responsive refactor over the past two
years. At the start we were working with our design team and receiving image
mockups (Design as a service is fundamentally flawed, don't ask) that the devs
ripped them apart saying "that's not the standard you provided before, does it
need to be different?" and the answer was usually "No".

The designers then got on board with this idea that there's already a standard
system in place so they didn't need to waste time creating mockups for
everything every time so they started sending us wireframes, knowing that tha
the finer detail for particular page blocks had already been defined. This
came to a head with one of our final page designs where we received... an
email. "These items below those ones, jump to a two column layout at the usual
point". The development team knew exactly what that email meant as it was all pre-existing components.
</aside>
</section>

<section markdown="1">
## Design Systems

### Are Implementation Agnostic

<aside class="notes" markdown="1">
This notion of a Design System is agnostic to any code you write. A single
design system can be implemented in HTML, Android apps or iOS apps - though
your system shall probably have something to say about how to integrate
environment-level conventions like "buttons should look like the OS buttons in
native apps".

Conversely a single design system may have multiple implementations on the
same environment. For example the BBC Global Experience Language defines a
standard grid and typography to be used across all BBC properties but each
team may have its own little foibles and implementation details. The GEL team
provide a reference implementation but we don't force people to use it. As
long as each implementation adheres to the design system it's not a problem if
there are differences in classnames or things like that.
</aside>
</section>

<section markdown="1">
## Design Systems

* Formalise the concept of standard patterns.
* Enforce consistency.
* Don't deal with implementation.

<aside class="notes" markdown="1">
Formalizing the content also includes giving it things standard names

If you want more on Design Systems then Kaelig gave an excellent talk last
year on "Bridging the Gap Between Designers and Developers" based on his work
at the Guardian. And Alla Kholmatova spoke at this years Responsive Day Out
about the process of modular design at FutureLearn.

There'll be links at the end of the slide deck to both of those talks.
</aside>

</section>

<section markdown="1">
## Component Libraries <br>and<br> Styleguides

<aside class="notes" markdown="1">
Once you've got all these ideas for your common patterns you can then write
them into your application - creating css and html fragments within your app
and reusing those styles all over the shop. By leveraging your prior work you
can vastly reduce the amount of effort required to create new templates,
especially if they reuse existing components. However that's meerly "creating a
library of components". There no place to demonstrate those components
that you've created without any other context around them or any documentation
on how to use them. It's tough for the other members of your team to know that
these items already exist or how to use them if there isn't a central place to
demonstrate their use.

So you've got two parts:
</aside>
</section>

<section markdown="1">
## Design System
which is implemented by your

## Component Library
which is documented within your

## Styleguide

<aside class="notes" markdown="1">
* The Component Library: Which is the implementation of your design system
* The Styleguide: The documentation for your component library (including
  examples in isolation)
</aside>
</section>

<section markdown="1">
## Component Library

<div class="grid">
  <div class="grid__item one-half"><h3>CSS-only<br> Foundations</h3></div>
  <div class="grid__item one-half"><h3>HTML<br> Templates</h3></div>
</div>

<aside class="notes" markdown="1">
The starting ground for you component library is that they're very broadly
split into two buckets

* CSS-only Foundations
* CSS & HTML Templates

The foundations pervade your entire site, they aren't so much about concrete
blocks of content, you can't go to a page and say "that bit" but they define
the underlying rhythm and brand of your site. The coloring, typography, grid
systems, form elements - that apply on, there abouts, a per HTML element basis
so there's no value in creating HTML templates for these. If you're familiar
with Brad Frost's Atomic Design then these are the atoms. If if you're not then don't worry, I'll be covering that in more detail later.

Then there's the items that are rendered using those visual foundations and
often correspond to your domain objects. Domain objects being those things you
use to model your problem domain - think entities in your database so for
instance /programmes has things like programme and broadcast objects, BBC News
would have an article object and BBC Food would have a recipe object. These
items require a whole bunch of html to render and probably have some logic
attached to them, for instance if the programme domain object we're rendering
is available to watch then show a play link. You can write these as HTML
partials in whatever templating language you choose.


Being an enterprising sort of people, many developers have created tools to
optimize the creation of these styleguides... KSS, StyleDocco, StyleDown and
Hologram to name a few.
</aside>
</section>


<section markdown="1">
## Styleguide Generators

KSS, StyleDocco, StyleDown & Hologram

&nbsp;

<aside class="notes" markdown="1">
They all seem to work in a similar way: Write some
docblock comments in your CSS files that provide a description of how to use
that CSS component, run a generator script and it'll spit out a bunch of
html files that you can place where ever you need them to go.

This is pretty neat but its only doing half a job.
</aside>
</section>

<section markdown="1">
## Styleguide Generators

<del>KSS, StyleDocco, StyleDown & Hologram</del>

Do half a job.

<aside class="notes" markdown="1">
It's covering the CSS-only parts but they don't have any kind of idea around
how to show output for the larger and more complex html templates - which are
what most people are going to need to make use of when creating new pages.
This means that for me they're a non-starter.

On the up side manually creating documentation pages within your app is pretty easy.
</aside>
</section>

<section markdown="1">
## Styleguide Generators

Don't bother. Write your own.

<aside class="notes" markdown="1">
It's a new controller and a view file for each page of documentation you want
to write. At it's simplest, write your documentation in those view files - no
need for a fancy database or anything else.

This is pretty much what we've been doing for the recently completed responsive
rebuild of /programmes over the past 2 years and it's worked pretty well.
We've got a corner of our app that we use for our styleguide to demonstrate the
major pieces of our front-end architecture at
www.bbc.co.uk/programmes/styleguide. There have been a few little
issues but they've not been big enough warrant the time fixing. However this
has now changed.
</aside>
</section>


<section markdown="1">
## Amen

The next generation of components<br>for /programmes and /radio

<aside class="notes" markdown="1">
We're now working with the team behind /radio on a new version
of iPlayer Radio and we want to share a single visual style across these two
distinct applications developed by different teams. This means that we need to
abstract our component library and styleguide out of the /programmes
application into a neutral location and thatgives us an opportunity to use the
things we learned last time in creating a new stricter, formalised approach.

And so we've wrote our new component library, which we've called Amen for
breakbeat sampling reasons.
</aside>
</section>

<section markdown="1">
## Amen Components

<div class="grid">
  <div class="grid__item one-third"><h3>Styleguide</h3></div>
  <div class="grid__item one-third"><h3>/progs</h3></div>
  <div class="grid__item one-third"><h3>/radio</h3></div>
</div>
</section>

<aside class="notes" markdown="1">
We're using Composer as a package manager and Twig as our templating engine as
we're a PHP shop so let's use the best PHP tools for the job. This means that
potentially the applications can get slightly out of sync if one has deployed a
newer version of Amen but the other hasn't updated yet but we decided that
isn't too bad for two applications. We could have gone down the hardcore route
like the Gov.uk's component library and provided a webservice that
returns the latest template to an application so updates to the component
library don't require multiple application deployments. But we decided that was
loads of engineering effort, building the webservice and the client libraries
that dealt with consuming the web service and caching responses, that was not
worth the time required to develop it when we could be working on other things.
Maybe that's different if you work for a company even more disparate than the BBC.

We chose Twig as a templating language as, well it's the best one out there in
PHP land and we're moving towards building sites with the Symfony and Silex
frameworks which have excellent integration with Twig. We could have used a
language-agnostic templating language like mustache or handlebars to help with
portability into other languages and help render templates on the client-side,
but we have no intention of moving to other languages and we prefer loading
blobs of HTML over AJAX to complex client-side code those pros weren't
relevant to us and sorting out the applications to handle two types of
templating would have been rather tricky. If you want to use the same templates on client and server side then perhaps Handlebars might be a better
fit for you.
</aside>

<section markdown="1">
## Amen Components

<div class="grid">
  <div class="grid__item one-half"><h3>Atoms</h3></div>
  <div class="grid__item one-half"><h3>Molecules</h3></div>
  <div class="grid__item one-half"><h3>Organisms</h3></div>
  <div class="grid__item one-half"><h3>Templates</h3></div>
</div>

<aside class="notes" markdown="1">
For our naming convention and a folder structure we pretty much followed Brad
Frost's Atomic Design which splits your items into four categories.

* Atoms are the fundamental pieces of your design - your colors, typography and
  styling for single elements. As they're single elements there isn't any value
  in having a html template for a <h1> tag for example.
* Molecules are groups of atoms that when combined do something more concrete,
  such as the media CSS object that is a visual abstraction containing
  mulitiple html elements. Or they are the rendering of a single element with
  a piece of simple data inside it that require some logic to display
  according to our standards such as a duration (e.g. we say "1 hour 30
  minutes", instead of "90 minutes".
* Organisms are the next step up and represent a largest section of your
  interface. It's at this level that you start expressing your more complex
  domain objects such as programme objects or article objects. These shall
  almost always contain HTML with a fair big of logic in them.
* Templates are the final step in this chain and are used for structuring a
  layout of organisms. These are mostly what I term aggregations, for instance
  we have a grid aggregation that accepts an array of any type of organism and
  displays them in a grid, so for instance we could have a grid of programme
  objects, a list of broadcasts or a carousel of gallery objects.

</aside>
</section>

<section markdown="1">
## Amen Components

```
TODO GET better TREE of folder structure here
Amen
  - Atom
  - Molecule
  - Organism
    - Broadcast
    - Programme
      - ProgrammePresenter.php
      - ProgrammePresenterInterface.php
      - _programme.scss
      - programme.html.twig
    - Promotion
  - Template
```
<aside class="notes" markdown="1">
As this is an abstracted library, we decided to have a single folder hierarchy
with everything relating to a component all living within the same folder. There's no value in repeating that
folder structure within /styles  and /templates folder. When you're working
you're in the mindset of "I'm working on the X object" not "I'm working on
stylesheets".

We've also realised that a component doesn't only consist of a CSS partial and
a HTML template, but should also have a few extra items.
</aside>

</section>

<section markdown="1">
## Component Interfaces

<div class="fragment" markdown="1">
```php
interface ProgrammePresenterInterface
{
    public function getTitle();
    public function getPlayerUrl();
    public function getImage();
    public function getSynopsis();
}
```
</div>

<aside class="notes" markdown="1">
Any component that has a template where variables get injected into it, for instance the programme component displays a title, also needs an interface to that template and a presenter class that implements said interface.

The interface provides a way of formalising the data object we pass into the
template - by using the type system to assert that we have various methods
available, then we ensure that the template won't throw an exception
complaining about missing data.

For instance if our programme template needs a title, a player url for when we
link to iplayer, an image, a title. Then we can define a
ProgrammePresenterInterface like so.

And we can safely know that any object that implements the
ProgrammePresenterInterface can be successfully rendered by the template. This
helps solve an issue with our prior systems where we weren't always clear on
what information was needed by our templates and what wasn't. This gives us an
explicit list of all values needed by a template so we can be sure we aren't
missing any.

We also need a Presenter Class to be a concrete implementation this interface.
</aside>
</section>

<section markdown="1">
## Presenter Classes

<div class="fragment" markdown="1">
```php
class ProgrammePresenter implements ProgrammePresenterInterface
{
    public function __construct(Programme $programme, array $options) {
      $this->programme = $programme;
      $this->options = $options;
    }

    public function getTitle() {
      return $this->programme->getTitle();
    }

    public function getPlayerUrl() {
      if ($this->programme instanceof Episode
        && $this->programme->isVideo()
      ) {
          return '/iplayer/episode/' . $this->programme->getPid();
        }

      return '/programmes/' . $this->programme->getPid();
    }
}
```
</div>

<aside class="notes" markdown="1">
This is where we can place all of our logic that deals with transforming our
data domain objects into the data that we need within the template. This
additional layer is useful because often your data domain objects don't always
directly translate to a value needed by your templates. For instance the
programme template needs to know what the playout link should be - should this
programme play out in TV iPlayer or iPlayer Radio? It is a purely
presentational concern so it doesn't belong in your data object, but putting
this logic in your template makes it crufty and hard to understand.
This solves the biggest thing we were unhappy with in our old system where our
templates were getting hard to read in some cases as there was a lot of this
sort of logic intermingled in with the HTML.

Amen has a simple rule: Where ever possible all logic should be done in the
Presenter. If a template has an if statement that has more than one conditional
in it then it must be refactored into a method within the presenter. This means
that your templates can focus on showing what is most important to them: your
HTML content.
</aside>
</section>

<section markdown="1">
## Data domain objects
which is implemented by your

## Component Library
which is documented within your

## Styleguide

<aside class="notes" markdown="1">
So you end up with the flow of a Data Domain object from your database is
passed to your Presenter, which is then passed to your template, which renders
its html.

This also means that your presentation layer is decouple from your data layer
and if like us you're in the middle of moving from one data source to another
you create a new Presenter for your new data source format and you're laughing.

Using Presenters also has another fun effect.
</aside>
</section>


<section markdown="1">
## Presenter Tests

<div class="fragment" markdown="1">
```php
class ProgrammePresenterTest extends BasePresenterTest
{
    public function testBasic()
    {
        $pp = new ProgrammePresenter(
            $this->getMockProgramme(),
            array()
        );

        $this->assertEquals('Mock Programme', $pp->getTitle());
        $this->assertEquals('/programmes/b0110ck3', $pp->getPlayerUrl());
    }
}
```
</div>

<aside class="notes" markdown="1">
Now that all your logic is in an class file in your language of choice, you
can go unit test all that logic like you would any other class. So each
Presenter in your component should also have Unit Tests.

Amen has also has another cool thing relating to testing. I found a Symfony
framework module that can parse a html blob and look for elements in it using
CSS selectors and get their content.
</aside>
</section>


<section markdown="1">
## Template Tests

<div class="fragment" markdown="1">
```php
class ProgrammeTemplateTest extends BaseTemplateTest
{
    public function testHideSynopsis()
    {
        $pp = new ProgrammePresenter(
            $this->getMockProgramme(),
            array('show_synopsis' => false)
        );

        $crawler = $this->getCrawlerForTemplate(
            'Organism/Programme/programme.html.twig',
            array('programme' => $pp)
        );

        $this->assertEmpty($crawler->filter('.programme__synopsis'));
    }
}
```

<aside class="notes" markdown="1">
So we're unit testing our templates!

For instance if we pass in an option to say don't render the programme
synopsis, then assert that element doesn't exist in the output.
</aside>
</div>

</section>

<section markdown="1">
## TL;DR

* Formalise your design system
* Extract logic into Presenter Classes
* Keep your HTML templates clean
* Test all the things

</section>

<section markdown="1">
## Link Dump

* [Bridging the gap between designers and developers](https://www.youtube.com/watch?v=ciG-A_1FyVg)
* [Modular Design](http://www.fivesimplesteps.com/products/modular-design)
* [Atomic Design](http://bradfrost.com/blog/post/atomic-web-design/)
* [Amen](http://amen.tools.bbc.co.uk/)

</section>

<section markdown="1">
# The Step After Styleguides

<aside class="notes" markdown="1">
This title of this talk was "The step after styleguides". There actually isn't one. Your styleguide is the documentation of your component library
but maybe your component library can contain more than just CSS and HTML
fragments.
</aside>
</section>

<section markdown="1">
# Thank You

### Any Questions?

<small>Ben Scott / [@BPScott](http://twitter.com/BPScott)</small>

<small>[reload.me.uk/talk-the-step-after-styleguides](http://www.reload.me.uk/talk-the-step-after-styleguides)</small>
</section>
