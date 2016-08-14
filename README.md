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
	- Changed the updatePostions function by:
		- Moved the mover selector outside the function so it wouldn't run upon every scroll
		- Stopped the forced synchronous layout by separating the calculations in the for loop into its own separate loop, storing the sin-based values in an array.

* style.css
	- Added a will-change:transform to the mover class