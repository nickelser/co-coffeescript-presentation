!SLIDE full-page

# ![CoffeeScript](logo.png)

## why not enjoy writing javascript again?

!SLIDE bullets

* Powerful, ubiquitous

* Compromise design (unarguable)

* Ugly (arguable)

* Needs libraries to be expressive


!SLIDE smbullets incremental

## **CoffeeScript** to the rescue!

* Not *that* different than javascript
* Combines the best aspects of Ruby and Python
* Whitespace sensitive for code organization
* Compiles into javascript (or is interpreted)


!SLIDE code smaller

    @@@ruby

    # example code (from my demo app)...

    $chat_input.keydown (e) =>
      c = e.keyCode || e.which
      if c == 13 # enter
        msg = $chat_input.val()
        $.ajax
          url: API_URL + 'chat'
          data:
            message: msg


!SLIDE bullets incremental


## Dispelling the 'toy' myth

* Used by [37 Signals](http://basecamphq.com/mobile/), [WordSquared](http://wordsquared.com), [Ars Technica](http://itunes.apple.com/us/app/ars-technica/id393859050?mt=8), [Pow](http://pow.cx/)
* Will be included by default with Rails 3.1
* Full list available from the [CS wiki](https://github.com/jashkenas/coffee-script/wiki/In-The-Wild)


!SLIDE center

# Why should we care?

## (aka the killer features)

!SLIDE center

# Killer Feature #1: **Strings**

!SLIDE code

    @@@ruby
    # Multiline Strings

    html = """
           <div class='player'>
            <span class='name'>
              ...
            </span>
           </div>
           """

!SLIDE code smaller

    @@@ruby

    # String Interpolation (à la Ruby)

    author = "Tupac Shakur"
    quote  = "Reality is wrong. Dreams are for real. -- #{author}"

!SLIDE code

    @@@ruby
    # Interpolation works on regexes too

    sep   = "[.\\/\\- ]"
    dates = /\d+#{sep}\d+#{sep}\d+/g


!SLIDE center

# Killer Feature #2: **Classes / Inheritance**

!SLIDE code smaller center

    @@@ruby
    # Create a class
    class Animal
      constructor: (@name) ->

      move: (meters) ->
        alert @name + " moved " + meters + "m."

    # Inherit from Animal (allows use of super)
    class Snake extends Animal
      move: ->
        alert "Slithering..."
        super 5

    class Horse extends Animal
      move: ->
        alert "Galloping..."
        super 45

    sam = new Snake "Sammy the Python"
    tom = new Horse "Tommy the Palomino"

    sam.move()
    tom.move()

!SLIDE center

# **The Basics**

!SLIDE code

    @@@ruby
    # Assignment:
    number   = 42
    opposite = true

    # Conditional:
    if happy and knowsIt
      clapsHands()
      chaChaCha()
    else
      showIt()

    # Single line Conditional:
    date = if friday then sue else jill


!SLIDE center

# Beautiful Object Syntax

!SLIDE code

    @@@ruby

    # lose the braces
    kids =
      brother:
        name: "Max"
        age:  11
      sister:
        name: "Ida"
        age:  9

!SLIDE center

# Beautiful Function Syntax

!SLIDE code

    @@@ruby

    # Functions:
    square = (x) -> x * x

    # Multiline:
    square = (x) ->
      x * x

!SLIDE code

    @@@ruby

    # bind some jquery events
    $('.nav-item').bind
      click: (e) ->
        console.log("clicked")

      mouseover: (e) ->
        console.log("mouseover")

      mouseout: (e) ->
        console.log("mouseout")

!SLIDE center

# Smart variable scoping

(no more forgetting to type var!)

!SLIDE code

    @@@ruby

    # lexical scoping
    outer = 1
    changeNumbers = ->
      inner = -1
      outer = 10
    inner = changeNumbers()


!SLIDE bullets incremental

# BTW: No global variables!

* Use: `window.myvariable = "something"`


!SLIDE center

# Safely use jQuery

    $ = jQuery

!SLIDE code

    @@@javascript

    // yeah, we don't need to do this anymore
    (function($) {

      // my jquery code

    })(jQuery);

!SLIDE center

# Array Comprehension 

## (yay Python!)

!SLIDE code smaller center

    @@@ruby
    lunch = eat food for food in ['toast', 'cheese', 'wine']

    # Naive collision detection.
    for roid in asteroids
      for roid2 in asteroids when roid isnt roid2
        roid.explode() if roid.overlaps roid2

    # works with ranges
    countdown = num for num in [10..1]

    deliverEggs = ->
      for i in [0...eggs.length] by 12
        dozen = eggs[i...i+12]
        deliver new eggCarton dozen


!SLIDE center

# Everything is an expression!

(implicit return statement for the last line of every function, à la Ruby)

!SLIDE code

    @@@ruby
    grade = (student) ->
      if student.excellentWork
        "A+"
      else if student.okayStuff
        if student.triedHard then "B" else "B-"
      else
        "C"

    eldest = if 24 > 21 then "Liz" else "Ike"

!SLIDE center

# More Goodies

!SLIDE code

    @@@ruby

    # existential operator (checks for undefined and null)

    name = "Joe Blow"
    showErrors() unless name? and email?

    # sets email if it doesnt exist
    email ?= "joe@blow.com"


!SLIDE code

    @@@ruby
    # is
    launch() if ignition is on

    # isnt
    volume = 10 if band isnt SpinalTap

    # unless
    letTheWildRumpusBegin() unless answer is no

    # in
    winner = yes if pick in [47, 92, 13]


!SLIDE code smaller

    @@@ruby
    Account = (customer, cart) ->
      # @customer is an alias for this.customer
      @customer = customer

      # binds "this" to the current Account
      $('.shopping_cart').bind 'click', (event) =>
        @customer.purchase event.cartItem

!SLIDE code

    # Chained comparisons

    cholesterol = 127
    healthy = 200 > cholesterol > 60


!SLIDE center

# Shut up and take my money!

http://coffeescript.org/#installation

!SLIDE bullets

# How to use it:

* Compile to js: `coffee myfile.coffee`

* Watch a folder: `coffee --watch .`

* Interactive: `coffee -i`

* (Or just use [Barista](https://github.com/Sutto/barista))

!SLIDE center

# You can also include 


!SLIDE center

## Learn more at http://coffeescript.org
