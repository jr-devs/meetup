# Aug. 28, 2018

## Talks

My name is **Ed Toro**. I taught at [Wyncode Academy](https://wyncode.co/) in Miami, FL for 4 years before moving to Atlanta about 2 months ago.

### Intro to Ruby

#### What is Ruby?

Ruby is a [Turing complete](https://www.cs.virginia.edu/~robins/Turing_Paper_1936.pdf) programming language.

Programming langauges have [traditionally been written to take it easy on the machine](http://www.hexblog.com/?p=17).

Ruby was written to to make programming easier on humans. ["Ruby is designed to make programmers happy."](https://www.artima.com/intv/rubyP.html)

Why is programmer happiness important?

Imagine a programming langauge spectrum.

At one end, [zeroes and ones](http://www.hexblog.com/?p=17) - hard for a human to understand what's going on, but easy for computers.

At the other end, high-level langauges like [Ruby](http://helloworldcollection.de/#Ruby) and [Python](http://helloworldcollection.de/#Python%C2%A03) - easy for humans to understand, but hard for computers.

Why do we have high-level languages?

Because [computers get twice as fast every two years](https://en.wikipedia.org/wiki/Moore%27s_law), but humans don't get twice as smart.

The things we did to [bend over backwards for computers](http://ascienceenthusiast.com/wp-content/uploads/2015/06/evolution.jpg) half-a-centry ago don't make sense today. Instead of adapting to our tools, our tools should be adapting to us.

Ruby [first appeared in 1995](https://en.wikipedia.org/wiki/Ruby_(programming_language)), the same [year Java was released](https://en.wikipedia.org/wiki/Java_(programming_language)). It was created by Japanese computer scientist [Yukihiro Matsumoto (aka Matz)](https://en.wikipedia.org/wiki/Yukihiro_Matsumoto).

Matz is very polite, so the Ruby community has a motto:
_MINASWAN_: "Matz is nice and so we are nice,"

Ruby is
- An easy-to-use scripting language.
- A well-designed programming language. It's like the Apple of programming languages.
- Designed to make programmers happy.

> Often people, especially computer engineers, focus on the machines. They think, ‘By doing this, the machine will run faster. By doing this, the machine will run more effectively. By doing this, the machine will something something something.’ They are focusing on machines. But in fact we need to focus on humans, on how humans care about doing programming or operating the application of the machines.
https://en.wikiquote.org/wiki/Yukihiro_Matsumoto

Ruby has a strong fanbase. Even people who have moved on to other languages look back fondly upon their time with Ruby.

#### Ruby Syntax

Practice at [REPL.it/languages/ruby](https://repl.it/languages/ruby)

What's the difference?
```ruby
# no newlines
print "Hello", "world"

# free newlines
puts "Hello", "world"
```

Math:
```ruby
1+1
1 - 1 # whitespace is optional
2*2
4/2
```

Floating point math:
```ruby
1/3
5/2

# Use floats if you want the answer to be a float.
1.0/3.0

# On either side
5.0/2
5/2.0
```

[Learn more about floating point arithmetic across different languages.](http://0.30000000000000004.com/)
```ruby
0.1 + 0.2
```

Ruby is an object-oriented langauge.
`object.method(argument, argument, ...)`
In OO-language syntax, the object typically comes first.

The object in OOP is like the subject of the sentence.

_The quick fox jumped over the lazy dog._
Translated into OOP syntax is.
`the_quick_fox.jumped_over(the_lazy_dog)`

_Run Forrest!_ becomes `forrest.run!`

Ruby has standard (canonical) and idiomatic syntaxes:
```rb
1+1    # idiomatic
1.+(1) # standard, but weird looking
```
Ruby converts the idiomatic into the standard. There is always a standard equivalent to every line of Ruby, even if it looks weird.

If the object is missing, it's _implied_ (like the JavaScript `window` object).

Sometimes the implied object is `Kernel`
```rb
puts "hello"         # idiomatic
Kernel.puts("Hello") # standard
```

Mostly the implied object is `self`:
```rb
to_s
self.to_s
```

Ruby has a large _standard library_.
```rb
methods
```

The stdlib is broken up into _modules_.
```rb
Kernel.methods
Math.methods
```

Parentheses and semicolons are optional. This syntax takes the most getting-used-to.
```rb
puts("Hello world");
puts "Hello world"
```
For example `methods` is a _method_ that returns a list of methods.
```rb
methods();
methods
```

To make Ruby more English-language-friendly, Matz noticed that the English language doesn't use (parens) and sem;colons very often, so he designed a language that would look similar. Ruby programs can sometimes look like minimalist poetry.

#### Ruby Data Types

Ruby understands numbers.
```rb
1
1.5
-1
```

Ruby can introspect. You can ask it what something is.
```rb
1.class
-1.class
1.5.class
(1.5).class # parens aren't required, but it makes this clearer
```

And you can ask it what something can do.
```rb
1.methods
```

Use introspection + Google to learn more about the language.

##### Numbers

```rb
1.even?
1.odd?
0.zero?
```

Ruby doesn't care that these methods end with a `?`. But, by convention, methods that end with `?` typically return `true` or `false` (like the answer to a yes/no question).

Rounding a number converts a `Float` into an `Integer`.
```rb
1.5.round
1.5.truncate
1.5.round.class
```

Comparison
```rb
0 < 1
0 <= 1
1 > 0
1 >= 0
0 == 0  # 2 ='s are good enough, 3 is overkill
1 <=> 1 # "spaceship" operator
```
The spaceship operator returns -1, 0, or 1 for less-than, equal-to, or greater-than.

##### Strings

```rb
"hello world"
'hello world'
"hello".class
"hello".methods
```

Some String methods.
```rb
"hello".upcase
"hello".downcase
"hello".capitalize
"hello".length
"a" < "b"
"hello" + " world"
```

Be careful with data types.
```rb
1 + 1
"1" + "1"
```

Convert your data types.
```rb
"1".to_i + "1".to_i
```
Ruby uses the `to_*` convention to indicate methods that change the data type.

Ruby is Unicode-aware.
```rb
puts "💩"
```

Ruby uses standard escape characters:
```rb
puts "Hello\"World"
puts 'Hello\'World'
puts 'Hello\\World'
```

`'string'` and `"string"` are slightly different
```rb
puts "Hello\nWorld"
puts 'Hello\nWorld'
```

##### Booleans

```rb
true
false
```

##### Nil

```rb
nil
"hello".nil?
nil.nil?
1 <=> "1"
```
The "spaceship" operator has 4 possible outputs: `-1`, `0`, `1`, and `nil` (not comparable).

##### Array

```rb
[1,2,3]
[1, 2, 3]
["hello", "world"]
```

Can contain mixed types.
```rb
[1, 1.5, "a", true, nil]
```

##### Hash

```rb
{ "a" => 1, "b" => 2 }
```

Ruby also has a JS-like Hash syntax.
```rb
{a: 1, b: 2}
```

But these two Hashes are not the same.
