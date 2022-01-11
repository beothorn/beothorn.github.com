Code is supposed to be read

context is important

who is the reader

read top to bottom left to right

avoid eye jumping from left to right

clear call hierarchy (what parameters belong to where)

important things go on the left

x(a,b,c,d){}
vs
pro
easier to rearrange
no need to hunt for commas
x(
    a,
    b,
    c,
    d
){}

formatters can't understand context

People writing the code knows what should be higlighted

pro
easy to write, no effort needed
con
really hard to read, hard to identify what goes where
a(b(c("not important", "also not important"), d("very important, "also very important")))
vs
pro
easy to refactor
highlight problem with too much inlined parameters
easy to identify where each param belongs to
con
calls attention to all parameters
takes a lot of space
a(
    b(
        c(
            "not important", 
            "also not important"
        ), 
        d(
            "very important, 
            "also very important"
        )
    )
)
vs
cons
uninportant parts are hard to read
pro
communicate immediatelly what is important
a(b(c("not important", "also not important"), d(
    "very important",
    "also very important"
)))

a(b(c("very important", "also very important"), d("not important", "also not important")))
vs
a(b(c(
    "very important", 
    "also very important"
), d("not important", also not important)))

even better, but not always possible
cons
require additional code
additional code may become hard to maintain depending on how data is set up
pro
reusable, easy to read
communicates what is important
descriptive instead of imperative
allThings = [
    "very important", 
    "also very important"
]
a(b(cForArray(allThings), d("not important", "also not important")))

