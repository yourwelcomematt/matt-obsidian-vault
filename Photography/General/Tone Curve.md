- Allows us to brighten or darken specific tones in the image
- X-axis is tones from black to white, and Y-axis is brightness from dark to bright
- Histogram represents the distribution of tones in the image
- Parametric tone curve allows adjustment of four preset tone zone sliders - highlights, lights, darks, and shadows
	- Not as useful as the next two curve types as it's more broad/general
- Point tone curve allows us to adjust any tone we want by adding any number of points to the curve
	- Two default points allow us to adjust the black and white points of the image
	- Can use the picker tool to select a specific tone in the image, which will add the corresponding point to the tone curve and allow adjustment of just that tone
	- Adding and adjusting a single point will also affect the rest of the curve, which we may not want; adding more than one point allows us to anchor certain tones so that they don't change too much when a given point is adjusted, meaning the rest of the curve is not as affected
- Colour point curves allow us to introduce colour casts to specific tones in the image (i.e., colour grade it)
	- Doesn't affect exposure - only colour
	- More specific than using the shadow/midtone/highlight colour dials, or HSL sliders
	- Useful for correcting colours in film scan inversions - just move the default points so that they start and end just before their respective colours start to clip in the main histogram

Adjusting contrast using the tone curve
- The contrast slider increases highlights and decreases shadows at the same time by the same amount, which we don't always want as it can be too much and ruin the balance of the image
- The tone curve gives us finer-grain control over contrast as we can target specific highlight and shadow tones and adjust them individually
- A simple way to add contrast is to create an S curve:
	- Add one point in the shadows (top right corner of the bottom left box) and one point in the highlights (bottom left corner of the top right box)
	- Decrease the shadow point and increase the highlight point as needed - they don't need to be adjusted by the same amount
	- This should result in a curve shape that looks like an S

Tone curve vs basics panel
- Basics panel adjustments have access to the full range of data from the RAW file, allowing us to directly change the base shape of the histogram
	- Use this to set the overall bounds or dynamic range of the image
	- Adjusting the whites and blacks sets the absolute brightest and darkest points of the image respectively (i.e., how bright the pure whites and blacks are)
	- Adjusting the highlights changes the mid-to-bright tones that are below pure white
	- Adjusting the shadows changes the mid-to-dark tones that are above pure black
	- Not as precise
- Tone curve adjustments work within the bounds of the dynamic range of the image (i.e., the base shape of the histogram with basics panel adjustments applied)
	- Can only edit what we can see in the image
	- Use this after the basics panel to make finer adjustments to contrast
	- More precise
	- Can't increase the white or black points - can only decrease them (i.e., fade them)

### References
- https://www.youtube.com/watch?v=dDKo7d46WsM How to Master the Tone Curve in Adobe Lightroom (2025) (maike born)
	- Concise, to-the-point, covers all the key info
- https://www.youtube.com/watch?v=iIWZFiKn6vQ This CHANGED My Editing... Learn Lightroom Curves In 20 Minutes (Signature Edits)
	- Comprehensive and well-taught video
- https://www.youtube.com/watch?v=LLBfRQLwHkw How To Use The TONE CURVE In Adobe Lightroom (In-depth!) (Pat Kay)
	- Specifically talks about the relationship between the basic panel settings and the tone curve
- https://www.youtube.com/watch?v=syYShMwcUY8 How to use the Tone Curve in Lightroom (Mitch Lally)
	- Specifically talks about the relationship between the basic panel settings and the tone curve
- https://www.youtube.com/watch?v=VeRFjYMwidE  Master the Tone Curve in 9 MINUTES! (Austin James Jackson)
	- More basic explanation but still useful and shorter
- https://www.youtube.com/watch?v=6CvSFieQGkw
	- The Last Tone Curve Tutorial You'll Ever Need To Watch (Signature Edits)
