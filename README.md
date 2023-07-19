# redlang-study
Recording my notes as I study the Red Programming Language

# Carl Sassenwrath's "REBOL Quick Start"

After quite a bit of floundering around, I settled on [this document](http://www.rebol.com/docs/quick-start.html) as a 
way to get started in Red.

## Red does not have `reform`

You will roll along smoothly, converting program headers from having `REBOL` to `Red` until you hit this example in
part 3:

```commandline
REBOL []

birth: 10-Aug-1990

alert reform ["You are" now - birth "days old!"]
```

Gregg Irwin [helped me out](https://matrix.to/#/!wUTlqkqOhNGtfQzIsO:matrix.org/$168971955127iIYhs:gitter.im?via=gitter.im&via=matrix.org&via=tchncs.de) with a couple of solutions as did
[cosacam](https://matrix.to/#/!wUTlqkqOhNGtfQzIsO:matrix.org/$1689775085114yRdnX:gitter.im?via=gitter.im&via=matrix.org&via=tchncs.de).

After this example, I was familiar with [reduce](http://www.rebol.com/docs/words/wreduce.html) as well as
[form](http://www.rebol.com/docs/words/wform.html). Form is a weird name. I think `stringify` or `as-string` would be 
better. And (given my Python background)I think `repr` would be a better for `mold` which I noticed at the bottom of the page while perusing the
docs.


## Red does not have `backdrop` or `btn`

This code failed also:

```
Red []

view layout [
    backcolor gold
    h2 "Web Bookmarks"
    style btn btn 130
    btn "REBOL.com" [browse http://www.rebol.com]
    btn "REBOL.net" [browse http://www.rebol.net]
    btn "REBOL.org" [browse http://www.rebol.org]
]

```

we need to use `backdrop` instead of `backcolor` [according to cosacam1](https://matrix.to/#/!wUTlqkqOhNGtfQzIsO:matrix.org/$1689776726116Iayym:gitter.im?via=gitter.im&via=matrix.org&via=tchncs.de)

Here is the working code:

```commandline
Red []

view layout [
    backdrop gold
    h2 "Web Bookmarks"
    style btn: button 130
    btn "REBOL.com" [browse http://www.rebol.com]
    btn "REBOL.net" [browse http://www.rebol.net]
    btn "REBOL.org" [browse http://www.rebol.org]
]

```
