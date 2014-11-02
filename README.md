# Gallery Slider#

This jQuery plugin will transform all of your WordPress galleries into fully responsive sliders!

## Getting Started ##

1. Add the JavaScript file to the js folder (make it if it doesn't exist already) inside your theme directory.
2. Enqueue the script with the folowing code inside functions.php: 

``` js
wp_enqueue_script(
    'galleryslider', //handle
    get_template_directory_uri() . '/js/galleryslider.js', //source
    array( 'jquery', 'plugins' ), //dependencies
    null, // version number
    true //load in footer
);
```

3. Add the following code to your functions.php file:

``` php
remove_shortcode('gallery');
add_shortcode('gallery', 'custom_size_gallery');

function custom_size_gallery($attr) {
    // Change size here - medium, large, full
    $attr['size'] = 'large';
    return gallery_shortcode($attr);
}
```

## Dependencies ##

- [jQuery](http://www.jquery.com) - This should already be part of your WordPress theme unless you've removed it.
- [Font Awesome](http://fortawesome.github.io/Font-Awesome/) - Because it's awesome!

## Styling ##

The slider can be styled with CSS. Since the default styles are inline styles, you'll likely need to add `!important` to your rules to override them.