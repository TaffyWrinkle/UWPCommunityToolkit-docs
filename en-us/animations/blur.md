---
permalink: /en-US/animations/blur.htm
title: Blur XAML and Code Animation 
description: The Blur animation behavior allows for blurring of XAML elements using composition
keywords: windows, app, toolkit, Blur, animation behavior, XAML behavior, image blur, XAML blur, XAML, animation, composition 
layout: api
search.product: eADQiWindows 10XVcnh
lang: en-us
---

# Blur

The **Blur animation behavior** selectively blurs a XAML element by increasing or decreasing pixel size.
Sometimes you want an element to appear slightly out of focus, but to be familiar to the user from other locations within an app.  Rather than having to rasterize the XAML into an image and apply a blur, you can apply a BlurBehavior to the original element at run time. 

## Syntax

You can either use the blur behavior from your XAML code:

{% highlight xml %}

    <interactivity:Interaction.Behaviors>
    <behaviors:Blur x:Name="BlurBehavior" 
           Value="10" 
           Duration="10" 
           Delay="0" 
           AutomaticallyStart="True"/>
    </interactivity:Interaction.Behaviors>

{% endhighlight %}

or directly from code:

{% highlight csharp %}

ToolkitLogo.Blur(value: 10, duration: 10, delay: 0);       

{% endhighlight %}

Behavior animations can also be chained and awaited.

{% highlight csharp %}

    Element.Rotate(value: 30f, duration: 0.3).StartAsync();

    await Element.Rotate(value: 30f, duration: 0.3).StartAsync();

    var anim = element.Rotate(30f).Fade(0.5).Blur(5);
    anim.SetDurationForAll(2);
    anim.Completed += animation_completed;
    anim.StartAsync();

    anim.Stop();

{% endhighlight %}

[Blur Behavior Sample Page Source](https://github.com/Microsoft/UWPCommunityToolkit/tree/master/Microsoft.Toolkit.Uwp.SampleApp/SamplePages/Blur)

Please view the [toolkit sample application](https://github.com/Microsoft/UWPCommunityToolkit/tree/master/Microsoft.Toolkit.Uwp.SampleApp) for the UWP Community Toolkit for current samples and example code.

## Example Image

![Blur Behavior animation]({{site.baseurl}}/resources/images/Animations-Blur.gif "Blur Behavior")

## Requirements (Windows 10 Device Family)

| [Device family](http://go.microsoft.com/fwlink/p/?LinkID=526370) | Universal, [Windows 10 Anniversary SDK 14393](https://blogs.windows.com/windowsexperience/2016/07/18/build14393/) 10.0.14393.0 |
| Namespace | Microsoft.Toolkit.Uwp.UI.Animations |

## API

* [Blur source code](https://github.com/Microsoft/UWPCommunityToolkit/blob/master/Microsoft.Toolkit.Uwp.UI.Animations/Behaviors/Blur.cs)
* [Blur Behavior API documentation]({{site.baseurl}}/{{page.lang}}/api/Microsoft_Toolkit_Uwp_UI_Animations_Behaviors_Blur.htm)
* [Blur Code API documentation]({{site.baseurl}}/{{page.lang}}/api/Microsoft_Toolkit_Uwp_UI_Animations_Composition.htm#blurmicrosofttoolkituwpuianimationsanimationset-animationsetsystemdouble-durationsystemdouble-delaysystemdouble-bluramount.htm)
