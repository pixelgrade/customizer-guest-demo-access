Backstage
========
**WordPress Customizer Demo Access for Everyone**

## Description

Allow your visitors to access the Customizer without logging in. This way you can showcase the customization experience as close to reality as possible.

### Secure

Everything is setup in such a way that people who are up to no good can't mess with your demo site data. We've put a lot of thought into this and we believe things are sound.

### Customizable

We know that each of us has their own design sensibilities and particular technical setup. That is why we've made it easy to integrate the plugin in a multitude of scenarios.

You can change both the frontend and the Customizer behavior of the plugin.
For the frontend, you have several options:
- For most the default HTML and CSS styling will be just fine. You can customize the button text.
- You can choose to provide your own button HTML and CSS.
- Or you can go all custom and handle the button yourself.

When it comes to the Customizer guest experience, the plugin will introduce a **Back to Demo button** (instead of the *Publish* button) and **a notification** for setting user expectations. You can customize the button text and the notification content and behavior.

### Compatible

Backstage should work with **any type of Customizer options** you have on your site:
- WordPress core controls;
- Colors and fonts controls;
- Layout and behavioral controls like content width or blog layout.

The plugin is compatible with any type of WordPress installation:
- Works with **regular, single installations;**
- Works with **Multisite setups;** you can activate the plugin **network-wide or per-blog.**

The following **limitations** are inherent to the reality of having a sandboxed Customizer:
- File uploads are not allowed; due to this, any controls that need file upload will not be allowed to be modified;
- Any time a visitor leaves the Customizer, any customization is lost and when he or she enters again, all will start clean.

### For theme authors by theme authors

The main audience of this plugin are **theme and plugin authors** that wish to showcase to potential customers the awesome customization possibilities provided by their product.

Earn that extra confidence needed for your next sale by being fully open and **letting your work speak for itself.**

**Made with love by [Pixelgrade](https://pixelgrade.com)**

## Installation

Installing "Backstage" can be done either by searching for "Backstage" via the "Plugins → Add New" screen in your WordPress dashboard, or by using the following steps:

1. Download the plugin via WordPress.org.
2. Upload the ZIP file through the _Plugins → Add New → Upload_ screen in your WordPress dashboard.
3. Activate the plugin through the _Plugins_ menu in WordPress.
4. Head over to _Appearance → Backstage_ (or _Network Settings → Backstage_ if network-wide activated) and set it up.

## Issues

If you identify any errors or have an idea for improving the plugin, please open an [issue](https://github.com/pixelgrade/backstage/issues?stage=open). We're more than excited to see what the community thinks of this little plugin, and we welcome your input!

If Github is not your thing but you are passionate about Backstage and want to help us make it better, don't hesitate to [reach us](https://pixelgrade.com/contact/).

## Getting the access URL remotely

If you want to provide your visitors with a link to access the Customizer from outside the WordPress installation, you can activate the REST API endpoint from the plugins settings. Optionally, you can secure the endpoint with a private secret key that should not be shared publicly.

You can send the following parameters to the endpoint:

```json
{
  "return_url": "https://google.com",
  "button_text": "Some text 🏀",
  "extra_query_args": {
    "autofocus[panel]": "theme_options_panel"
  },
  "secret_key": "thesecretkey"
}
```

The `secret_key` parameter is required only if you have activated it via the plugin settings.

The `extra_query_args` allow you to provide additional parameters to the Customizer URL like autofocusing on a specific panel or section, markers that you need for some custom logic you've added in the Customizer, etc. 

## Frequently Asked Questions

### Is this safe to use in production?

We believe so. To put our money where our mouth is, we use it in production on our own [demo multisite installation](https://demos.pixelgrade.com).

We've strived to close off any endpoints that WordPress uses to save things (mainly the changeset logic specific to the Customizer experience).

### Without changesets how is the experience consistent with a real scenario?

There is no point in showcasing a customization experience that is not consistent with the real one. We couldn't agree more. That is why we've studied the Customizer JavaScript logic and found ways to maintain the same results without saving anything in the database.

### When I navigate in the preview window, customizations don't get applied?

Sometimes, WordPress themes will come with custom JavaScript that will bind to _click events_ and stop their propagation. Due to this, the Customizer (not our's) logic can't catch that click and go the proper way of refreshing the preview window. We really have not way around that.

### Can I choose to hide certain Customizer sections or panels?

The plugin doesn't provide this functionality as it is quite difficult to map it to a set of configuration options. But it should be quite straight forward to code a function that "removes" panels, sections or controls when the special pseudo-guest user is logged in.

### I am a developer. Can I easily change how things work?

We are also developers (and designers, and marketers, and support people...) just like you. We know how important it is that plugins get coded in a open, thoughtful manner that is friendly towards those that have custom requirements.

The plugin provides actions and filters in all the right places allowing you introduce custom logic just about anywhere, if the need arises.

## Credits

* [CMB2](https://github.com/CMB2/CMB2) Metaboxes, custom fields library - License: GPLv2 or later
* [CMB2 Conditionals](https://github.com/jcchavezs/cmb2-conditionals/) plugin for CMB2 - License: GPLv2 or later

## Changelog

### 1.4.2
_2019-11-08_
* Prevent aggressive sanitization for custom code fields.

## 1.4.1
_2019-11-07_
* Allow POST method also for REST API endpoint.

### 1.4.0
_2019-11-06_
* Added support for injecting custom CSS and JS in the Customizer.
* Added support for UTF-8 characters in the button text.
* Added support for extra query arguments to the REST API endpoint.
* Made sure that settings data in conditionally hidden fields is persistent so you wouldn't lose you custom code.

### 1.3.0
_2019-10-08_
* Added new settings and logic for enabling a REST API endpoint to fetch the secure customizer access link.

### 1.2.0
_2019-10-07_
* Improved behaviour when working within multisite settings and the plugin is activated on a per site basis.
* Improved security checks to prevent edge-cases on multisite installations.
* Added upgrade routines for smoother plugin updates.
* Tested with WordPress 5.2.3.

### 1.1.0
_2018-12-10_
* Added frame busting when in an iframe because the Customizer doesn't play well when opened in an iframe.
* Tested with WordPress 5.0.

### 1.0
_2018-09-27_
* Initial release
