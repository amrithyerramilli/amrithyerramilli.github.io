---
layout: post
description: Quick hack to turn your web apps into mobile apps
image:
  feature: ay-web-app.jpg
  credit: 
  creditlink: 
tags:
  - UI
  - UX
  - Web Technology
  - Chrome
  - Open Web
  - Mobile App

comments: true
share: true
modified: "2016-01-25 02:20 +0530"
title: Add to Home screen
---
Over the last couple of hours, I hacked my way into creating an _**"app"**_ out of my website.

A couple of hours and I can make an app out of my existing website ? :smirk:

Alright, you got me. I didn't really _make an app_.

There's this nifty little feature called **Add to Home screen** on most mobile browsers. [Chrome for Android](https://play.google.com/store/apps/details?id=com.android.chrome) takes this a notch higher and lets you give a _native_ look and feel to your web app.

## What is this sorcery?

Quite simple actually, you just create a _manifest_ (a file representing a certain configuration) and add a simple HTML link tag in your web app.

### Linking to the manifest

To associate the manifest with your website, include the link element in your web page (for example, index.html):

{% highlight html %}
<link rel="manifest" href="manifest.json">
{% endhighlight %}

### The manifest metadata

>
The manifest metadata can define a title, landing page, default orientation, and different icons depending on size and screen density. The display represents how developers would like the user agent to present the web application to a user (for example, in fullscreen).

{% highlight json %}
{
	"name": "Amrith Yerramilli | all in",
	"short_name": "AY | all in",
	"icons": [
		{
			"src": "\/images\/icons\/android-chrome-36x36.png",
			"sizes": "36x36",
			"type": "image\/png",
			"density": 0.75
		},
		{
			"src": "\/images\/icons\/android-chrome-48x48.png",
			"sizes": "48x48",
			"type": "image\/png",
			"density": 1
		},
		{
			"src": "\/images\/icons\/android-chrome-72x72.png",
			"sizes": "72x72",
			"density": 1.5
		},
		{
			"src": "\/images\/icons\/android-chrome-96x96.png",
			"sizes": "96x96",
			"type": "image\/png",
			"density": 2
		},
		{
			"src": "\/images\/icons\/android-chrome-144x144.png",
			"sizes": "144x144",
			"type": "image\/png",
			"density": 3
		}
	],
	"start_url": "https:\/\/amrithyerramilli.github.io",
	"display": "standalone"
}

{% endhighlight%}

And voilà, my website is now a mobile application. Well, sort of.

I was pleasntly surprised that it loaded a decent splash screen with my site icon and title.

Obviously there are a **lot** of limitations to this and duh, it is currently only for Chrome on Android. Apple has their own spec for creating these _native-ish_ web apps. What's funny is this doesn't even work with Chrome on iOS :unamused:.

## But why do this?

>
Nowadays, the primary gaps between native and web is not so much technological. It’s user experience. Users simply love installing apps, which live snugly on the homescreen (or the desktop) waiting to be tickled into life with the tap of a finger or the click of a mouse.
In browser land, we are still fumbling around trying to find opened tabs and having to type long and boring URLs to get anything done.

---

Go ahead, add my site to your homescreen (those of you who use Chrome for Android) and see for yourself.

<img src="https://developer.chrome.com/multidevice/images/home_add.png" alt="Add to home screen" style="max-height: 400px" />

##### More info and references :

- [Configuring Web Applications](https://developer.apple.com/library/ios/documentation/AppleApplications/Reference/SafariWebContent/ConfiguringWebApplications/ConfiguringWebApplications.html) in Safari/iOS
- [Add to Homescreen](https://developer.chrome.com/multidevice/android/installtohomescreen) in [Chrome for Android](https://play.google.com/store/apps/details?id=com.android.chrome)
- [Html5Doctor](http://html5doctor.com/web-manifest-specification/)
- [MDN](https://developer.mozilla.org/en-US/docs/Web/Manifest)