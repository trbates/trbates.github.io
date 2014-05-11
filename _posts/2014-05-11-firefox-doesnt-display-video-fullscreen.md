---
layout: post
title:  "Firefox doesn't display video fullscreen"
categories: 
---

Firefox doesn't display video fullscreen if parent has transform-style.
------

Found this interesting bug in Firefox the other day when working with the HTML5 video tag.
[http://stackoverflow.com/questions/13788233/firefox-doesnt-display-flash-if-inside-transform-stylepreserve-3d](http://stackoverflow.com/questions/13788233/firefox-doesnt-display-flash-if-inside-transform-stylepreserve-3d) and the bug report contained therein [https://bugzilla.mozilla.org/show_bug.cgi?id=819763](https://bugzilla.mozilla.org/show_bug.cgi?id=819763) .

Nest the video tag inside a parent that has the CSS transform-style attribute applied.  The video will play, but when you decide to go fullscreen you'll be presented with an undesirable experience.

~~~ html
<html>
	<body>
		<div style="transform-style: preserve-3d;">
			<video controls="" preload="none">
				<source src="http://videos-cdn.mozilla.net/serv/webmademovies/Moz_Doc_0329_GetInvolved_ST.webm" type="video/webm">
			</video>
		</div>
	</body>
</html>
~~~

My specific scenario wasn't exactly worded the way its in the Stackoverflow question or the bug report, but I could recreate the issue by applying transform-style: preserve-3d to a parent element.

I ultimately decided on a javascript enhanced hack to workaround this issue.  For Firefox, I removed the controls from the video and added a "Fullscreen" button next to the video.  When the user clicks the new fullscreen button I clone the video element out to the body and request fullscreen on the cloned element.