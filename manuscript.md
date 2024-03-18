The responsibilities of UI developers has changed a lot in the last 10-15 years. Responsive design and mobile first was a cool buzzword! The web environment was very fragmented - browser support for JS and CSS was different wherever you looked. Remember fixing that thing in Internet Explorer 11 only for it to not work in Internet Explorer 10? All this shaped the frontend role into a highly specialized field. It put a lot of emphasis on finding and coming up with black magic hacks and knowing the intricacies of all the stuff you wanted to use. That's not everything it was of course, but without that you were lost. (remember the time before the inspector had a ruler and you had to hold a physical ruler up to the screen to see if items were aligned?).

The modern frontend role has shifted away from that, and the expectations on UI developers have as well. Browser vendors are nowadays in-sync with each other and working together to ship features. Web apps with Javscript frameworks alongside these endlessly configurable and well-documented component libraries makes for a fairly time-efficient way to ship features nowadays. No more weird clearfix or aspect ratio hacks, no more self-maintained components - we are at that stage where we're expected to put less emphasis on how we build components and more on how we place them (kind of/in general/you know what I mean/you see what I'm saying?).

That's why I won't focus on things like custom properties, @layer, @nesting, :is()/:where() or new color notations because problems like that are already solved in your Material UI-esque setup. It might not be the most fun way to solve them, but we have our business socks on right now and we're going to solve them the business way. Some other time I'd be more than happy to go into depth about these things though!



## Aspect ratio
This is how many of us have approached responsive aspect ratio handling.
In this example we’re applying a 16/9 aspect ratio to an iframe'd youtube video. To get a 16/9 aspect ratio we have to divide 9 / 16 and multiply it by 100 to get this 56.25 seemingly arbitrary percentage value.

This approach works because when we set padding on the y-axis, in a percentage value CSS calculates the padding based on the element’s width. However, as you see, to achieve this we must:
- wrap our target element with a parent element
- apply all this other code from Stack overflow (because who remembers this?)
- and THEN we have a responsive element.

With the aspect-ratio property we can do away with all that and just do this. Now, 16 / 9 is a very standard format, but anything will do really.
The previous picture had a width of 495px and a width of 280px so if that’s the aspect-ratio I have to work with I can just input that!

And this is how easy you define a square! While the aspect-ratio property in an of itself isn’t a giant leap for mankind, it, and most of the other things I am about to show you are very neat solutions absolving us from having to jump through hoops to achieve the designs we want.

## Layout bootcamp

### Kill it with fire
I'm never going to change your mind so let me help you...
#### Impress everyone at work
  - center a div
    display: grid;
    place-items: center;


### I avoid it if I can
The fewer lines you write the better you feel, so I'll try to make them count.
#### Just use gap
In the olden days, grid layouts were half the reason you used something like Bootstrap or Foundation. You all know the drill:
- create your container
- add your items and define at which breakpoint they should be x and y wide

Minus margin, padding on items, headache. If you wanted to style your items in a certain way you have to wrap the one extra time and you'll generally end up with in wrapper hell.

Gap got 100% supported all the way back in 2017 and takes care of all of that. Works with both `flex` and `grid`!

### Ok I guess

#### When to use grid or flex?
While I can't give you a blessed way to decide between grid or flex I can give you a good  rule of thumb:

- I don't need control over my children
  Use flex.
    With flex you decide what your children look like on each child item.
- I want to control my children
  Use grid.
    With grid you do that on the parent level.

### I enjoy it!
#### Replace media queries with grid one-liners
ex:
```css
// replace this
grid-template-columns: 1fr;
@media (width > 475px) {
  grid-template-columns: 1fr 1fr;
}

@media (width > 640px) {
  grid-template-columns: 1fr 1fr 1fr;
}

// with this
grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
```

### OMG LET ME TELL YOU ABOUT SUBGRID!
Let me tell you about subgrid! Prop drilling, but for grid.



Ex:
```css
/* Flex */
.wrapper {
  display: flex;

  .item-1 {
    flex: 2;
  }

  .item-2 {
    flex: 1;
  }
}

/* Grid */
.wrapper {
  display: grid;
  grid-template-columns: 2fr 1fr;
}
```

