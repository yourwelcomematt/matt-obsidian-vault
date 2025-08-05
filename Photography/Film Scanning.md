## Equipment

- Digital camera
	- Fujifilm X-T2
- Macro lens w/ 1:1 magnification for 35mm
	- Note that for smaller sensor sizes you don't necessarily need 1:1 magnification, as this would result in the image being bigger than the sensor itself
		- E.g., for APS-C you only need 1:1.5 magnification, as the sensor is 1.5x smaller than a full-frame sensor
		- However, it can be helpful having greater magnification than what is required, as you can take multiple pictures of an image and stitch them together to get higher resolution
		- You can also adjust the focus to get less magnification
		- https://www.reddit.com/r/AnalogCommunity/comments/1ghy42a/deleted_by_user/
		- https://www.reddit.com/r/AnalogCommunity/comments/t5teyu/apcc_dslr_scanning_35mm_film_do_i_need_an/
		- https://www.dpreview.com/forums/thread/4512290
	- TTartisan 40mm f2.8
		- 1:1 magnification
		- https://www.reddit.com/r/fujifilm/comments/15kffp3/experience_on_ttartisan_40mm_macro_for_dslr/
		- https://www.youtube.com/watch?v=QjRsoiNGF4A
		- Corner sharpness is a lot better than the 7Artisans lens
		- Apparently there can be issues with internal reflections causing a loss of contrast (see Micael Widell's video), although this may not be an issue with film scanning as light is only coming directly into the lens and not from off angles
		- https://www.youtube.com/watch?v=82_Qw_rzDJw
	- 7Artisans 60mm f2.8 v2
		- 1:1 magnification
		- Corner sharpness isn't very good
	- Canon FD 50mm f3.5
		- 1:2 magnification
		- Needs FD-25 extension tube for 1:1 magnification
		- https://www.reddit.com/r/AnalogCommunity/comments/pyqpth/would_a_canon_eos_m3_and_a_canon_fd_50mm_f35/
	- Nikkor 55mm f3.5 or f2.8
		- 1:2 magnification
		- Needs PK-13 extension tube for 1:1 magnification
		- f2.8 is newer but has reported issues with stick aperture blades
- High CRI diffused light source
	- Cinestill CS-Lite
- Film holder
	- Essential Film Holder
		- People have mentioned vignetting issues so may be best to stay away
		- https://www.reddit.com/r/AnalogCommunity/comments/tp4do6/essential_film_holder_not_that_good_for_35mm/
	- Valoi 35mm Holder (also comes in 120)
		- Can't find many negative reviews
	- For cut strips, a negative holder from an enlarger is often better
		- https://www.reddit.com/r/AnalogCommunity/comments/1avccps/film_scan_system_filmcopy_vario_vs_valoi_360/
- Tripod or copy stand or enlarger

Notes on all-in-one solutions like the Valoi Easy 35
- People have mentioned vignetting issues on the Easy 120 video as well as in Reddit threads
- Same for JJC

## Software

- Negative Lab Pro plugin for Lightroom Classic
	- Most popular
- FilmLab
- Grain2Pixel
	- From Kyle's Valoi Easy 35 video: "I don't use Lightroom but Grain2Pixel works like a charm, is free and does batches. Allows quite a lot of post conversion actions and even creates a virtual contact print."
	- https://www.reddit.com/r/AnalogCommunity/comments/1lp8k70/comment/n0tu1mq/?utm_source=share&utm_medium=web3x&utm_name=web3xcss&utm_term=1&utm_content=share_button

## Scanning Process

1. Set the camera up on the tripod or copy stand so that the lens is facing down
2. Place the light source underneath it
3. Place the film holder on top of the light source (the film should be elevated off it and not directly on it for best results)
4. Ensure that the camera is directly parallel to / level with the light source and film holder (can use a mirror for this)
5. Try to turn off or reduce any other lights in the room
6. Insert the film strip into the film holder so that the first frame is illuminated (emulsion side up apparently - need to research this more)
7. Turn the camera on
8. Move the camera up or down until the whole screen is filled with the first frame (leave a bit of border around it though)
9. Camera settings
	1. RAW
	2. Lowest ISO to reduce digital noise (e.g., ISO 100 or 200)
	3. Aperture of f5.6-11 to ensure maximum sharpness - f8 is a good middle ground
	4. Shutter speed on auto
	5. Exposure compensation +1/2 to +1 stop (optional but suggested by Kyle McDougall)
	6. WB constant (Kyle uses 5600K)
	7. Manual focus + focus peaking
	8. Remote shutter release or self-timer to reduce camera shake from pressing the shutter release button
10. Adjust focus until the grains in the film are sharp (can use max aperture like f2.8 to ensure critical focus before stopping down to take the image)
11. Use a blower to remove any dust from the film
12. Take the image using the remote shutter release or self-timer
13. Repeat Steps 1-11 for the remaining images

Levelling the camera and film holder:
- Comment from Teo Crawford's video: "There's a trick to level your camera, you can use a small mirror and place it on top of where the film will be and once the reflection of your lens is in in the middle of the frame of your camera, it is perfectly leveled."
- From Kyle's X-T4 scanning video: "If you line your lens/camera up perfectly you will get even better results. Use a mirror on top of your negative holder, and then line the centre focus point up with the centre of the lens. I too use the 7Artisans, and this line up trick gives cracking results! Also, focus at f2.8 on the grain, then take the shots at f8."
- https://www.valoi.co/how-to-scan-film-with-a-digital-camera
- https://www.valoi.co/post/how-to-level-your-dslr-scanning-setup-making-your-film-and-sensor-parallel

Which side of the film to scan?
- Hashem talks about scanning with the emulsion side facing upwards in this video: https://www.youtube.com/watch?v=SPMekdFH900
	- Less shiny, therefore less issues with reflections
	- Sharper result from testing
	- Can curl up though

Scanning half-frame film
- Apparently APS-C is better for scanning half-frame as you can get closer to the negative
* https://www.reddit.com/r/AnalogCommunity/comments/1hzzk86/valoi_scanning_system_and_macro_lens_advice/

## Editing Process

1) Import the images into Lightroom
2) Use the auto white balance dropper and click on the border of the image (non-photo part of the film) to set the white balance
3) Open the Negative Lab Pro plugin and change the following settings (if required):
	1) Colour Model: Replicates colour profiles of different scanners. Frontier or Noritsu are good choices for colour film. Choose B+W for black and white film.
	2) Pre-Saturation: Can be left as default but Teo Crawford said to use the highest setting, as the default can be a bit desaturated.
	3) Border Buffer: Choose a value that removes the border from around the image. This ensures that the conversion is not affected by the border.
4) Click "Convert Negatives"
5) Edit the converted image to taste using the available settings
	1) Kyle McDougall likes the Linear profile
	2) Uncheck "Make Copy"
	3) Turn off sharpening
6) Click "Apply"
7) In LR, crop the image to remove the border
8) Sharpen the image (Amount = 80-100 and Radius = 1.5 - recommended by Kyle in Easy 35 video)
9) Export to JPEG

From TTArtisan 40mm macro Reddit post:
- "A little tip for processing the RAF files. I import the files from the SD card to Capture One Express (free Fujifilm license), and export them as TIFFs to convert with Negative Lab Pro in Lightroom. It avoids the worming problem with Lightroom and RAF files."

### References

- Refer to Photography playlist in YouTube
- https://www.reddit.com/r/AnalogCommunity/comments/1gggf19/i_spent_weeks_planning_my_first_dslr_film_scan_at/
- https://www.reddit.com/r/AnalogCommunity/comments/1g196pc/what_would_i_need_to_scan_film_negatives/



Film camera recommendations
	* Olympus OM-1 or OM-2 or OM-20
		* Small SLR option
		* OM-1 only takes mercury batteries
		* OM-2 takes SR44 batteries but is harder to find