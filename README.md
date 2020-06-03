# jgu-panopto-video-downloader
Download videos from JGU Panopto platform video.uni-mainz.de

# How To
Just open the video you want to download, copy paste the contents of downloader.js (or from the code block under this paragraph) into your browser console and hit enter.
A new tab should be opened with the .mp4 file in the address bar. Just right click and then "Save video".
Done.

# Le code
```javascript
javascript:(function()
	{
	if(window.location.href.indexOf("video.uni-mainz.de/") < 1) 
	{ 
		alert("No Panopto video detected!"); 
		exit(); 
	}
	var metas = document.getElementsByTagName('meta'); 
	for (var i=0; i<metas.length; i++) 
		if (metas[i].getAttribute("name") == "twitter:player:stream") 
		{ 
			console.log(metas[i].getAttribute("content"));
			window.open(metas[i].getAttribute("content").split('?')[0]);
		} 
	}
)();
```
