---
layout: drawpile_post
title: "Dev Update: Week 44 and 45 of 2026"
date: 2026-11-09 00:00:00 +0100
category: "devblog"
tag: "@askmeaboutloom"
---

The last two weeks had several more additions to the liquify tool as well as the transform tool.

Everything described is available [in the alpha release](https://github.com/drawpile/Drawpile/releases/tag/continuous){:target="_blank"}.

## More Liquify Features

You can now adjust a liquify's displacement using the "factor" slider. This is mostly useful for animations, where you may want to use this to create in-betweens. The factor can be applied through the menu in the tool, making whatever you set the slider to the new 100%.

Stamping a liquify is also possible now, which works like it does for transforms: putting the liquified image on the current layer, but continuing it. You can switch layers or frames afterwards. Like transforms, it only works when you're liquifying a single layer.

And in a similar vein, you can also copy, cut and paste liquifies now. As with stamping, this works for single layers.

There is also now a "reposition" option in the liquify menu, which lets you drag the position of the liquified image around.

This was suggested by BulletPepper [on Discord](https://drawpile.net/discord/){:target="_blank"}.

<video controls>
  <source src="{{ "/assets/vid/2026-11-09_liquifyfactor.mp4" | relative_url }}" type="video/mp4"/>
</video>

## Transform Pivot

Transforms now let you set a pivot point. The most obvious use for this is of course to rotate around it. Skew will also apply to it by default. Scaling will use the pivot as well if you hold the center key (Alt by default) or enable centering in the tool options.

Double-clicking the pivot point resets it to the center. You can also do this via the menu in the tool options. Here there is also the option to show and hide the pivot.

This was suggested by Aries Raenidaz, Bro, BulletPepper, GreenDyno and tiar [on Discord](https://drawpile.net/discord/){:target="_blank"}.

<video controls>
  <source src="{{ "/assets/vid/2026-11-09_pivot.mp4" | relative_url }}" type="video/mp4"/>
</video>

## Transform Copying

Just like liquifies above, you can now cut, copy and paste transforms. Pasting will bring it back in the same state as you copied it. It also only works for single layers, since there is currently no way to tell which layers the image is floating over.

<video controls>
  <source src="{{ "/assets/vid/2026-11-09_copytransform.mp4" | relative_url }}" type="video/mp4"/>
</video>

## Minor Additions and Bugfixes

Trying to transform an image to more than twice the canvas width or height now turns it into a cut and paste operation, rather than refusing to do it. This was reported by eliasa [on Discord](https://drawpile.net/discord/){:target="_blank"}. Cut and paste transforms have been optimized along the way, they no longer bother pasting parts of images that are outside of the canvas.

Drawpile now tries a bit harder to keep dppr files' creation time (also known as birth time on Linux) consistent. Like, you shouldn't actually *rely* on this, creation time can always change on a whim, but it should at least no longer change every time you save now. This was suggested by Daorf on GitHub.

Local layer and track states should now be restored properly when a dppr was spawned by saving from another dppr file. This was reported by TGS.

Drawpile now builds on FreeBSD out of the box. There was already a port of it, it just had a little patch to make it work, which was upstreamed by yurivict [on GitHub](https://github.com/drawpile/Drawpile/pull/1609){:target="_blank"}.

You can now hold Alt and use the scroll wheel to change frames in the animation timeline, as well as Ctrl+Alt and scrolling to change frames within the range. This was suggested by Ben.
