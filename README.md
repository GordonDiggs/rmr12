# Rocky Mountain Ruby 2012

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
* [http://bit.ly/poodr-combo](http://bit.ly/poodr-combo)


