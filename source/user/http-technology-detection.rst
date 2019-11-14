HTTP Technology Detection
=========================

If you want to know which technologies are in use by a web site, you can use the
habu.http.tech command, like this:

::

   $ habu.http.tech https://woocommerce.com
   Google Tag Manager       unknown
   MySQL                    unknown
   Nginx                    unknown
   PHP                      unknown
   Prototype                unknown
   RequireJS                unknown
   WooCommerce              3.8.0
   WordPress                5.2.4
   Yoast SEO                10.0.1


This command only makes one HTTP request, so it's very stealthy.

The database used to detect the technologies it's the 'apps.json' file, by the
Wappalyzer project (https://www.wappalyzer.com).


How Was Detected Each Technology?
---------------------------------

If you want to know that, use the '-v' or '--verbose' option, and the information
will be shown, like in the following example:

::

   $ habu.http.tech -v https://woocommerce.com
   Google Tag Manager detected by HTML body with regex googletagmanager\.com/ns\.html[^>]+></iframe>
   Nginx detected by Server HTTP header = nginx
   Prototype detected by HTML body with regex (?:prototype|protoaculous)(?:-([\d.]*[\d]))?.*\.js
   RequireJS detected by HTML body with regex require.*\.js
   WooCommerce detected by meta generator tag with regex WooCommerce ([\d.]+)
   WordPress detected by link HTTP header = <https://woocommerce.com/wp-json/>; rel="https://api.w.org/"
   WordPress detected by HTML body with regex /wp-(?:content|includes)/
   WordPress detected by HTML body with regex <link[^>]+s\d+\.wp\.com
   WordPress detected by meta generator tag with regex ^WordPress ?([\d.]+)?
   WordPress VIP detected by x-powered-by HTTP header = WordPress.com VIP <https://wpvip.com>
   Yoast SEO detected by HTML body with regex <!-- This site is optimized with the Yoast (?:WordPress )?SEO plugin v([\d.]+) -
   WordPress detected because implied by WooCommerce
   PHP detected because implied by WordPress
   MySQL detected because implied by WordPress
   WordPress detected because implied by WordPress VIP
   WordPress detected because implied by Yoast SEO
   Google Tag Manager       unknown
   MySQL                    unknown
   Nginx                    unknown
   PHP                      unknown
   Prototype                unknown
   RequireJS                unknown
   WooCommerce              3.8.0
   WordPress                5.2.4
   WordPress VIP            unknown
   Yoast SEO                10.0.1


Cache
-----

By default, the command uses a requests cache, to no send repeated HTTP requests.

If you want to disable the cache, use the option '--no-cache'.


