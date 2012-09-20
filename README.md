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
