#### CSS Foundations
- * is the universal selector
- Specificity (priority):
	- ID selectors
	- Class selectors
	- Type selectors (tags)
- +, ~, > are all combinators
	- Child selector (>)
	- Adjacent selector (+)
	- General sibling selector (~)
- Combinators don't affect specificity
- Tie-breakers are resolved by using the last defined rule
- The `box-sizing: border-box` rule switches the CSS box model
	- margin, padding and border is made within the width and height of the box
	- rather than adding to the size of the box
- Use *auto* for horizontal centering of any element
- Normal flow refers to how elements are laid out by default
- Block vs Inline
	- Block elements appear on a new line, inline elements do not
	- `<div>` is a block element used as a container for grouping other elements
	- Inline-block allows us to set a height and width to an element inline with other elements
- Flexbox
	- Flex containers contain the `display: flex;` property
	- Flex items are anything inside of a flex container
	- `flex: 1` is shorthand for `flex-grow: 1; flex-shrink: 1; and flex-basis: 0`
	- `flex-grow` can be used to make a single div in the container larger than the others
	- `flex-shrink` is only applied when the size of the container is larger than the space given. It can be used to specify which div will shrink in this case
	- `flex-basis` sets the initial size of a flex item. When set to **auto** the flex item will check for a width declaration
	- Alignment will be according to the flex-direction. Specified in the flex container
	- `justify-content` affects items on the main axis while align-items affects items on the cross axis
	- When `flex-direction` is row then the main axis is horizontal and the cross axis is vertical. When `flex-direction` is column then the axes are swapped

#### JavaScript Foundations
- There are eight primitive data types in JS: ==string, number, bigint, boolean, null, undefined, symbol== 
- There is also one non-primitive data type: object
- Use backticks for strings so that its easier to add variables to string literals
- undefined is the default value for a declared variable
- null is the value assigned to an empty object
- undefined and null are both falsy values
- Truthy and falsy values are those values that when passed into a logical operation are converted to true or false respectively
- Short circuit evaluation in logical operations (using the fact that OR will stop after the first truthy value, AND will stop after the first falsy value)
- JS is single threaded. The call stack works by creating a global execution context (main() or global()) and subsequent function execution contexts
- Anonymous functions are functions without names, often passed as arguments to other functions

### Intermediate HTML & CSS 
- Use semantic HTML when a piece of text needs to be emphasized, if it needs to be styled then a CSS property is enough
- Letter spacing can be used in negative to create a overlapping effect
- Line height changes the space between lines (only applies to wrapped text), used for readability
- Use overflow to add scrollbars to content that exceeds its containers width or height
- 