processing_shaker
=================

Shaker source for Processing. JavaScript/web and Desktop versions.

Hi, I'm posting links to test results based on week 3 code samples and my notes (from the coursera.org class, Creative Programming for Digital Media and Mobile Apps).

Motivation: 
I'm a musician and wanted a free egg shaker to play at guitar meetups. Our gatherings can be quite large so I'd like to be able to increase the volume easily.
To better understand drawing objects around circles. 
To better understand the accelerometer and what I can do with it. 
To try additional visualizations for average Power. 

---

Web demo: http://www.carolchung.com/shaker
Github: (search processing_shaker) https://github.com/mosaicworld/processing_shaker
	(one *.zip file with only the JavaScript and Desktop versions since the Android version was pretty buggy)
Note: source was tested against Processing v2.0.1 (newer versions have been released since the class end)

1 Observations Across Platforms (web/iPad, desktop, Android)

I tried to create a shaker instrument on all 3 platforms and found that the web (javascript) version played on an iPad was the most successful in terms of sound. 

When I tried to read average Power on the desktop or Android device, clicking/tapping the screen resulted in a clicking/static sound (for a short clip, non-looping). Workaround: On the desktop and Android devices, it is better to read average Power on a longer audio clip and enable looping. Visualizing average Power seems to work the best on the desktop.

Found when I get the accelerometer's X value, seems like it's measuring the angle when I rotate the device so that top of device points towards my head or top of device points towards my feet. On Android, when top of device points towards my head, reads like a negative value. On an iPad, when the top of device points towards my head, reads like a positive value.

2a Web/iPad Specific Notes

Best played on an iPad in landscape orientation (requires resizing for iPhone).

Features:
	Tapping on the left side plays a single shaker.
	Tapping on the right side plays a double shaker.
	Rotate the device towards and away from you for volume changes. When the top of the device is pointing towards your head, the volume increases. When the top of the device points towards your feet, the volume decreases.
	
Issues:
	A JavaScript error resulted when trying to use AudioPlayer.setAnalyzing(true) and as a result, I was unable to interpret the average Power in the visualization

2b Desktop Specific Notes

Features:
	Clicking on the left side plays an organ funk clip.
	Clicking on the right side plays a funk rhythm clip.
	Holding the mouse down on either side shows a dynamic average Power visualization.

2c Android Specific Notes

Note: Since the Shaker app crashed regularly on an Android phone, the source was not included on github but test results are shared for info.
	
Issues:
	Extra clicking sound on screen tap (short audio, non-looping, play triggered in draw method)
	Messy orientation reading (due to accelerometer tracking)
	I have an older Android phone and when I try to read in more than one accelerometer dimension (in the draw method), my application often crashes with an out of memory error. 
	I also tried to open the javascript version using the Android browser on my phone but only got visual effects and no sound (probably b/c of an older phone/Android version; TMobile MyTouch 4G; Android 2.3.4 using Android Internet Browser). This issue might be resolved on a phone supporting Android version (4.0) and the Chrome browser for Android. Other browsers for Android (Firefox, Opera Mini, UC Browser) did not resolve the sound issue either.

---

Resources:

http://processing.org/tutorials/trig/

Shaker Audio (web)
	http://www.freesound.org/people/qubodup/sounds/171935/
	(edited with Audacity for 2 separate clips)
	
Music (desktop)
   http://www.freesound.org/people/suonho/sounds/25918/
   http://www.freesound.org/people/Raggaman/sounds/26978/

Image
	Project AngelFood 2013 Calendar
