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
- There are eight primitive data types in JS: string, number, bigint, boolean, null, undefined, symbol
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
- Line Styles
	- Letter spacing can be used in negative to create a overlapping effect
	- Line height changes the space between lines (only applies to wrapped text), used for readability
- Use overflow to add scrollbars to content that exceeds its containers width or height
- Pseudo-classes include `:hover`, `:focus`, etc.
- Pseudo-elements allow us to customize different parts of our default elements like `::selection` allows us to change the color of highlighting on our page
- Attribute selectors select all tags with the specified property such as `[href]` for an `img` tag
- Positioning:
	- Static is the default positioning
	- Relative is the same as static but can be displaced using offset properties like `left`
	- Absolute positioning can place something anywhere on the screen without disturbing other elements on the page
	- Fixed is the same as absolute but as you scroll the fixed element retains its position
	- Sticky is the same as fixed but it will only go to a certain position after you scroll to a point where it is out of the viewport
- CSS Functions: 
	- Check out the uses for min(), max(), and clamp()
	- Use CSS variables, declared like so `--example-variable`, with these functions for cool tricks
- Web Compatibility:
	- If you wanna view a website on IOS or iPad OS then make sure the website is compatible with Safari web view
	- Use SASS pre-processor to make CSS more maintainable
- Forms
	- The name attribute determines the names attached to the data the backend receives
	- `fieldset` tags can be used to contain similar form inputs and a `legend` tag can be used to label this `fieldset`
	- Form Validation
		- `required`
		- `minlength`
		- `maxlength`
		- `pattern`
	- Style validations using the `:valid` and `:invalid` pseudo-classes
- Flexbox vs Grid
	- Use a mixture of flexbox and grid to design layouts they are container specific (only affect direct children)
	- Use flexbox when the layout is only aligned with other items in one dimension
	- Use grid for a layout that lines up in both dimensions
	- Grid can also be used to overlap 2 items with variable content lengths (useful!!!)

### Advanced JavaScript
- `class` syntax vs `prototype` syntax
	- `prototype` is a group of properties all objects in JS have
	- This list of functions and values can be changed to create custom objects that share functionality
	- `class` is current convention, syntactic sugar over prototype based solution
	- This is a more familiar way to handle objects and widely used
- npm is the package manager for JS
	- it creates a package.json file with all dependencies
	- --save-dev saves the dependency as a devDependency
	- --save saves it as a normal dependency
	- this allows us to separate packages depending on what is needed in production vs development
- Webpack is used to make JS code compatible with the browser via a build step
	- Browser JS code does not have access to the file system so it cannot pick up dependencies from the node modules folder
	- The build step has access to the file system where it will take all the dependencies and add it to a single output file (typically names dist/main.js), this is known as bundling
	- The index.html file will point to this output JS file and all dependencies will be picked up from there as needed
	- Example command for webpack: `./node_modules/.bin/webpack index.js --mode=development
- Babel is used to transpile JavaScript from ES6 to CommonJS which allows us to write modern JavaScript that is still compatible with older browsers
- We can create workflows for these tools using a build step which automates different parts of the build process
	- Task runners are used to automate the process, this includes tools like Grunt and Gulp
	- Nowadays people use npm scripts
- ES6 modules have replaced the module pattern (IIFEs) in JavaScript
	- ES6 modules are used using `export default <function name>` and `import from '<file path>'` 
	- This allows for code reuse as seen in modern frontend frameworks
	- Only what has been exported can be accessed in other modules and they are only accessible in the file they have been imported to (locally scoped)
	- Allows for easily maintainable code
- ESLint vs Prettier
	- Orgs follow style guides that influence how their employees write their code
	- ESLint is a ruleset of such styles that are highlighted as warnings or errors in code
	- A basic example is the warning when var is used instead of let or const in JS
	- Prettier is a formatter
	- It formats code according to certain rules which allows code to be uniform in format across orgs.
- Template repositories:
	- When creating projects with similar tech stacks and setup use a template repo
	- This will allow use to reuse webpack config etc. in our new projects
- Asynchronous Code:
	- Avoid callback hell; create functions as variables and pass those variables as callbacks
	- Ideally keep code shallow instead of over nesting
	- Modularize to create clearer separation and convey idea through function name
	```
		// modularized and called by declared name
		module.exports.submit = formSubmit
		
		function formSubmit (submitEvent) {
		  var name = document.querySelector('input').value
		  request({
		    uri: "http://example.com/upload",
		    body: name,
		    method: "POST"
		  }, postResponse)
		}
		
		function postResponse (err, response, body) {
		  var statusMessage = document.querySelector('.status')
		  if (err) return statusMessage.value = err
		  statusMessage.value = body
		}
	```
	- Function hoisting allows us to declare the function after its usage in the code
		- When the code is run the function formSubmit and postResponse will be declared before any code is executed
	- To handle errors in callbacks the first line should always be to catch errors