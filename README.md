# Website Optimization Project

This project optimized an existing website by increasing the page score of index.html as well as achieving 60fps performance by altering main.js

## Running the Application

The application can be run by opening index.html and pizza.html with a web browser.

## Changes Made

* index.html
	- Commented out the link to the web font
	- Made a thumbnail for the pizzeria image and deleted the inline CSS
	- Made local copies for the thumbnail images
	- Made a local copy of analytics.js
	- Added async to analytics.js
	- Commented out the links to external CSS files and embedded the code in the page to improve the CRP

* main.js
	- Reduced the number of background pizzas from 200 to 35. Most of them were off screen.
	- Greatly simplified the code for resizing the pizzas, removing unnecessary and complicated calculations. Resizing is now under 5ms.
		- Used the getElementById call instead of querySelector to increase speed.
	- Moved the pizzasDiv outside its for loop so the query wasn't run every time a pizza was generated.
	- Changed the updatePostions function by:
		- Moved the mover selector outside the function so it wouldn't run upon every scroll
		- Stopped the forced synchronous layout by separating the calculations in the for loop into its own separate loop, storing the sin-based values in an array.
		- Use transform:translateX instead of left to avoid repainting the pizzas.
		- Checked the length of randomPIzzas and items in the variable definition of their respective for loops to avoid recalculating them each pass.
	- DOMContentLoaded Event Listner
		- Used getElemetbyId instead of querySelector for speed in the DOMContentLoaded event listener.  Also moved this outside the loop.
		- Changed the property to style.left because of use of translateX in the updatePositions loop.
	- Calculated the number of pizzas needed depending on the screen size, adjusting for smaller, responsive screens.

* style.css
	- Added the will-change:transform and backface-visibility: hidden properties to the mover class