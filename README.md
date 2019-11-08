# WP Simple Google Analytics
Simple Google Analytics implementation for Wordpress that avoids using cookies and external javascript.

## Configuration
Configuration is done by defining PHP constants in your /wp-config.php file. Below is an example configuration:
```php
/**
 * Google Analytics Tracking
 */
define('GOOGLE_ANALYTICS_TRACKING_ID', 'UA-NNNNNNNN-N');
define('GOOGLE_ANALYTICS_TRACK_INTERNAL_IPS', false);
define('GOOGLE_ANALYTICS_DO_NOT_TRACK_IPS',
	serialize(
		array(
			'0.0.0.0'
		)
	)
);
```
### Configuration Options
#### GOOGLE_ANALYTICS_TRACKING_ID
The Google Analytics Tracking ID you wish to use for this website.
#### GOOGLE_ANALYTICS_TRACK_INTERNAL_IPS
Whether or not internal IP addresses should be tracked. Defaults to false to avoid inflating the tracking with loopback requests. You may wish to turn this on to test your site while developing locally or if you have a proxy or CDN implemented on your website.
#### GOOGLE_ANALYTICS_DO_NOT_TRACK_IPS
Array of IPv4 addresses that will never be tracked. Useful to eliminate businesses from inflating the tracking with traffic coming from themseleves.
