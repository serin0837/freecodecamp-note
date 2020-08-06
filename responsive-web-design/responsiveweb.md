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
- justify-content(main axis)(horizontal)
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

- display: grid
- grid-template-columns : 50px 50px (2 50px columns)
- grid-template-rows: 50px 50px two rows to the grid that are 50px tall each.
- grid-template-columns: auto 50px 10% 2fr 1fr;
  The first column is as wide as its content, the second column is 50px, the third column is 10% of its container, and for the last two columns; the remaining space is divided into three sections, two are allocated for the fourth column, and one for the fifth.

- grid-column-gap: 10px;
  10px of empty space between all of our columns.

- grid-row-gap:5px;

- grid-gap :
  10px 20px<- 1. row 2. columns
  10 px <- all columns and rows

(from here for itmes/ before was for container)

- grid-column: 1 / 3;
  the item start at the first vertical line of the grid on the left and span to the 3rd line of the grid, consuming two columns.

- grid-row

- justify-self (Align an Item horizontally)): stretch, start,center,end

the content of each item is located in a box which is referred to as a cell

stretch: make the content fill the whole width of the cell.(default)

- align-self(Align an Item Vertically):stretch, start,center,end
