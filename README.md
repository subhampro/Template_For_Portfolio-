# CreativeSpace - Modern Portfolio Website

Live Preview : https://codepen.io/SubhamPRO-isLive/pen/NPWOJad

A beautiful and modern portfolio website template with interactive features and responsive design.

## Features

- Responsive design that works on all devices
- Modern UI with smooth animations and transitions
- Interactive portfolio filtering
- Testimonial slider
- Contact form with validation
- Smooth scrolling navigation
- Clean and well-commented code

## Technologies Used

- HTML5
- CSS3 (with modern features like flexbox, grid, and animations)
- JavaScript (vanilla JS with no frameworks)
- Font Awesome icons

## How to Use

1. Simply open the `index.html` file in your web browser to view the website.
2. Customize the content in the HTML file to add your own information.
3. Modify the styles in `styles.css` to change colors, fonts, and layout as needed.
4. Update the JavaScript functionality in `script.js` if you need additional features.

## Customization Tips

### Changing Colors

The color scheme can be easily changed by modifying the CSS variables in the `:root` selector in styles.css:

```css
:root {
    --primary-color: #6C63FF;
    --secondary-color: #4A42FC;
    --accent-color: #FF6584;
    --dark-color: #2A2A2A;
    --light-color: #FFFFFF;
    --gray-color: #F5F5F5;
    --text-color: #444444;
}
```

### Adding Your Portfolio Projects

To add new portfolio items, duplicate the existing portfolio item structure in the HTML and update with your own content:

```html
<div class="portfolio-item" data-category="your-category">
    <div class="portfolio-img"></div>
    <div class="portfolio-info">
        <h3>Your Project Title</h3>
        <p>Category</p>
        <a href="#" class="portfolio-link"><i class="fas fa-link"></i></a>
    </div>
</div>
```

Then add your project image by updating the CSS for that specific portfolio item.

## Credits

- Font Awesome for icons
- Google Fonts for typography
- Placeholder.com for placeholder images

## License

This template is free to use for both personal and commercial projects. Attribution is appreciated but not required.

---

Created with ❤️ by SubhamPRO
