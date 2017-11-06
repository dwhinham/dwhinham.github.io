---
layout: page
title: Portfolio
permalink: /portfolio/
---

{::options parse_block_html="true" /}

Here is a selection of my previous work and contributions related to graphics, physics, game engine, and other areas of programming.

## Student projects

### Stunt Track Racer (2017)

<div class="gallery">
[![str1_thumb]][str1]
[![str2_thumb]][str2]
</div>

Developed as part of the [Computer Games Development] module of my BSc. degree, this game was designed as a nod to the 1989 classic, [Stunt Car Racer](http://gamesnostalgia.com/en/game/stunt-track-racer) on the Amiga.

The objective is simple - complete the circuit by reaching all the checkpoints before the time runs out. If you fall off the track, you can reset to the previous checkpoint, __BUT__ it will cost you 10 seconds!
 
The game features:
  * A custom game engine written from scratch in C++.
  * Cross-platform support by using [SDL][sdl] and OpenGL.
  * Sophisticated vehicle physics using [Bullet][bullet].
  * Custom "zone"-based memory allocation and management (à la the Doom and Quake engines).
  * Data-driven track, car, and asset loading by means of parsing [YAML](http://yaml.org/) (.yml) files.
  * Semi-automated track geometry generation by using control points loaded from data files to create [Catmull-Rom splines](https://en.wikipedia.org/wiki/Centripetal_Catmull%E2%80%93Rom_spline).

#### Resources

  * [Play in your browser (work in progress - no sound and large download!)](http://lavaburn.untergrund.net/str)
  * [Windows version](/assets/files/str-win.zip)

### Screen-Space Ambient Occlusion (2017)

<div id="ssao" class="twentytwenty-container">
![ssao1]
![ssao2]
</div>

For my final year BSc dissertation project, I chose to implement an advanced graphics rendering technique called _Screen-Space Ambient Occlusion_, or SSAO. This technique allows one to add realtime soft shadows to a 3D scene as a fast post-processing stage within a deferred rendering pipeline.

The aim of the project was to evaluate the performance of the algorithm, both in terms of efficiency and visual appearance. The [Crytek Sponza](http://g3d.cs.williams.edu/g3d/data10/index.html) was chosen as a test scene, and a cross-platform engine was developed as a test bench for the algorithm. [SDL][sdl] was used to ease porting between Windows and Android.

The software project features:
  * A 4-stage deferred rendering pipeline for OpenGL 3.x and OpenGL ES 3.x.
  * Frames-per-second counter.
  * Configurable number of SSAO samples.
  * Ability to enable/disable blurring stage.
  * Ability to examine the "G-buffer" to visualise the different stages of the pipeline.

This project was very interesting as it gave me experience of leveraging framebuffer objects and "render-to-texture" to implement post-processing effects. It was also nice to see that SSAO is feasible on mobile GPUs in 2017; 10 years ago SSAO was just becoming a possibiliy on desktop PC GPUs.

#### Resources

  * [SSAO demo - Windows version](/assets/files/ssao-win.zip)
  * [SSAO demo - Android version on Google Play](https://play.google.com/store/apps/details?id=org.dwhinham.ssaodemo)
  * [Read my dissertation][dissertation_pdf]

## Contributions to other projects

### MilkyTracker (2014-present)

[![mt_thumb]][mt]{: .image-popup-no-margins }

[MilkyTracker] is a cross-platform music creation tool based around the [.XM (eXtended Module)] format. Developed as a clone of [FastTracker II](https://en.wikipedia.org/wiki/FastTracker_2) for MS-DOS, which gained popularity in the 1990s within the games industry and the [demoscene], MilkyTracker has become a go-to tool for musicians aiming to achieve a "retro" or "chiptune" sound.

My involvement with the project began in 2014, when I contributed a reworked port of the program for macOS based around modern APIs ("Cocoa"). Originally, MilkyTracker's Macintosh port was based around "Carbon", a depracated legacy compatibility layer intended as a stop-gap solution for bringing apps from MacOS 9.x to Mac OS X. A more modern port of MilkyTracker based around OpenGL and Cocoa meant that tighter integration with modern macOS features could be achieved.

I now make fairly regular contributions as co-maintainer of the project.

Some of my previous contributions include:
  * Replacing the old Automake build system with a new cross-platform CMake-based one.
  * Setting up [Travis] and [AppVeyor] continuous integration for the project to cover the three major ports (Windows, macOS, Linux).
  * Bugfixes to the Mac Core Audio sound driver.
  * Implementation of miscellaneous feature requests and addressing bug reports.
  * Reworking the old website to use GitHub Pages and Jekyll for easier maintenance.

<script>
$(document).ready(function() {
	$('.gallery').magnificPopup({
		delegate: 'a',
		type: 'image',
		closeOnContentClick: false,
		closeBtnInside: false,
		mainClass: 'mfp-with-zoom mfp-img-mobile',
		image: {
			verticalFit: true
		},
		gallery: {
			enabled: true
		},
		zoom: {
			enabled: true,
			duration: 300
		}
	});

	$('.image-popup-no-margins').magnificPopup({
		type: 'image',
		closeOnContentClick: true,
		closeBtnInside: false,
		fixedContentPos: true,
		mainClass: 'mfp-no-margins mfp-with-zoom',
		image: {
			verticalFit: true
		},
		zoom: {
			enabled: true,
			duration: 300
		}
	});
});

$(function() {
	$('#ssao').twentytwenty({
		default_offset_pct: 0.5, // How much of the before image is visible when the page loads
		before_label: 'No SSAO', // Set a custom before label
		after_label: 'SSAO enabled, 8 samples', // Set a custom after label

		click_to_move: true // Allow a user to click (or tap) anywhere on the image to move the slider to that location.

	});
});
</script>


[str1]: /assets/screenshots/str1.png "Stunt Track Racer - 'A Dead Easy Little Exercise'"
[str2]: /assets/screenshots/str2.png "Stunt Track Racer - 'The Hump Back'"

[ssao1]: /assets/screenshots/ssao1.png "SSAO Demo - SSAO on"
[ssao2]: /assets/screenshots/ssao2.png "SSAO Demo - SSAO off"
[ssao3]: /assets/screenshots/ssao3.png "SSAO Demo - SSAO only"
[ssao4]: /assets/screenshots/ssao4.png "SSAO Demo - G-buffer"

[str1_thumb]: /assets/screenshots/thumbs/str1.png "Stunt Track Racer - 'A Dead Easy Little Exercise'"
{: .float-image }
[str2_thumb]: /assets/screenshots/thumbs/str2.png "Stunt Track Racer - 'The Hump Back'"
{: .float-image }

[dissertation_pdf]: /assets/docs/dale_whinham_screen_space_secondary_lighting.pdf

[ssao1_thumb]: /assets/screenshots/thumbs/ssao1.png
[ssao2_thumb]: /assets/screenshots/thumbs/ssao2.png
[ssao3_thumb]: /assets/screenshots/thumbs/ssao3.png
[ssao4_thumb]: /assets/screenshots/thumbs/ssao4.png

[ssao1]: /assets/screenshots/ssao1.png
[ssao2]: /assets/screenshots/ssao2.png
[ssao3]: /assets/screenshots/ssao3.png
[ssao4]: /assets/screenshots/ssao4.png

[mt]: /assets/screenshots/milkytracker.png "MilkyTracker"

[mt_thumb]: /assets/screenshots/milkytracker.png "MilkyTracker"
{: .float-image }


[sdl]: https://www.libsdl.org
[bullet]: http://bulletphysics.org

[Computer Games Development]: https://www.ncl.ac.uk/module-catalogue/module.php?code=CSC3224

[.XM (eXtended Module)]: https://en.wikipedia.org/wiki/XM_(file_format)
[demoscene]: https://en.wikipedia.org/wiki/Demoscene
[MilkyTracker]: http://milkytracker.titandemo.org
[Travis]: https://travis-ci.org
[AppVeyor]: https://www.appveyor.com