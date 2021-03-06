=== Paid Memberships Pro - Subscription Delays Add On ===
Contributors: strangerstudios
Tags: paid memberships pro, pmpro, memberships, ecommerce
Requires at least: 3.5
Tested up to: 4.9.5
Stable tag: .4.5

Adds a "delay" field to PMPro membership levels and discount codes, allowing you to set a variable-length period between your initial payment (if required) and recurring subscription payment.

== Description ==
This plugin requires Paid Memberships Pro to function.

Adds a "delay" field to PMPro membership levels and discount codes, allowing you to set a variable-length period between your initial payment (if required) and recurring subscription payment.

Set "delay" to be:
- a number of days (i.e. 7 for 1 week trial)
- a specific date (i.e. 2015-01-01)
- a date calculated based on signup (i.e. Y2-01-01 or Y1-M2-01)

== Installation ==

1. Upload the `pmpro-subscription-delays` directory to the `/wp-content/plugins/` directory of your site.
1. Activate the plugin through the 'Plugins' menu in WordPress.
1. That's it. No settings.

== Changelog ==
= .4.5 =
* BUG: Didn't handle the documented M/Y variables (M1 & Y1)

= .4.4 =
* BUG: The 1 period free trial bug was still happening in some cases with discount codes with delays set on them.

= .4.3 =
* BUG: Fixed issue with Authorize.net where the user would get an additional 1 period trial after the subscription delay. (Thanks, mobilizedcloud)
* ENHANCEMENT: Added pmprosd_getDelay($level_id, $code_id) helper function.

= .4.2 =
* BUG: Fixed incorrect level cost text

= .4.1 =
* Fixed level cost text when specified dates are used. (Thanks, russell77)
* BUG: Now correctly checking for and replacing "M", "Y", etc. in subscription delays.

= .4 =
* Using current_time('timestamp') to improve accuracy of dates and times generated.
* Keeping track of a "pmprosd_trialing_until" value after checkout and filter pmpro_next_payment to use that value if it is sooner than the calculated next payment date.

= .3.3 =
* Added pmprosd_modify_start_date filter to change the start_date generated by the plugin. Passes $start_date, $order, $subscription_delay. (Thanks, Thomas Sjolshagen)
* Using esc_sql function.
* Removed the code that would set TrialBillingCycles to 0 if a subscription delay was set. Be sure to update your level settings and delays to account for this.

= .3.2.2 =
* Fixed grammar when costs are wrapped in <strong> tags. So "The price for membership is $2.00 per Month. after your 14 day trial." is now "The price for membership is $2.00 per Month after your 14 day trial.".

= .3.2.1 =
* Fixed a warning.

= .3.2 =
* Just removed the "edited" from the name.

= .3.1 =
* Fixed bug where specific date delays were showing up as integers (e.g. 2015-01-01 would become just 2015) on the edit levels page.

= .3 =
* Added ability to set a specific date for the delay. Use format YYYY-MM-DD and the plugin will calculate the # of days until that date and use that for the delay value.

= .2 =
* Now adds delay box to basic levels as well as discount codes.
* Adds "after your X day trial" to the end of the level cost text.