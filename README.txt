=== PrivaKey SignOn ===
Contributors: nhauslerprobaris
Tags: login, authentication, security, 2FA, mfa
Requires at least: 3.6.0
Tested up to: 4.4.1
Stable tag: 1.0.7
License: GPLv3
License URI: https://www.gnu.org/licenses/gpl-3.0-standalone.html

This plugin allows users to sign into their WordPress accounts with the authentication service PrivaKey.

== Description ==

PrivaKey (www.privakey.com) is a secure, multi-factor authentication service that acts as an alternative to
usernames and passwords. A user creates a PrivaKey account with a personal device, such as their mobile phone,
and a PIN. They can then use this account to log into any PrivaKey-enabled website.

This plugin enables users to connect their PrivaKey accounts to their WordPress accounts, so anyone who switches
can sign in with PrivaKey instead of their username & password. 

== Installation ==

Note: In order for this plugin to work with your WordPress website and allow users to sign in, you must
register as a Relying Party (RP) on PrivaKey's website. Details about this process can be found here:
https://www.privakey.com/service

1. In the WordPress administrator panel, go to "Plugins->Add New" and click "Upload Plugin". Click "Choose File"
and navigate to the folder where you have saved WPPrivaKeySignOn.zip, select it, and click "Open".
2. Once the plugin has installed, find PrivaKey in the plugins list and click "Activate".
3. Once you have registered as a Relying Party, go to "Settings->PrivaKey", input your Client ID and Secret,
and save. These values can be found on your PrivaKey administrator page.
4. Copy the the link labelled "Call Back URL" and paste it in the matching field on your PrivaKey administrator page.
5. Users should now be able to switch to PrivaKey authentication from their profile page, using the button
"Enable PrivaKey Login"

== Frequently Asked Questions ==

= I'm getting "could not retrieve a valid response" errors =
PrivaKey's servers may be temporarily unavailable, or the Relying Party settings are misconfigured. Try again
later or check the settings. Make sure the client ID, client secret, and call back URI match those shown on 
your PrivaKey administrator page.


= I've lost my PrivaKey account and can't log in with my password =

For security reasons, a user's password login is disabled when they enable PrivaKey. If you would like to revert to
password login but have lost access to your PrivaKey account, either contact an administrator and have them revert your
account manually, or follow the "Lost your password?" link to set a new password. Doing so automatically reverts
your account to password login.


== Changelog ==

= 1.0.1 =
* Popout window now runs inside wordpress core

= 1.0.2 =
* Popout now checks for 'state=privakeylogin' instead of 'privakey_login=true' in querystring

= 1.0.3 =
* Plugin no longer generates "n characters of unexpected output" warning on activation

= 1.0.4 =
* colon in state replaced with hyphen, prevents page from loading twice on newer versions of WP

= 1.0.5 =
* IDP url updated to reflect PrivaKey's domain change
* nonce no longer sent in requesttoken calls
* unix-server-compatible file paths
* error JSONs can now have no error_description field

= 1.0.6 =
* HTML in popout generated after redirect header sent

= 1.0.7 =
* Minor error-handling improvements
