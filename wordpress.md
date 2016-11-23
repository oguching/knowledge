Plugins  
WordPress plugins are programs that add functionality to a WordPress site using WordPress API. Plugins can be written in PHP and JavaScript.  

Suggested Folder Structure  
* wp-plugin-name
  * wp-plugin-name.php - main plugin class.
  * readme.txt – optional, describes the plugin for use in the wordpress.org plugin directory.
  * post-types/ – define each post type separately in this directory.
    * custom-post-type.php – each post type is defined separately.
  * templates/ – all of your admin side templates.
    * custom-post-type-inner-metabox.php – every custom post type that your plugin defines will need a inner-metabox template this keeps your presentation logic out of your business logic.
    * settings.php – this is the plugin settings page template.
  
Plugins are detected automatically from the `wp-content/plugins` directory within your WordPress installation directory. Plugins will be on inactive status by default. We can click on the `activate` link to activate the plugin. Once the plugin is successfully activated, its features will get effected to your website.   

* [How to write a WordPress Plugin](http://www.yaconiello.com/blog/how-to-write-wordpress-plugin/)

`wp_enqueue_script` is used to include scripts into an HTML document. It is the recommended practice. Some developers inline styles using `echo` this practice is not recommended. We also add styles with `wp_enqueue_script`.   
`wp_enqueue_script()` functions requires at least two parameters: the _name_ of the script and the _URL_ to it.  
For example: `wp_enqueue_script('test', plugin_dir_url(__FILE__) . 'test.js');`

Three additional parameters lets you have more control on the way your script will be included, especially the last parameter which is a boolean: by default, this boolean is set to `false` and your script will be included in the `head` tag, but if you set it to `true`, then your script will be included in the footer.

The fourth parameter is useful if you make various versions of your script: it is a string containing the version number which will be concatented to the end of the URL. Adding a version number ensures that visitors will get the right version of your script regardless of caching.

The third parameter let's you indicate dependencies for your script For example, if your script needs jQuery, you can use this parameter.

```php 
  wp_enqueue_script('test', plugin_dir_url(__FILE__) . 'test.js', array('jquery')); 
```

Dependencies must be indicated into an array, even if there is only one dependency. The name that you indicate into this array is the name of a script registered thanks to a second function: `wp_register_script()`

Adding JavaScript

```php
  add_actions('wp_enqueue_scripts', 'fwd_scripts');
  function fwds_scripts()
  {
    wp_enqueue_script('jquery');
    
    wp_register_script('slidesjs_core', plugins_url('js/jquery.slides.min.js',__FILE__), array("jquery"));
    
    wp_enqueue_script('slidesjs_core');
  }
```

jQuery comes installed with WordPress so we don't need to register it, we just add it. jQuery.slides does not come with WordPress so we have to register it before we can add it to our pages.

Adding Styles

```php
 add_action('wp-enqueue_scripts', 'fwds_styles');
 function fwds_styles()
 {
   wp_register_style('slidesjs_example', plugins_url('css/example.css', __FILE__));
   wp_enqueue_style('slidesjs_example');
 }
```

Hooks  
In programming,initialisation of data is important as it's where we setup the prerequisites for the application such as its attributes, its required files and data, its connection to the database, and so on. WordPress has a lot of `hooks` that you can attach a function to. 

```php
  add_action('wp_head', 'my_facebook_tags');
  
  function my_facebook_tags()
  {
    echo "I am in the head section";
  }
```

In the code above, `wp-head` is a hook and it has the `my_facebook_tags()` function attached to it, so the function runs in the head section of all WordPress pages.

The `init` hook
* WordPress recommends the use of `init` hook for **registering new custom post types**.
* **Plugin configurations and settings** need to be defined in each and every request and hence its a good practice to include them inside this hook.
* We can intercept user submitted data (using $_GET and $_POST) without any actions, but it's recommended to use the `init` hooks as it guarantees the execution in each request.
* We can define new rewrite rules using the `init` hook, but keep in mind that these rules will only take effect once we flush the rewrite rules.
* Plugins contain many **custom actions** for extending the functionality. There will be scenarios where we need to add new custom actions as well as remove existing ones. In such occasions, it's essential to implement those activities within `init` hook.
* WordPress offers multi-language support and thus we are allowed to load the file containing the translated string. This should also be placed inside the `init` hook.


There are two types of hooks, `actions` and `filters`. 

Actions  
Actions run whenever WordPress detects the hook that calls them.

* [WordPress Hooks](https://premium.wpmudev.org/blog/wordpress-hooks/)
* [WordPress Plugin Development - Wpmudev](https://premium.wpmudev.org/blog/wordpress-plugin-development-guide/)
* [WordPress Initialisation hooks benefits](https://code.tutsplus.com/articles/wordpress-initialization-hooks-benefits-and-common-mistakes--wp-34427)


Just gonna put some wordpress links here.
* [Creating Custom Post Types](https://www.elegantthemes.com/blog/tips-tricks/creating-custom-post-types-in-wordpress) 
* [How to create a WordPress Plugin](https://www.elegantthemes.com/blog/tips-tricks/how-to-create-a-wordpress-plugin)
* [WordPress Post Types](https://codex.wordpress.org/Post_Types) Custom Post Type API  
* [WordPress Theme files and what they do](https://www.doitwithwp.com/rundown-wordpress-theme-files-what-they-do/)

Shortcodes  
Shortcodes inject content into a WordPress site/page using square `([])` brackets. We instruct WordPress to find the macro that is in square brackets and replace it with the appropriate dynamic content, which is produced by a PHP function.

The creation process involves the following steps:
1. Create the function, which will be called by WordPress when it finds a shortcode.
2. Register the shortcode by setting a unique name.
3. Tie the registration function to a WordPress action.

* [Complete guide to shortcodes](https://www.smashingmagazine.com/2012/05/wordpress-shortcodes-complete-guide/)

Taxonomy  
Think of a Taxonomy as a type of categorizing feature that is completely custom. WordPress already includes Categories and Tag support by default but developers can create custom taxonomies to extend their themes or plugins even further.
* [Taxonomy - WordPress](https://codex.wordpress.org/Taxonomies)  

Ajax  
In WordPress, all Ajax requests are sent to `admin-ajax.php` for processing.

Child Themes       
Child themes are the recommended way to customise an existing theme. It inherits the functionality and styling of it's parent theme. The only file required for the Child theme is `style.css`. However it must be specially formatted with the `Template` value matching the parent filename in `wp-content/themes`.

```css

  /***
   *** Theme Name: Child Theme Name
   *** Description: Description of your Child Theme
   *** Author: Your name here
   *** Template: folder
   ***
   ***/
```
WordPress looks to the child theme folder first before the parent theme. You can override the parent theme functionality with these files. You can even have an `index.php` file in your child theme folder and it will override the parent's.  
* [Child Theme - WordPress](https://codex.wordpress.org/Child_Themes)  
* [Creating a Child Theme for Customizr](http://docs.presscustomizr.com/article/24-creating-a-child-theme-for-customizr)  
* [How to create modify and utilise child themes](https://www.doitwithwp.com/what-why-how-child-themes-wordpress/)
* [How to modify the parent theme behaviour within the child theme](https://code.tutsplus.com/articles/how-to-modify-the-parent-theme-behavior-within-the-child-theme--wp-31006)  

Who to follow
* [Carl Alexander](https://carlalexander.ca)
* [Hugh Lashbrooke](https://hughlashbrooke.com/)
