---
layout: page
title: Portfolio
permalink: /portfolio/
---

{::options parse_block_html="true" /}

Here is a selection of my previous work and contributions related to graphics, physics, game engine, and other areas of programming.

### Student projects

<div id="str_gallery" style="float:right;">
<a href="/assets/screenshots/str1.png" data-source="http://500px.com/photo/32736307">
<img src="/assets/screenshots/str1.png" width="193" height="125">
</a>
<a href="/assets/screenshots/str2.png" data-source="http://500px.com/photo/32554131">
<img src="/assets/screenshots/str2.png" width="82px" height="125">
</a>
</div>

#### Stunt Track Racer (2017)

Developed as part of the [Computer Games Development module](https://www.ncl.ac.uk/module-catalogue/module.php?code=CSC3224) of my BSc. degree, this game was designed as a nod to the 1989 classic, [Stunt Car Racer](http://gamesnostalgia.com/en/game/stunt-track-racer) on the Amiga.

The objective is simple - complete the circuit by reaching all the checkpoints before the time runs out. If you fall off the track, you can reset to the previous checkpoint, __BUT__ it will cost you 5 seconds!
 
The game features:
  * A custom game engine written from scratch in C++
  * Cross-platform support by using [SDL](https://www.libsdl.org/) and OpenGL.
  * Sophisticated vehicle physics using [Bullet](http://bulletphysics.org/)
  * Custom "zone"-based memory allocation and management (à la the Doom and Quake engines)
  * Data-driven track, car, and asset loading by means of parsing [YAML](http://yaml.org/) (.yml) files
  * Semi-automated track geometry generation by using control points loaded from data files to create [Catmull-Rom splines](https://en.wikipedia.org/wiki/Centripetal_Catmull%E2%80%93Rom_spline)

#### Screen-space Ambient Occlusion Demo (2017)

<div id="ssao" class="twentytwenty-container" style="width:80%;">
![ssao1_img]
![ssao2_img]
</div>

### Contributions to other projects

<script>
$(document).ready(function() {
	$('#str_gallery').magnificPopup({
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
			duration: 300, // don't foget to change the duration also in CSS
			opener: function(element) {
				return element.find('img');
			}
		}
	});
});

$(function() {
  $('#ssao').twentytwenty();
});
</script>


[str1]: /assets/screenshots/str1.png "Stunt Track Racer - 'A Dead Easy Little Exercise'"
[str2]: /assets/screenshots/str2.png "Stunt Track Racer - 'The Hump Back'"

[str1_img]: /assets/screenshots/str1.png "Stunt Track Racer - 'A Dead Easy Little Exercise'"
{: width="120px" style="clear:both;float:right;margin:10px 0px 10px 0px;" }

[str2_img]: /assets/screenshots/str2.png "Stunt Track Racer - 'The Hump Back'"
{: width="120px" style="clear:both;float:right;margin:10px 0px 10px 0px;" }

[ssao1]: /assets/screenshots/ssao1.png
[ssao2]: /assets/screenshots/ssao2.png
[ssao3]: /assets/screenshots/ssao3.png
[ssao4]: /assets/screenshots/ssao4.png

[ssao1_img]: /assets/screenshots/ssao1.png "SSAO Demo - SSAO on"
[ssao2_img]: /assets/screenshots/ssao2.png "SSAO Demo - SSAO off"
[ssao3_img]: /assets/screenshots/ssao3.png "SSAO Demo - SSAO only"
{: width="320px" style="clear:both;float:right;margin:10px 0px 10px 0px;" }
[ssao4_img]: /assets/screenshots/ssao4.png "SSAO Demo - G-buffer"
{: width="320px" style="clear:both;float:right;margin:10px 0px 10px 0px;" }