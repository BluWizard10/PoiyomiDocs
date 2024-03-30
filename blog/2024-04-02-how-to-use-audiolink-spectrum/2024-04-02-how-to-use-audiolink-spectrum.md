---
slug: 2024-04-02-how-to-use-audiolink-spectrum
title: 'How To Use AudioLink Spectrum in Poiyomi 9.0'
description: Learn how to use AudioLink Spectrum with Poiyomi Shaders
authors:
  bluwizard
tags: [shader, audiolink, vrchat, features]
---

Greetings y'all! My name is BluWizard, an avid VRChat Avatar, World Creator, and Docs contributor.

In this Blog post, I'm going to teach you how to use one of the most interesting AudioLink Effects that you can do with Poiyomi Shaders. The effect we're talking about is AL Spectrum! Mainly because so many of y'all have been asking me a lot on how I do it. So, I'm going to demonstrate the way I personally set up Spectrum to work with my Avatar's unique Meshes and UVs.

## The Basics

Let's first start with the basics! AudioLink Spectrum is a very unique and interesting Shader effect that emulates various visualizer-like effects that react to your music. It is projected onto the Mesh of your choice, whether that would be a flat Plane or wrapped around a 3D mesh.

The way it appears depends on how you wish for it to appear. A few examples include:

### Wavy Visualizer

### Bar Visualizer

## Setting up your UVs

:::info Blender Knowledge Recommended!
This will go over how to unwrap your UVs for use with your AL Spectrum, so here's your heads up!

If you are familiar with UV Tile Discard already, this Tutorial will feel very similar.
:::

1. Import your Model in a new Blender Project, via `File -> Import -> FBX` in the menu.
    - *If you already have a Blender file of your Avatar, use `File -> Append` to import it from another Blender project.*
2. Select the Mesh you want to add your Spectrum on.
3. On the `Properties` Sidebar, click the `Data` Tab and scroll down to `UV Maps` and expand it. You should see something like this:
4. Add a secondary UV Map by clicking the `+` button and name it. For this tutorial, we're gonna name it "ALSpectrum".
    - *Ensure this UV Map is at least __below__ the topmost one. This is important!*
5. Now, hit `Tab` on your Keyboard to go into **Edit Mode**, OR by clicking the `Object Mode` dropdown to switch to `Edit Mode` on your Mesh.
6. With your selector mode, switch to `Edge` selection mode by clicking this button.
7. Use `Shift + Left-Click` to multi-select each Edge of the area you want your Spectrum to be on. This will be it's boundaries.
    - *You can also hold `Ctrl` as you select Edges to make your selection choose the shortest path.*
8. Once you have selected the Edges you want as the boundaries of your Spectrum, click `Edge -> Mark Seam` though the Menu. This will change those Edges to a Red Color.
    - *For future reference, a Marked Seam indicates the boundaries of a UV island.*
9. Now with your selector mode, switch to `Face` selection mode by clicking this button.
10. Hover your Mouse over the area of your Mesh that is surrounded by your Marked Seams, then press `L` on your Keyboard to select the Faces. They should only select anywhere that's within the boundaries of the Seams you have marked.
11. With all those Faces selected, select the Secondary UV Map that you created, which was "ALSpectrum". With it selected, hit `U` on the Keyboard followed by `Unwrap` in the context menu.
12. Now switch over to `UV Editing` Tab. When you do, you should see that your unwrapped "ALSpectrum" Map is covering the UV area like this:
13. Select the UVs and then Rotate and Position them to where you want them to be. You would want to ensure it covers as much as the area on the bottom for your Spectrum.
14. Finally, Export your FBX as per usual and import it into Unity.
    - *If you are using an Avatar Base, please follow the guide set forth by your Avatar Creator on how to properly swap your FBXes.*

## Configuring your AL Spectrum

Now here comes the fun part!

This is where we are going to configure how the Spectrum appears on your newly-made FBX that you have created.

1. First things first, enable `AudioLink` in your Material.
2. Under `AudioLink` Category, enable `AL Spectrum`.
3. Since you unwrapped a secondary UV, you are going to select the `UV` to be `UV1` instead of `UV0`.
4. Enter Play Mode to test AudioLink. If you are seeing this, it means you have configured things correctly. Congratulations!

Now that we got that sorted, let's go over what you can do here while we are in play mode.