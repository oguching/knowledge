Plugins  
WordPress plugins are programs that add functionality to a WordPress site using WordPress API. Plugins can be written in PHP and JavaScript.  

Plugins are detected automatically from the `wp-content/plugins` directory within your WordPress installation directory.

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

Taxonomy  
Think of a Taxonomy as a type of categorizing feature that is completely custom. WordPress already includes Categories and Tag support by default but developers can create custom taxonomies to extend their themes or plugins even further.
* [Taxonomy - WordPress](https://codex.wordpress.org/Taxonomies)  

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
