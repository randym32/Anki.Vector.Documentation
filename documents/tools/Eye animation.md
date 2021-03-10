# Eye Animation tools

The eye parameters in the animation files are very complex.
FBS animation file in turn took different eye patterns, and interpolated
movements between the points.

## Individual frames

The animator's probably only rarely set up the eye in detail.
Instead, they had tools to simplify the process.
They were pre loaded with the eye settings for many common looks 
that took into account:

* Brow
* Gaze direction (left to right, up to down)
* Cheeks
* How open, closed, the eyes are such as eye squint (per eye?), or sleepiness
* Head tilt
* Squash and stretch -- at least, how close and far apart the eyes are

We saw some of the animators tools in magazines photos, and they give clues to
the controls that they worked with.  
Below are screen grabs of the eye animation tools for Cozmo and Vector:

These tools likely translate the button settings into one of a couple of
dozen "canned" eye patterns (pre-programmed eye parameters).

![Cozmo's eye configuration tool](CozmoEye-config.png#center#zoom)
_Figure: Cozmo's eye configuration tool_

![Vector's eye configuration tool](VectorEye-config.png#center#zoom)
_Figure: Vector's eye configuration tool_

We can clearly see the controls to where Vector should look, some of his relative
eye shape, and so on.


## What about movement, and playing with movement

On Cozmo and Vector, the animation system moves its working version of each the
parameters to transition from frame to frame over the given time period.

On the desktop, the animation tools likely do this as well -- looping movements
between the eye frames to checkout the eye motion.

There probably was a style guide or informal rules on the kinds of frames to use 
(and when) for eye shape and movement to reflect:

* Internal state like emotion, mood, stress,
* Blinking, and  breathing.
* Sleepiness and interest


## JoystickNSliders techniques

Last spring Digital Dream Labs animator Molly Wright made an interesting
video using a JoystickNSliders to animate a Cozmo/Vector fact.
This tool probably reflects how these could have worked.

* [Making Cozmo and Vector an UwU Face #joysticksnsliders](https://www.facebook.com/digitaldreamlabs/videos/203227877312275/)
  (May 22, 2020)

This one is interesting in presenting a bit more of how to think about the eyes.
It appears to have simplified the eye controls four axis:


1. Worry vs Curiosity.
2. Mad vs happy
3. A blink rate, from slow to fast
4. A gaze direction of left to right

The tool works by setting up the eye parameters for each end of the slider, and
perhaps the middle.
These form the template for how the eyes look.
Then, as the sliders move, it performs an interpolation between each of these points.

Some, like the blinking, may be a bit of timer and controls a few other intermediate steps.
