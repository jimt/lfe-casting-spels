## Global State

Many languages allow for something called *global variables*. The LFE REPL has partial support for this -- you did it when you created the ``objects`` variable earlier.

What does it *mean*, though?

For example, if you have a global variable, you can access from a function. We could have defined our ``cccr`` function like this, to take advantage of the global variable:

```lisp
> (defun cccr ()
    (car (cdr (cdr objects))))
```

That's just *accessing* the global variable; some languages will let you *change* the value of global variables. Conversely, other consider this an *anti-pattern* (something you shoulnd't do) and either discourage it our out-right prevent it.

LFE is one of the latter: you can't change a global variable (unless you do some seriously crazy things to your code ... it *is* a Lisp, after all, so even come impossible things are possible!). LFE does allow you so *shadow* global variables, but that won't change the original; it just covers it up temporarily.

When writing a simple game or modeling objects, global state is an easy thing to use for new-comers. Common Lisp supports this easily. However, in LFE this isn't an option. We're going to have to dive a little deeper for an alternative, and so our game won't be quite as simple as it might have been if we wrote it in Common Lisp or Python. But since LFE is a language for writing distributed systems, you are probably interested in avoiding global state anyway.

So, buckle your seat-belt: before adventure time, we're gonna do some learnin'!
It's okay, though -- it'll be fun :-)