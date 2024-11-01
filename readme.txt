=== youthphotosRSS ===
Contributors: risr team (Niels Richter)
Donate link: http://blog.youthphotos.eu/de/about
Tags: photos, images, sidebar, widget, rss, youthphotos, jugendfotos, ungbild
Requires at least: 2.3.2
Tested up to: 2.6
Stable tag: 0.1.3

Allows you to integrate Youthphotos photos into your own site. It supports user-, pools- and recent-pictures.


== Description ==

This plugin allows you to easily display Youthphotos photos on your site. It supports user-, pools- and recent-pictures. The plugin is relatively easy to setup and configure via an options panel. It also has support for an image cache located on your server.


== Installation ==

1. Put youthphotos_rss.php in your plugins directory
2. If you want to cache images, create a directory and make it writable
3. Activate the plugin
4. Configure your settings via the panel in Options
5. Add the plugin via the widget management or add `<?php get_youthphotosRSS(); ?>` somewhere in your templates

If your theme doesn't support widgets use the snippets provided at [Other notes](http://wordpress.org/extend/plugins/youthphotos-rss/other_notes/)

We figured out a problem with PHP4 and UTF-8 in combination with the internal caching of Wordpress. If you run into this problem, please update to PHP5!

== Frequently Asked Questions ==

= Can I get random images from my stream? =
No, it's a limitation of using the RSS feed (it only contains the most recent photos)	

= How do I refresh the photos manually? =
The plugin uses built-in WordPress functions to update the feed. You can reload with STRG + SHIFT + R in our browser. This forces deletion of every cache.

= When I enable cache, why do just a bunch of random characters show up? =
You've probably specified the full path wrong. Double check with your host to make sure you've got it right.

= Why aren't any photos showing up? =
Sometimes it can take a little while to kick in, have patience. Youthphotos may possibly have been down. Also, make sure it works without the cache first.

= How can I user my own style =
There is a special CSS file (youthphotos_rss.css) in the youthphotos-rss plugin folder. Read and edit it. We can't give support on this.

= How do a I get borders between photos? =
You need to edit your CSS file. There are plenty of tutorials online, you may find an example in our blog.

== Advanced ==

The plugin also supports a number of parameters, allowing you to have multiple instances across your site.

1.	`$platform` - platform you are asking (www.youthphotos.eu, www.jugendfotos.de, ...)
2.	`$user` - specify a user ID
3.	`$type` - user, friends, pool, recent
4.	`$num_items` - number of items to display
5.	`$before_image` - html appearing before each photo
6.	`$after_image` - html appearing after each photo
7.	`$pool` - specify pool if you use type = pool

**Example 1**

`<?php get_youthphotosRSS("www.jugendfotos.de", 1, "user", 5); ?>`

This would return 5 pictures from the author at www.jugendfotos.de

**Example 2**

`<?php get_youthphotosRSS("www.youthphotos.eu", 1, "friends", 10); ?>`

This would show the 10 most recent pictures from the friends of the user with ID 1 at youthphotos.eu

**Example 3**

`<?php get_youthphotosRSS("www.youthphotos.eu", 1, "pool", 5, "", "", 1); ?>`

This would show the 5 most recent pictures from contest with number 1 at youthphotos.eu

**Example 4**

`<?php get_youthphotosRSS("www.jugendfotos.de", "", "recent", 10, "<span class=\"image\">", "</span>"); ?>`

This would show the most recent 10 pictures from jugendfotos.de, each picture wraped with <span class="image">picture</span>

**Full option support**

`<?php get_youthphotosRSS(get_option('youthphotosRSS_yp_platform'), get_option('youthphotosRSS_yp_id'), get_option('youthphotosRSS_display_type'), get_option('youthphotosRSS_display_numitems'), get_option('youthphotosRSS_before'), get_option('youthphotosRSS_after')); ?>`

If you have a theme which doesn't support widget, you can use this snippet of code to control the youthphotosRSS-plugin from your admin page like it's done with the widgets.

== Screenshots ==

Not available at the moment

== Feedback and Support ==

Visit the [Jugendfotos.de blog](http://blog.youthphotos.eu/de/) for help getting the plugin working. Use the comments.

== Plugin History ==

**Latest Release:** July 13, 2008

* 0.1.3 - Added default CSS
		- Added 'Full option support' to readme.txt
* 0.1.2 - Fixed problem with PHP4, UTF-8 and MagpieRSS
        - Fixed wrong handling of variables when using the functions
* 0.1.1 - Added default settings
* 0.1.0 - Initial release

== TODO ==
* Screenshots, Screencast
* Example at [blog](http://blog.youthphotos.eu/de/)

== Thanks ==

Thanks to Dave Kellam from [Eightface](http://eightface.com/) for his [flickrrss plugin](http://eightface.com/wordpress/flickrrss/). This plugin is based on it.