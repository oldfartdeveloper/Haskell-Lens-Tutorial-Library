# Haskell-Lens-Tutorial-Library
The missing tutorial module for the lens library

## Why this Fork?

Gabriel439 wrote a tutorial that worked well for me except for one area where I simply assumed that his instruction to...

```zsh
$ ghci
>>> import Control.Lens.Tutorial
```

... stood by itself.

In my case, it didn't; it complained that the `lens-tutorial` wasn't installed.  At that point, I realized:

1. I wasn't hooked up to anything that had the lenses; I just started `ghci` with nothing for it to work with except `Prelude`.
1. My own project was using `microlens`, and (I'm told) there are slight differences.

I then realized that his tutorial statements needed to have his project behind it.
So I decided to fork his project and update to the latest versions of the Haskell tools.  This required me to fix some minor
version incompatibilities which are included here in this fork of his project.

## Installation

The following presumes that you have already installed an available Haskell tool set that supports `stack`.

1.  `cd` into your projects where you want to create this Haskell project. Then:

    ```zsh
    git clone https://github.com/oldfartdeveloper/Haskell-Lens-Tutorial-Library.git
    cd Haskell-Lens-Tutorial-Library
    stack init --force
    stack build
    stack repl
    ```

1.  Now you are in the GHCi repl and can execute the instructions in his tutorial:

    ```haskell
    >>> let atom = Atom { _element = "C", _point = Point { _x = 1.0, _y = 2.0 } }
    >>> shiftAtomX atom
    Atom {_element = "C", _point = Point {_x = 2.0, _y = 2.0}}
    ```
    
And that's it.  Hope this helps those of you who were stuck similarly.
