## What is NegPy?

- https://github.com/marcinz606/NegPy/blob/main/docs/USER_GUIDE.md
- NegPy turns film scans into finished positives with a non-destructive, darkroom-style pipeline
- Nothing is ever written back to your source files - every edit lives in a local database, so you can experiment freely
- Processing workflow order (tabs and panels)
	- Setup (cogs icon)
		- Presets
		- Process (film type, negative to positive normalisation)
		- Roll Analysis (roll-wide baselines)
	- Geometry (crop icon)
		- Geometry (crop, straighten)
		- Flat Field (lens/falloff correction)
	- Exposure (sun icon)
		- Filtration (WB, colour casts)
		- Tone (density, contrast, curve)
		- Dodge & Burn
	- Colour (palette icon)
		- Lab (saturation, sharpening, effects)
		- Toning (split/chemical toning)
	- Finish (brush icon)
		- Retouch (dust removal)
		- Finishing (vignette, border, carrier)
	- History (clock icon)
		- Edit History
	- Export (file icon)
		- Export Settings (format, size, colour, batch output)
	- Metadata (tags icon)
		- Archival Metadata (original camera/lens/film details)
	- Scan (camera icon)
		- Scanner
		- Camera Scanning
- You don't have to touch every panel, as NegPy's defaults are tuned to produce a good print straight away - most frames only need a crop, maybe a white-balance nudge, and export
- A small dot on a panel header or tab icon means you've changed something from its default
- Every panel header has a reset action to return it to defaults

## Film strip (left sidebar)

Let's you view your loaded frames as a contact sheet

Half Frame button
- When scanned with two frames per scan, toggling this button on separates the frames automatically, allowing you to apply individual edits to each frame
- When toggled off, the frames are put back together without the edits, which return once it's toggled back on

Culling
- Press K to mark a photo as a keeper
- Press Shift + X to reject a photo
- Rejected photos stay on the contact sheet, however they are dropped from batch exports and sidecar writes
- Sheet menu filters
	- All
	- Keepers only
	- Hide rejected

Tethered camera scanning
- Drives the body and Scanlight directly (macOS/Linux)
- See docs/CAMERA_SCANNING.md

## Controls panel (right sidebar)

Edits auto-save to a local database - no manual save required between files

Process
- Mode picks the chemistry (type of film shot)
- Linear RAW bypasses the as-shot white balance so the orange mask arrives untouched; try on and off and keep what suits your scanning rig
- Luma pass sets the black/white point span
- Per-channel colour pass removes the orange mask
- Luma Range Clip tunes the tonal span
	- Neutral applies a small robust clip
	- Positive tightens the clip (good for dense or fogged negatives where a few stray pixels drag the bounds to extremes)
	- Negative loosens the clip (good for lifted blacks and unclipped highlights)
	- Colour Clip does the same for the per-channel balance
- Lock Bounds freezes the frame's analysed bounds (e.g., white and black points), so cropping or moving a slider no longer re-meters it; lock it in once the conversion looks right
- In E-6 mode a Normalize button appears at the bottom, stretching a faded or expired slide back to the full range
- Crosstalk fixes dye mixing, where a given dye layer absorbs colours outside of its own band, which leak one channel into another and mute colour
	- Pick a profile matching your film stock and blend it in with the Separation strength
	- Re-run Batch Analysis after making any changes, as this step occurs before Batch Analysis
- Roll Consistency
	- Batch Analysis meters every loaded frame and builds a roll-wide baseline
	- Use Roll Average then locks frames to this baseline, so that exposure and colour don't jump from frame to frame
	- Roll presets save and load the baseline for later sessions

Geometry (crop and straighten)
- Cropping out the film base border out is crucial, as the conversion meters what's inside the crop to find the correct black and white points
	- Unexposed rebate sits at film base density, providing a false brightest highlight
	- Sprocket holes and scanner bed provide a false darkest shadow
	- Combined, these can throw off the conversion
	- Alternatively, you can use the Analysis Buffer if you want to keep the border
- Auto detects the film edge
- Fine Rot straightens tilted scans
- Detect Aspect Ratio snaps to the nearest standard ratio
- Guide dropdown switches the overlay grid
	- O cycles between grids
	- Shift + O flips orientation
- Flat-field correction
	- Corrects uneven illumination from your light source or scanner by using a reference scan of the bare light
	- Uneven illumination manifests as vignetting or light fall-off
	- Can save multiple named reference profiles and toggle correction per-image

Exposure & Tone
- Density
	- Slides the negative's log exposure along the paper curve - exactly like enlarger exposure time
	- Lower values print brighter
- Zone Density
	- Shadows Density and Highlights Density darken or brighten each zone while rolling into the paper's black and white limits instead of clipping
	- Shadows Density has the wider travel of the two, since shadow burns (making them darker) are what a print usually needs
- Grade
	- Sets contrast on the photographic ISO-R paper scale (50–180, default 115) - the range of log exposure the paper accepts
	- Lower R is harder (more contrast and punch), while higher R is softer
- Split Grade (Zone Contrast)
	- Shadows Grade and Highlights Grade trim each zone's contrast in ISO-R points on top of the main Grade
	- Can achieve harder shadows without blowing the highlights, or softer highlights without flattening the shadows
	- Both trims spare the midtones and stay bounded by the paper's black and white
- Auto Density and Auto Grade
	- Meter each frame for sensible brightness and contrast out of the box
	- Correct only partially, so low-key and high-key shots keep their mood
	- Turn off to let the conversion follow the negative honestly
	- Set Targets calibrates the Auto Density and Auto Grade to your idea of a good print
		- Print Density Target is how bright the metered midtone prints
		- Contrast Target is the printed contrast every frame is aimed at
		- Strength sliders decide how much each target is trusted - at 0 you get a fixed setting for every frame, at 1 every frame is forced to the same key or the same contrast
- H&D Curve
	- Shapes the shadow and highlight roll-off of the H&D characteristic curve - a model of how photographic paper responds to light, not a generic tone curve
	- Toe lifts the paper-black ceiling - positive gives film a gentle shadow toe, while negative deepens it
	- Shoulder compresses highlights toward paper white - negative extends them instead, and can clip
	- Width controls how far each knee's roll-off reaches up (Toe) or down (Shoulder) the tonal scale
	- Snap controls the paper's variable midtone gamma
	- Paper White simulates paper base density; whites print at ~0.93 rather than pure white
	- Paper Black shows the paper's real D-max as a lifted, slightly milky black
- Global/Red/Green/Blue selector
	- Scopes the curve controls to a single dye layer
	- Split Grades, Toe, Shoulder, Widths and Snap all retarget to that layer, with their labels gaining an R, G or B
	- Grade and Widths swap to dedicated trim sliders centred on zero - you're nudging that layer away from the shared curve, not setting it from scratch
	- Allows you to fix crossover casts that differ between shadows, mids and highlights
	- What isn't per-layer greys out while a channel is selected - Print Density, zone densities, autos and paper toggles are properties of the print
	- No selector in B&W
- Filtration
	- Includes WB and CMY controls
	- Global/Shadows/Highlights buttons scope the CMY sliders to a region for precise split-toning control
	- Temperature slider re-dials the filter pack along the warm–cool axis: Magenta and Yellow move together in the right ratio while the green-magenta tint stays put
	- Cast Removal slider ensures greys read neutral from deep shadows through to highlights
- Paper Response
	- Sets the print character (H&D curve shape) without touching contrast or exposure
	- Each profile carries its paper's tone, per-channel gamma and base tint, mapped from Ilford/Kodak/Foma/Fuji datasheets
	- Profiles are mode-aware (RA4 colour papers in C-41, tonal papers in B&W) and sticky roll-wide
	- Dropdown steps aside entirely in E-6, where a slide is the final image and no paper is involved
- Dodge & Burn
	- Darkroom-style local lighten/darken with freehand polygon masks
	- Draw Mask, click to drop vertices, double-click to close; each mask has its own EV Strength and Feather
	- Masks change the print exposure ahead of the paper curve

Lab
- Colour
	- Separation amplifies R/G/B channel differences for richer colour
	- Saturation boosts all tones equally
	- Vibrance lifts muted tones while protecting already-saturated ones
	- Dye Mute mutes colour in step with print contrast, so a hard grade doesn't run away into poster colour
		- On by default - set to 0 for the fully saturated look
- Sharpen
	- Uses L-channel unsharp masking - no colour halos
- Detail
	- CLAHE applies local contrast enhancement that lifts midtone detail without blowing out highlights
	- Denoise smooths chroma noise in Lab space without touching luminance grain
- Effects
	- Glow simulates lens bloom
	- Halation mimics red scatter caused by light bouncing back through the film base - strongly red-dominant, exactly like real film halation
- Toning
	- Split Toning (all modes) pushes shadows and highlights toward independent hue angles with their own strength
	- Selenium and Sepia simulate classic chemical toners on the print's silver density (B&W mode only)
		- Selenium converts the densest silver first, giving deeper blacks and cool eggplant shadows
		- Sepia bleach-redevelops the thinnest silver first, giving warm highlights that hold the shadows (partial strength gives the classic split-sepia look)
	- Gold is the archival gold bath - a cool blue-black shift in the highlights and mids with a slight density boost, while dense shadows hold
		- Run it over Sepia for the classic combination - toned highlights pushed from yellow-brown toward orange-red

Retouch
- Optical Removal detects and removes small particles on the visible scan by local contrast
	- Lower the threshold to be more aggressive
- Overlay allows you to tune Optical Removal's dust threshold by eye
	- The Marked option paints every spot the detector is about to fix
	- Watch the overlay while you drag a threshold - too aggressive lights up grain, too conservative leaves specks unmarked
- IR Removal works from the scanner's infrared channel, where dust blocks light but the colour dyes don't
- Heal Tool: click individual dust spots in the preview - each heal clones a matching patch from elsewhere in the frame and blends the seam, so grain stays intact
- Scratch Tool: click a polyline along a hair or scratch, double-click or Enter to commit

Finishing
- Print-presentation touches that are applied at the very end of the pipeline
- Edge Burn is a real exposure burn measured in stops
	- Used to achieve a vignette
	- Size sets how far in it reaches
	- Roundness morphs it from a radial falloff to a straight-edged card burn
- Filed Carrier prints the black rebate of a filed-out negative carrier
	- Width sets the frame (0 = off)
	- Roughness breaks up its inner edge the way a filed carrier actually looks
- Border lays a mat around the print
	- Use Width plus Bottom weight for the window-mat proportion where the bottom margin runs deeper
	- Pick its colour from the swatch, or turn on Paper white to tie the mat to the toned paper white so it matches the print instead of fighting it

History
- Lists every edit step for the current photo (up to 100 per file)
- Click any step to jump back to that state (the preview updates instantly), then carry on editing from there
- Right-click a step to Export that this version
- History survives restarts

Metadata
- Writes film and scan info (stock, format, developer, push/pull, scanner) into the EXIF/XMP of exported files
- Click Manage… to open the Gear Library - a searchable, user-extendable library of cameras, lenses and film stocks
	- Gear picked for a frame rides into the exported XMP
- Protect original metadata keeps the source file's EXIF/XMP untouched instead of NegPy rewriting it

Export
- Choose a format (JPEG, high-bit-depth TIFF, PNG, WebP, JPEG XL, DNG), pick a colour space, and set resolution or print size
- Export and Export Presets buttons are triggers - each button's menu arrow picks what it exports (current frame, selected frames, or all visible frames) and remembers the choice
- Contact Sheet renders all frames into one sheet
- Flat exports a flat, neutral, wide-gamut 16-bit TIFF (or linear DNG) digital-intermediate master for editing in Lightroom/Darktable/Photoshop
	- Preview Flat peeks at the master on the canvas
	- Roll Baseline keeps flat masters consistent across a roll

## Keyboard shortcuts

- Press ? or use the ⋯ menu for keyboard shortcuts
- Canvas tools grammar
	- First Esc clears the points you're placing
	- Second Esc puts the tool down
- Shift+S = Scratch
- Shift+B = Dodge & Burn
- Shift+R = Analysis Region
- | = flat-master peek