# WPSocialite

This plugin adds the SocialiteJS Functionailty (Developed by David Bushell[http://dbushell.com/]) to Wordpress. Original readme is as follows:

### Because if you're selling your soul, you may as well do it asynchronously.

Socialite provides a very easy way to implement and activate a plethora of social sharing buttons — any time you wish. On document load, on article hover, on any event!

[For a demo visit: **socialitejs.com**](http://www.socialitejs.com/)

Author: David Bushell [http://dbushell.com](http://dbushell.com/) [@dbushell](http://twitter.com/dbushell/)

Copyright © 2012

## Features and Benefits

* No dependencies to use.</li>
* Loads external resources only when needed.
* Less than 2kb when minified and compressed.
* More accessible and styleable defaults/fallbacks.
* Support for Twitter, Google+, Facebook, LinkedIn, Pinterest, and Spotify.
* Extensible with other social networks.
* Mimics native implementation when activated.
* Supported in all browsers (providing the buttons are).

## Setup

Create an element with the class `socialite` and a class like `twitter` to specify the social network. Best practice is to provide an accessible fallback URL like the example below. You can style it however you like! See [http://socialitejs.com](http://socialitejs.com) for demos.

	<a class="socialite twitter" href="http://twitter.com/share" data-url="http://socialitejs.com">
		Share on Twitter
	</a>

Use `data-*` attributes to configure your button. These configurations directly correlate to the individual network implementations, so while Twitter uses `data-url`, Facebook uses `data-href`. Not ideal but I'd rather keep this script very small!

Supported network classes are currently: `twitter`, `googleplus`, `facebook`, `linkedin`, `pinit`, and `spotify-play`. For other [Twitter buttons](https://twitter.com/about/resources/) add an extra class of either `follow`, `hashtag` or `mention`. For [Embedded Tweets](https://dev.twitter.com/docs/embedded-tweets) copy the `<blockquote>` code provided by Twitter and replace the class attribute with `socialite tweet`.

For all individual button configurations visit [Twitter](https://twitter.com/about/resources/buttons/), [Google+](https://developers.google.com/+/plugins/+1button/), [Facebook](http://developers.facebook.com/docs/reference/plugins/like/), [LinkedIn](http://developer.linkedin.com/plugins/share-button/), [Pinterest](http://pinterest.com/about/goodies/), and [Spotify](https://developer.spotify.com/technologies/spotify-play-button/). **Important:** don't include the scripts provided by these networks, Socialite does that for you!

Include **socialite.js** right at the end of your document (before `</body>`) and activate with the options below.

***Please note:*** you can easily edit socialite.js to remove the social networks you don't need.

### Pinterest

For Pinterest's "Pin it" buttons the `url`, `media` and `description` are appended to the URL query string rather than as `data-*` attributes. The only configuration option is `data-count-layout="horizontal"` (or "vertical").

### Spotify

For the Spotify Play Button simply link to the song or playlist like so:

	<a class="socialite spotify-play" href="http://open.spotify.com/track/2EZ2KXLqs9zdRVVMMz1IsH" data-theme="black" data-width="500" data-height="80" target="_blank" title="Sexy And I Know It">
		Listen to <em>Sexy And I Know It</em> by <strong>LMFAO</strong> on Spotify
	</a>

## Functions

### Load

	Socialite.load();

`load` will search the document for elements with the class `socialite` and magically transform them into sharing buttons (based on a network class and data-* attributes).

Always wait for at least the `DOMContentLoaded` event — `$(document).ready(function() { });` with jQuery.

	Socialite.load(context);

Be kind! Provide an element to search within using `context` rather than the whole document.

### Activate

	Socialite.activate(element, 'network');

`activate` replaces a single element (or an array of) with the specific social network button.

### Extend

	Socialite.extend('network', function);

With `extend` you can add more social networks! The `function` is called by `Socialite.load` and `Socialite.activate` to replace the default element with the shiny sharing button.

## Contribute

Send me feedback and testing issues!
