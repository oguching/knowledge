When choosing fonts there are three things to keep in mind: **readability**, **legibility**, and **purpose**.
Choose fonts that are conventional and easy to read. Avoid highly decorative fonts in favour of simple and practical fonts.
Also be mindful of the purpose of a font. For example, some fonts are more suited for headers rather than body text.

Pairing Fonts. Keep font pairing simple to a maximum of three different fonts. Pair fonts that contrast each other.The next step after
pairing font is setting font sizes. [Modular Scale](http://www.modularscale.com/) by is a great tool for this.

System fonts
System fonts allow for the use of native fonts on the web. So users on Windows will be served Segoe UI, Mac users will be served San Francisco and Android/Chrome OS will be served Roboto. With the work Microsoft, Apple and Google put into making their fonts legible across different sizes, system fonts are a great default.

` -apple-system, BlinkMacSystemFont, “Segoe UI”, Roboto, sans-serif `

When using system fonts, be sure to avoid shorthand declaration.

```CSS
Good
  body { 
  font-family: -apple-system, BlinkMacSystemFont, “Segoe UI”, Roboto, Helvetica, Arial, sans-serif;
}
```

```CSS
Bad 
  body { 
  font: 16px/1.2 BlinkMacSystemFont, -apple-system, “Segoe UI”, Roboto, Helvetica, Arial, sans-serif;
}
```

Resources
* [Typography can Make or Break your design](https://medium.freecodecamp.com/typography-can-make-your-design-or-break-it-7be710aadcfe)  
* [Typekit](https://typekit.com/)  
* [Google Fonts](https://fonts.google.com/)  
* [Font Squirrel](https://www.fontsquirrel.com/)  
* [Mailchimp Styleguide](https://ux.mailchimp.com/patterns)  
* [System fonts](https://booking.design/implementing-system-fonts-on-booking-com-a-lesson-learned-bdc984df627f)
