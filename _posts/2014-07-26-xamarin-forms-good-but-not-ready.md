---
layout: post
title:  "Xamarin.Forms good but not ready"
categories: 
---

Xamarin's new Xamarin.Forms are almost there
------

I was recently had the opportunity to evaluate the new [Xamarin.Forms](http://xamarin.com/forms) (1.2.1.6229) technology.

Xamarin has started something that has tremendous potential, but I don't think you should switch to Xamarin.Forms just yet.  The potential to construct your UIs using code or XAML and when that code is then compiled to each platform with platform-specific native UI elements is huge.  The general idea is that your development is independent of the target platform.  Within in Xamarin.Forms the platform-specific [Renderers](http://developer.xamarin.com/guides/cross-platform/xamarin-forms/custom-renderer/) take on the task of choosing which UI element to draw on the screen.

The following bad parts are reasons I believe Xamarin.Forms is not ready, but hope they will have addressed in future releases.

####Lack of documentation

Likely your first roadblock will end up being the nearly absent documentation or examples showing you how to create your UI with XAML.  Most of the useful samples you find are examples of how to use C# code to create your UI, but not XAML.  When Microsoft introduced XAML for WPF, I wasn't really enamoured with it then and documentation seemed to be sparse then too.

To Xamarin's credit, they are working to close that gap by posting samples of Xamarin.Forms usage to Github.  Their [repository](https://github.com/xamarin/xamarin-forms-samples) contains some straight forward examples to help you work through the top-level concepts.  Unfortunately, their GitHub repo highlights my next bad point.

####Custom Renderers are required

Custom Renderers are the answer for a lot of the "why doesn't this work" in Xamarin.Forms. 

Want to change the color of the Navigation Bar?
*Use a custom renderer.*

Want to change the background color of the MasterDetailPage seperator?
*Use a custom renderer.*

Background color of a input element?
*Yep, custom renderer.*

Alternate styles on a table element or list element?
*That's right, use a custom renderer.*

Indeed the examples above are for adjusting color or style of an element.  Yes these are trivial, but these aren't things I would expect to have to write platform specific code to handle.  It should be this cross-platform UI toolkit's responsibility that I've just invested in to expose common appearance customizations like background color.   This sort of developer friendly detail seems like an obvious oversight.

I see Xamarin.Forms as Xamarin’s answer to mobile development solutions like Cordova.  Cordova simplifies the mobile app development process across multiple platforms by enabling your developers to utilize their existing HTML, Javascript and CSS skillsets.    This is Xamarin’s first steps into living the dream of developing your UI, application logic and business rules layers once and have it all executed on multiple mobile platforms.  I don’t believe the story of Xamarin.Forms is over and I’ll continue to watch their progress.  I’m excited to see Xamarin products and eager to see what the future holds.