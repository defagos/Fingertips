# Fingertips: Presentation mode for your iOS app

Fingertips is a small library meant for presentations from iOS devices that shows all touches and gestures so that the audience can see them. 

This is only designed for the iPad 2 and iPhone 4S (or later), which feature [hardware video mirroring](http://www.apple.com/ipad/features/airplay/) support. **This library does not do the mirroring for you!**

Just use the `fingerTipSettings` property added to `UIWindow` to access Fingertips settings. The `enabled` setting must be set to `YES` in order to make touches and gestures visible. Your app will automatically determine when an external screen is available, and will show every touch on-screen with a nice partially-transparent graphic that automatically fades out when the touch ends. 

Here's a [demo video](http://vimeo.com/22136667).

Fingertips requires iOS 5.0 or greater and ARC. 

## About this fork

This repository is a fork of the original [repository](https://github.com/mapbox/Fingertips), which turns Fingertips into a `UIWindow` category. The original Fingertips namely requires you to replace the window of your application, which is impractical if this window is already an instance of a `UIWindow` subclass, or if you do not instantiate it yourself.

Because of the use of method swizzling, it was decided not to merge back this version of Fingertips into the official repository. I will still maintain this repository as a fork, and try to merge back changes from the official repository when possible.

## Configuration

You shouldn't need to configure anything, but if you want to tweak some knobs, retrieve the `MBFingerTipSettings` instance associated with your window by accessing the `fingerTipSettings` property. The following settings are available: 

 * `enabled`: set to `YES` to enabled Fingertips (disabled by default)
 * `touchImage`: pass a `UIImage` to use for showing touches
 * `touchAlpha`: change the visible-touch alpha transparency
 * `fadeDuration`: change how long lifted touches fade out
 * `strokeColor`: change default `touchImage` stroke color (defaults to black)
 * `fillColor`: change default `touchImage` fill color (defaults to white)

## License

Copyright (c) 2011-2013 MapBox, Inc.

The Fingertips library should be accompanied by a LICENSE file. This file contains the license relevant to this distribution. If no license exists, please contact [MapBox](http://mapbox.com).