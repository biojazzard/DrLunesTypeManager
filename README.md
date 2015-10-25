# DrLunesTypeManager
ProcessWire Module Helper for Typekit´s WebFontLoader.

DrLunesTypeManager is a Template Helper.

DrLunesTypeManager asks you for a typekit ID, Google Fonts Family, CDN, Custom CSS and more, and outputs the code needed to use this fonts in your templates. It also forces some tags to use this fonts and your custom CSS styles to be applied to the page.

## Inspiration

Inspired by [Dr. Rober´s](rober@1un.es) needs. 
	
ProcessWire is about efficient code, but sometimes humans need helpers.

## Install Via PW:

+ Download zip
+ Use modules administrator in PW to upload it to the server.
+ Open it and configure it with your settings.

## Install Via GIT:
I´m not a git pro, but it´s nice to have modules as a subtree so it´s not a pain to mantain, and you can easily reuse it in other projects keeping it´s development in github as well.

+ Fork [DrLunesTypeManager](git@github.com:biojazzard/DrLunesTypeManager.git)
+ Ad it as a subtree in git with relative path site/modules/
+ Edit it as you like.
+ Install DrLunesTypeManager with modules administrator in PW.
+ Open it and configure it with your settings.

## Using DrLunesTypeManager in templates.


Last thing is to output code, this can be done in your:
``$config->appendTemplateFile``

+ DrLunesTypeManager uses jQuery.

So output code AFTER **jQuery** is loaded, usually in your ``head``, but preferably before ``body`` tag.

```php
<?php

// Get Module
$typekit = $modules->get('DrLunesTypeManager');
// Render Script & Settings.
echo $typekit->render();
// It´s done.
?>

```

## html outout

MODULE-VALUE-* represents your value settings in Module´s Settings

```html

...
<script>
  WebFontConfig = {
    typekit: { id: "MODULE-VALUE-TYPEKIT-ID" },
    google: {
        families: ["MODULE-VALUE-GOOGLE-FONT"]
    }
  };
  (function() {
      var wf = document.createElement("script");
      wf.src = ("https:" == document.location.protocol ? "https" : "http") + ":MODULE-VALUE-TYPEKIT-CDN";
      wf.async = "true";
      var s = document.getElementsByTagName("script")[0];
      s.parentNode.insertBefore(wf, s);
  })();
	
	// TypeKit Classes added to main text tags

  (function($) {
    $("p").addClass("MODULE-VALUE-BODY-CLASS")
    $("ul").addClass("MODULE-VALUE-BODY-CLASS")
    $("h1, h2, h3").addClass("MODULE-VALUE-H13-CLASS")
    $("h4, h5, h6").addClass("MODULE-VALUE-H46-CLASS")
  })(jQuery);

</script>

```

If you are using the **Custom CSS** field, you may add ``!important`` in order to get this styles loaded as expected:

```css
h1.tk-cubano {
  letter-spacing: -1px;
  color: hsla(360, 94%, 32%, 0.76) !important; // FORCE RED
  text-shadow: 1px 1px 3px hsla(360, 94%, 32%, 0.3); //SHADOW
}
```


With love.

1un.es