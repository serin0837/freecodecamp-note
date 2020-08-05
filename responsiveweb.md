# CSS position

- position:static <-default
- position:relative <-act as like static but you have options like left,right, top ,bottom
  from static location!!
  (not going to use normally becuase i can only move 1 elemnt, so i have to move each child element )

- position:absolute
  not relative but relative with parent

- position:fixed
  not care of parent, only care whole doc and stick with same position

- position:sticky
  relative+fixed
  (looks like relative but when I scroll stay same place)

# CSS flex

CSS3 introduced Flexible Boxes, or flexbox, to create page layouts for a dynamic UI. It is a layout mode that arranges elements in a predictable way for different screen sizes and browsers.

- display:flex
- flex-direction:
- justify-content(main axis)
- align-item(cross axis)
- flex-wrap
- flex-shrink
- flex-grow
- flex-basis :set initial size
- flex : 1 0 10px (grow, shrink, basis)
- order: the order of how flex items appear in the flex container
- align-self: individually

# CSS Grid

CSS Grid helps you easily build complex web designs. It works by turning an HTML element into a grid container with rows and columns for you to place children elements where you want within the grid.
