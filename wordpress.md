Just gonna put some wordpress links here.
* [Creating Custom Post Types](https://www.elegantthemes.com/blog/tips-tricks/creating-custom-post-types-in-wordpress) 
* [How to create a WordPress Plugin](https://www.elegantthemes.com/blog/tips-tricks/how-to-create-a-wordpress-plugin)
* [WordPress Post Types](https://codex.wordpress.org/Post_Types) Custom Post Type API  

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
