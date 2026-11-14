# GO GREEN: Software Company Website

A multi-page, responsive website for a software company, built with plain HTML, CSS and jQuery. No build step, no framework, no backend. Open it in a browser and it works.

The brand is "GO GREEN" and the accent colour is a fresh green (`#1dbf73`). The content is placeholder text and stock images, so it's meant to be a starting point you reshape for a real company, or a solid piece of frontend practice.

## What's inside

Six pages, all linked from the same navbar:

| Page | What it has |
| --- | --- |
| `index.html` | The full landing page: hero carousel, about, services, call to action, pricing, skill bars, animated counters, portfolio, team, testimonials, client logos, contact |
| `about.html` | Welcome text plus Mission, Vision and Objective |
| `service.html` | Service cards (web design, web development, app design, app development) |
| `portfolio.html` | Filterable project gallery with a lightbox |
| `price.html` | Three pricing plans side by side |
| `contact.html` | Address, phone, email and a contact form |

A few things worth pointing out:

- **Portfolio filtering.** Isotope lets you filter by All, Web Design, Web Development, App Design and App Development without reloading the page.
- **Lightbox.** Portfolio images open in a lightbox.
- **Carousels.** The hero uses Bootstrap's carousel with swipe support for touch screens. Testimonials and client logos use Owl Carousel with autoplay.
- **Scroll effects.** Skill bars fill and counters count up when you scroll to them (Waypoints + CounterUp). The header changes style after 100px of scrolling and there's a back-to-top button.
- **Navigation.** Superfish handles the desktop dropdown menu. On small screens `main.js` clones the menu into a slide-in mobile nav.

## Getting started

You only need a browser.

```bash
# 1. Grab the project
cd "Software Company Business Website"

# 2. Open index.html directly...
open index.html          # macOS
xdg-open index.html      # Linux
start index.html         # Windows

# ...or serve it locally
python3 -m http.server 8000
# then visit http://localhost:8000
```

If you use VS Code, the Live Server extension works out of the box. The included `.vscode/settings.json` sets it to port `5501`.

One note: the Google Fonts (Montserrat and Nunito) load from Google's CDN, so you'll see fallback fonts if you open the site offline. Everything else is bundled locally.

## Project structure

```
.
├── index.html
├── about.html
├── service.html
├── portfolio.html
├── price.html
├── contact.html
├── css/
│   └── style.css          # All custom styling (~1,500 lines)
├── js/
│   └── main.js            # Plugin setup, mobile nav, scroll behaviour
├── img/                   # Hero slides, portfolio, team, clients, favicon
└── vendor/                # Third-party libraries, bundled locally
    ├── bootstrap/         # 4.2.1
    ├── jquery/            # + jquery-migrate
    ├── ionicons/          # 4.5.10, icon font
    ├── owlcarousel/
    ├── isotope/
    ├── lightbox/
    ├── superfish/         # + hoverIntent
    ├── waypoints/
    ├── counterup/
    ├── touchSwipe/
    └── easing/
```

## Tech stack

- HTML5 and CSS3
- Bootstrap 4.2.1 for the grid and base components
- jQuery for all the interactivity
- Ionicons for icons
- Owl Carousel, Isotope, Lightbox, Superfish, Waypoints, CounterUp, TouchSwipe

## Customising it

**Branding.** "GO GREEN" appears in the header and footer of every page. Search and replace it across the six HTML files. Each page also has a generic `<title>`, so update those too.

**Colours.** The main green is `#1dbf73` in `css/style.css`. Search for that value and swap it for your own.

**Content.** All text and image paths live directly in the HTML. Images are in `img/`, so replace them with files of the same name or update the `src` attributes.

**Portfolio categories.** Each portfolio item carries a class like `web-des` or `app-dev`, and the filter buttons match on those. To add a category, add a new `<li data-filter=".your-class">` and give the relevant items that class. The same filter markup appears in both `index.html` and `portfolio.html`.

**Pricing.** Plans are plain markup inside `.price-plan` blocks on `index.html` and `price.html`. Edit the amount and the feature list in place. Right now the feature lists still describe the template itself ("HTML5 and CSS3", "Bootstrap 4"), so you'll want to rewrite them.

## Known gaps

Being upfront about what isn't finished:

- **The contact form doesn't send anything.** `contact.html` has a form with no `action` and no handler, so submitting it does nothing. You'll need to wire it to a backend or a service like Formspree or EmailJS.
- **The newsletter form in the footer is the same story.** It has an empty `action` and no script behind it.
- **Placeholder content throughout.** Names, testimonials, address, phone and email are all dummy data. Service card links point to `#`.
- **Some leftovers from the original template.** The page titles still read "HTML Business Template", and `vendor/lightbox/links.php` references paths that don't exist here. Neither affects the site.
- **No SEO or accessibility pass yet.** There are no meta descriptions or Open Graph tags, and the image `alt` text and form labels deserve a review.

## Ideas for next steps

- Hook up the contact form and newsletter signup
- Pull the repeated header and footer into includes, or move to a small static site generator, so a nav change doesn't mean editing six files
- Add meta tags and proper alt text
- Swap the stock photos and dummy copy for real content
- Deploy it on GitHub Pages, Netlify or Vercel, since it's fully static

## Credits and licences

The bundled libraries keep their own licences (Bootstrap and Ionicons are MIT, Owl Carousel ships with its own `LICENSE` file). Check each library's terms before using the site commercially. Photos in `img/` are placeholders, so replace them with images you have the rights to use.
