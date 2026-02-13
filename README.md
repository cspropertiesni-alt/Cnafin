# CNA Financial Planning - Website Package

## Overview
This is a complete 5-page website for CNA Financial Planning, a financial wellbeing and mortgage advisory business. The website is ready to deploy to any standard web hosting service.

## Package Contents

### Pages (5 HTML files)
1. **index.html** - Home page with hero section, services overview, testimonials
2. **services.html** - Detailed service descriptions (Wills, Mortgages, Insurance, Investing, Pensions)
3. **workshops.html** - Workshop information and booking forms
4. **about.html** - Company information, team profiles, values, and credentials
5. **contact.html** - Contact forms, FAQs, office hours

### Assets
- **css/styles.css** - Complete stylesheet with responsive design
- **js/script.js** - JavaScript for navigation, forms, and interactivity
- **images/** - 14 placeholder images (logo and content images)

## Folder Structure

```
cna-website/
├── index.html
├── services.html
├── workshops.html
├── about.html
├── contact.html
├── css/
│   └── styles.css
├── js/
│   └── script.js
└── images/
    ├── logo.png
    ├── hero-home.jpg
    ├── hero-services.jpg
    ├── hero-workshops.jpg
    ├── hero-about.jpg
    ├── hero-contact.jpg
    ├── service-wills.jpg
    ├── service-mortgages.jpg
    ├── service-insurance.jpg
    ├── service-investing.jpg
    ├── service-pensions.jpg
    ├── team-chris.jpg
    ├── workshop-group.jpg
    └── workshop-virtual.jpg
```

## Installation Instructions

### Option 1: Standard Web Hosting (cPanel, Plesk, etc.)

1. **Access your hosting control panel**
   - Log into your web hosting account (e.g., cPanel, Plesk)

2. **Navigate to File Manager**
   - Find the File Manager or FTP section
   - Go to your `public_html` or `www` directory

3. **Upload the files**
   - Upload ALL files maintaining the folder structure
   - Ensure the following structure is preserved:
     ```
     public_html/
     ├── index.html
     ├── services.html
     ├── workshops.html
     ├── about.html
     ├── contact.html
     ├── css/
     ├── js/
     └── images/
     ```

4. **Set permissions** (if required)
   - HTML files: 644
   - CSS/JS files: 644
   - Images: 644
   - Directories: 755

5. **Test the website**
   - Visit your domain in a browser
   - Test all navigation links
   - Test forms (note: forms need backend configuration - see below)

### Option 2: FTP Upload

1. **Use an FTP client** (FileZilla, Cyberduck, etc.)
   - Host: ftp.yourdomain.com
   - Username: [your FTP username]
   - Password: [your FTP password]

2. **Connect and upload**
   - Connect to your server
   - Navigate to your web root directory (usually `public_html` or `www`)
   - Upload all files maintaining folder structure

### Option 3: GitHub Pages (Free Hosting)

1. **Create a GitHub repository**
   - Go to github.com and create a new repository
   - Name it `yourusername.github.io` or any name

2. **Upload files**
   - Upload all files to the repository
   - Maintain folder structure

3. **Enable GitHub Pages**
   - Go to Settings > Pages
   - Select main branch as source
   - Your site will be live at `https://yourusername.github.io`

## Browser Compatibility

✅ **Tested and compatible with:**
- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)
- Mobile browsers (iOS Safari, Chrome Mobile)

## Responsive Design

The website is fully responsive with breakpoints at:
- **Desktop**: > 1024px
- **Tablet**: 768px - 1024px
- **Mobile**: < 768px

## Color Scheme

The website uses the CNA brand colors from the provided flyer:

- **Primary Navy**: #1a1f4d
- **White**: #ffffff
- **Light Blue**: #4a9eff (accent color)
- **Light Grey**: #f5f7fa (backgrounds)
- **Dark Grey**: #333333 (text)
- **Medium Grey**: #666666 (secondary text)

## Customization Guide

### 1. Replace Placeholder Content

#### Contact Information
Update in ALL HTML files (footer section):
```html
<!-- Find and replace these: -->
<a href="tel:07397852939">07397852939</a>
<a href="mailto:Chris@cnafinancial.co.uk">Chris@cnafinancial.co.uk</a>
<a href="https://CNAfinancial.co.uk">CNAfinancial.co.uk</a>
```

#### FCA Registration Number
In **about.html**, find:
```html
<p style="font-size: 0.9rem; margin-top: 1rem;">
    FCA Number: [To be inserted]
</p>
```
Replace `[To be inserted]` with your actual FCA number.

### 2. Replace Placeholder Images

All images in the `images/` folder are placeholders. Replace them with:

- **logo.png** - Your actual company logo (recommended: 200x60px)
- **hero-*.jpg** - Hero/banner images for each page (1200x400-600px)
- **service-*.jpg** - Service-specific images (600x400px)
- **team-chris.jpg** - Team member photo (400x400px square)
- **workshop-*.jpg** - Workshop images (800x500px)

**Important**: Keep the same filenames or update references in HTML files.

### 3. Update Team Information

In **about.html**, find the team section and:
- Add real qualifications
- Add actual team member information
- Replace placeholder text with real bio

### 4. Configure Forms (CRITICAL)

The forms currently show browser alerts. For production, you need to:

#### Option A: Use a Form Service (Easiest)
1. Sign up for Formspree, Basin, or similar service
2. Update form action:
```html
<form action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
```

#### Option B: Use Server-Side Processing
1. Create a PHP script (contact-handler.php):
```php
<?php
if ($_SERVER["REQUEST_METHOD"] == "POST") {
    $name = $_POST['first-name'] . ' ' . $_POST['last-name'];
    $email = $_POST['email'];
    $phone = $_POST['phone'];
    $service = $_POST['service'];
    
    $to = "Chris@cnafinancial.co.uk";
    $subject = "New Consultation Request";
    $message = "Name: $name\nEmail: $email\nPhone: $phone\nService: $service";
    
    mail($to, $subject, $message);
    
    header("Location: thank-you.html");
}
?>
```

2. Update form in contact.html:
```html
<form action="contact-handler.php" method="POST">
```

### 5. Add Google Analytics (Recommended)

Add before closing `</head>` tag in all HTML files:
```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_MEASUREMENT_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'GA_MEASUREMENT_ID');
</script>
```

Replace `GA_MEASUREMENT_ID` with your Google Analytics ID.

### 6. Add Social Media Links

In footer section of all pages, update:
```html
<div class="social-links">
    <a href="https://linkedin.com/company/your-page" aria-label="LinkedIn">in</a>
    <a href="https://facebook.com/your-page" aria-label="Facebook">f</a>
    <a href="https://twitter.com/your-handle" aria-label="Twitter">𝕏</a>
</div>
```

### 7. SEO Optimization

Update meta descriptions in each HTML file:
```html
<meta name="description" content="Your custom description here">
```

Add to `<head>` section:
```html
<meta name="keywords" content="financial planning, mortgage advisor, pension advice, UK">
<meta name="author" content="CNA Financial Planning">
```

## Features

### Navigation
- Sticky header navigation
- Mobile-responsive hamburger menu
- Active page highlighting
- Smooth scroll for anchor links

### Forms
- Client-side validation
- Required field indicators
- Mobile-friendly inputs
- Checkbox groups for multiple selections

### Interactive Elements
- FAQ accordion (expandable questions)
- Hover effects on cards and buttons
- Scroll-to-top button
- Form validation feedback

### Accessibility
- Semantic HTML
- ARIA labels for screen readers
- Keyboard navigation support
- Proper heading hierarchy

## Performance Optimization

### Current Setup
- Single CSS file (minify for production)
- Single JS file (minify for production)
- Optimized images (replace placeholders with web-optimized versions)

### Recommendations for Production

1. **Minify CSS and JS**
   - Use online tools or build processes to minify
   - Can reduce file size by 30-50%

2. **Optimize Images**
   - Use WebP format where supported
   - Compress JPEG images to 80-85% quality
   - Use appropriate sizes (don't serve 4K images for thumbnails)

3. **Enable Caching**
   Add to `.htaccess` file:
   ```apache
   <IfModule mod_expires.c>
     ExpiresActive On
     ExpiresByType image/jpg "access plus 1 year"
     ExpiresByType image/jpeg "access plus 1 year"
     ExpiresByType image/png "access plus 1 year"
     ExpiresByType text/css "access plus 1 month"
     ExpiresByType application/javascript "access plus 1 month"
   </IfModule>
   ```

4. **Enable Compression**
   Add to `.htaccess`:
   ```apache
   <IfModule mod_deflate.c>
     AddOutputFilterByType DEFLATE text/html text/plain text/css text/javascript application/javascript
   </IfModule>
   ```

## Security Recommendations

1. **SSL Certificate (HTTPS)**
   - Essential for forms and trust
   - Most hosts offer free Let's Encrypt certificates
   - Configure before launch

2. **Form Protection**
   - Add CAPTCHA to prevent spam (Google reCAPTCHA)
   - Implement rate limiting on server
   - Validate all inputs server-side

3. **Regular Updates**
   - Keep contact information current
   - Update testimonials regularly
   - Review and update service information

## Legal Requirements (UK)

### Required Pages to Create
You'll need to add these pages:

1. **Privacy Policy** (privacy.html)
   - Required under UK GDPR
   - Template: ico.org.uk

2. **Terms & Conditions** (terms.html)
   - Website terms of use
   - Service terms

3. **Cookie Policy** (cookies.html)
   - Cookie usage disclosure
   - Or add cookie consent banner

4. **Complaints Procedure** (complaints.html)
   - FCA requires this for regulated activities

### Cookie Consent Banner
Add before closing `</body>` tag:
```html
<div id="cookie-banner" style="position: fixed; bottom: 0; width: 100%; background: #1a1f4d; color: white; padding: 1rem; text-align: center; z-index: 9999;">
    <p>We use cookies to improve your experience. <a href="cookies.html" style="color: #4a9eff;">Learn more</a></p>
    <button onclick="document.getElementById('cookie-banner').style.display='none'" style="background: #4a9eff; color: white; border: none; padding: 0.5rem 1rem; margin-left: 1rem; cursor: pointer;">Accept</button>
</div>
```

## Testing Checklist

Before going live, test:

- [ ] All navigation links work
- [ ] All pages display correctly on mobile
- [ ] All pages display correctly on tablet
- [ ] All pages display correctly on desktop
- [ ] Forms submit correctly (or show appropriate messages)
- [ ] All images load
- [ ] Contact information is correct
- [ ] Social media links work
- [ ] Email links open mail client
- [ ] Phone links work on mobile
- [ ] FAQ accordion opens/closes
- [ ] Mobile navigation menu works
- [ ] No console errors in browser developer tools
- [ ] Page load speed is acceptable (< 3 seconds)
- [ ] All text is spelled correctly
- [ ] FCA disclaimers are present and correct

## Common Issues & Fixes

### Issue: Images don't load
**Fix**: Check file paths are correct and case-sensitive. Ensure folder structure is maintained.

### Issue: Navigation doesn't work on mobile
**Fix**: Ensure `js/script.js` is loading. Check browser console for errors.

### Issue: Forms don't submit
**Fix**: Forms need backend configuration. See "Configure Forms" section above.

### Issue: Styles look broken
**Fix**: Ensure `css/styles.css` is in correct location. Check browser console for 404 errors.

### Issue: Google Fonts not loading
**Fix**: Requires internet connection. Fonts load from Google CDN.

## Next Steps After Deployment

1. **Set up email forwarding**
   - Ensure Chris@cnafinancial.co.uk works
   - Configure on your hosting panel

2. **Configure forms**
   - Choose form handling method
   - Test thoroughly

3. **Set up analytics**
   - Google Analytics
   - Google Search Console

4. **SEO**
   - Submit sitemap to Google
   - Verify with Google Search Console
   - Set up Google My Business

5. **Marketing**
   - Share on social media
   - Email existing contacts
   - Update business cards with website

6. **Legal pages**
   - Create privacy policy
   - Create terms & conditions
   - Add cookie consent

7. **Ongoing maintenance**
   - Regular backups
   - Update content quarterly
   - Monitor analytics
   - Respond to form submissions promptly

## Support & Customization

### Want to customize further?

**Change colors:**
Edit CSS variables in `css/styles.css` (lines 3-10):
```css
:root {
    --primary-navy: #1a1f4d;
    --light-blue: #4a9eff;
    /* etc. */
}
```

**Change fonts:**
Update in `<head>` of HTML files and in CSS:
```html
<link href="https://fonts.googleapis.com/css2?family=YOUR-FONT&display=swap" rel="stylesheet">
```

**Add more pages:**
Copy an existing HTML file and modify content. Ensure navigation is updated in ALL pages.

## Troubleshooting

### Forms aren't working
The forms are currently set up with JavaScript validation only. For production use, you MUST configure backend form handling. See "Configure Forms" section.

### Mobile menu won't close
Make sure `js/script.js` is loading correctly. Check browser console for errors.

### Styles look different than expected
Ensure you're viewing over HTTP/HTTPS, not as local files (file://). Some browsers restrict local file loading.

## Credits

**Design & Development**: Based on CNA Financial Planning brand materials
**Framework**: Pure HTML5, CSS3, JavaScript (no dependencies)
**Icons**: Emoji (for maximum compatibility)
**Fonts**: Google Fonts (Montserrat, Open Sans)

## License

This website package is provided for CNA Financial Planning. All content should be customized for your specific business needs.

---

**Need help?** Contact your web developer or hosting provider for assistance with deployment and configuration.

**Last Updated**: February 2026
**Version**: 1.0
