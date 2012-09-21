![](https://dl.dropbox.com/u/114112/mobile-logo.png)

## Thursday, September 20

### Sandi Metz (@sandimetz): Go Ahead, Make a Mess

* Objects just need to be more stable than the things that depend on it
* Good OO Design will help manage the mess
* What to do with messy code that has no dependencies (that is the end of the line, like a method that doesn't call anything else)?
  * If it doesn't need to change, leave it. You will never know less than you know now.
  * You can still do a little refactoring
* Unstable dependencies need to be moved
* It's better to send a message than implement behavior
  * Hide the mess by delegating more
  * Factories can help (ie. for delegating something to types `#{class_name}ShockCost`)
* [bit.ly/poodr-combo](http://bit.ly/poodr-combo)

### Ben Orenstein (@r00k): Refactoring from Good to Great

* Extracting to methods means you aren't tempted to read how it's done
* Repeated params are a data clump - you can move them into their own class
  * ie. `@start_date` and `@end_date` become `DateRange.new(start, end)`
* Refactor with tests
* `arr.inject(&:+)`: Sum values in 1.9
* Null Object Pattern
  * `@contact = contact || NullContact.new`
  * `NullContact` returns default values for when contact is absent
  * Some methods can just do nothing
  * Removes checks for `if contact.present?`
  * `NullContact` can be a singleton
  * Can help with logged in / logged out logic as well (`current_user.welcome_message`)
* Not everything works everywhere (_Tell, don't ask_ not necessarily good for views)
* Depend Upon Abstractions
  * Extract stuff into wrapper classes
* When do you refactor?
  * Refactor god objects (usually `User` and whatever your app really uses)
  * Files that change a lot ([danmayer/churn](https://github.com/danmayer/churn))
  * Places that you find bugs
    * You found the bug because you didn't understand the code in the first place

### Justin Searls: To Mock or Not To Mock

* How much reality does a test need?
  * Acceptance tests need a high level of reality
* Tests should be readable to let the next person know how something works
* What value will I get out of this test?
* Use isolation tests to drive design, end-to-end tests to prove it works (the GOOS way)
* Object surface area: how many public methods are on it
* [is.gd/rubymocks](http://is.gd/rubymocks)
* [is.gd/gimmeruby](http://is.gd/gimmeruby)

### Roy Tomeij (@roy): Modular & Reusable Front End Code / The Joy of Front-End

* Bob Ross created modular painting
* [roy.io/book](http://roy.io/book)
* Modular HTML5
  * Sectioning elements can start with h1
  * Modernizr for IE
* Modular CSS
  * Determine and re-use common elements
  * Print out designs and cross out unique elements
  * Refactoring
    * Give similar modules a new class name, style that
    * Make a new css file (clean code goes in clean files)
  * Namespace modules (`mod-foo`)
  * Use generic class names and shallow selectors
  * Use a second class name for specific instances, rather than scoping
    * Second class names don't need to be semantic in naming
  * Use media queries in sass
* Modular JS
  * Use IDs for javascript and testing only
  * Use data attributes instead of classes to target multiple elements
    * [roy.io/datatest](http://roy.io/datatest)
    * Slightly slower than using classes
* Slides: [roy.io/rmr12](http://roy.io/rmr12)

### Angela Harms (@angelaharms): Enhance Your Code With Rainbows

### Lightning Talks Round 1

#### Colin Thomas Arnold (@colinta): RubyMotion

* Compiles ruby into native iOS code

#### Derrick Ko: mailcheck.js

### Growing Developers Panel

* Apprentice developers
* Where are the jobs for people without 3-5 years experience?

## Friday, September 21

### José Valim (@josevalim): Let's Talk Concurrency

* Single Process, Multi-core Concurrency
* In thread, lock with `synchronize {...}`
* Atomic blocks: `atomic {...}`, `ref{...}` for soft transactional memory
* Atomic blocks in ruby not actually atomic, will execute, check, and roll back if necessary
* Message passing
  * `receive` blocks until message is received
  * Client sends message with `server <- message`
* Oz language
* [github.com/celluloid](http://github.com/celluloid)
* _Seven Languages in Seven Weeks_ book
* See slides for references

### Josh Nichols (@techpickles): ChatOps: Using Chat as a Command Line For Your Company

* Tabular output : clitable
* Is it iced coffee weather
* oembed

### Stephan Hagemann (@shageman): Wrangling Large Rails Codebases

* [shageman/the\_next\_big\_thing](http://github.com/shageman/the_next_big_thing)
* Organize models into namespaced Modules
  * adds some structure but doesn't help much else
* Gems bring their own specs
  * the gem only deals with its own stuff
* Higher cohesion inside, looser coupling outside
* Annoyance gem
* use unbuilt gems, require by path
  * `gem "annoyance", path: 'gems/annoyance'`
* Rails engines can wrap behavior
  * use `mount` in routes
  * `isolate_namespace` in engine
* Putting things in boxes won't solve a lot of problems, but it will help

### Derrick Ko (@derrickko): Building in Rails, Backbone and Coffeescript

* XMPP / Pusher / HTML5 SSE
* RABL can replace to_json for responses
* Keep views self-contained for re-use
* Action Caching, View Caching
  * non-cachable views extend cached ones
  * expiring view expires action, but not other views in that action
* require.js
* Don't over-engineer

### Lightning Talks Round 2

#### Ruby command line

* `rescue Interrupt; exit 130`
* [bit.ly/rmr12-sprintf](http://bit.ly/rmr12-sprintf)

#### Cleanshaved

* compile handlebars templates server-side
* [fredjean/clean\_shaved](http://github.com/fredjean/clean_shaved)

#### Ruby on Android

#### Dependency Injection in Ruby

* An object doesn't take what it needs, it get what it needs
* method decorator
* ServiceProvider

#### John Foley (@jw_foley): Project Grok

* Google Hangout?

#### Dave Woodall (@dmwoodall): Learning to Program

#### Cameron Pope: ack

#### Drew Neil: vim

### Paul Elliott (@p_elliott): Expert Consulting

* Everyone is a consultant
* Be an expert in what you know
* Know when to hold 'em, know when to fold 'em
* Propose the best solution, not all the solutions
* Different stakeholders care about different things. Present the right context.

### Russ Olsen: Eloquent Explanations

* The only way we can get smarter is to explain things to each other
* Five ways to make your explanations stick:
  * Take Explaining Seriously
     * Have a plan
     * Don't try to explain everything all at once
  * Be Agile
    * Do it, measure it, fix it, repeat
  * Put the important stuff first
    * Explaining is a timed event
    * Terminology is not the important stuff
    * Supply small victories
    * Tell them it's hard after explaining
  * Don't add extra things
    * Repeat yourself for emphasis and context
  * Mix in some humor
    * _Numerical Methods that Work_ by Forman S. Acton
    * Don't let them get in the way
    * Subtle is better
* Always show up
