# DrLunesTypeManager
ProcessWire Module Helper for Typekit´s WebFontLoader.

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

Last thing is to output code, this can be done in your "_out.php", AFTER jquery is loaded, usually in your <head>, but preferably before </body> tag.

```
<?php

// Get Module
$typekit = $modules->get('DrLunesTypeManager');
// Render Script & Settings.
echo $typekit->render();
// It´s done.
?>

```

With love.

1un.es