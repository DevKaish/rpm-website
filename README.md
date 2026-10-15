# Real Estate Profit Machine (RPM) website

Static HTML, CSS and JavaScript. Open `index.html` in a browser (internet needed for Google Fonts and Font Awesome icons).

## Structure
```
index.html        Home
projects.html     All plotting projects (filters, search, sort, detail popup)
commercial.html   Commercial plots (type tiles, filters, detail popup, frontage guide)
vrindavan.html    Vrindavan Mathura township page
dholera.html      Dholera township page
login.html        Member login
register.html     Create account
css/style.css     All styles (one file for every page)
js/app.js         Shared data (PLOTS, TOWNS), SVG artwork, header and footer
js/township.js    Renders the Vrindavan and Dholera pages from a small config
js/auth.js        Icons, form validation for login and register
images/favicon.svg
```
Header and footer are written once in `js/app.js` (`mountChrome`) and used on every page except login and register.

## Replace the sample content
- **Plots:** the `PLOTS` array at the top of `js/app.js` is sample data. Replace it with your real listings or load it from your API. Every listing page, stat, chart and popup reads from it.
- **Townships:** `TOWNS` in `js/app.js` (names, links, artwork mood).
- **Contact details, WhatsApp number:** `WA` at the top of `js/app.js`, and the footer block in `mountChrome`. Current values are the demo ones from the design (`+91 90000 11111`, `hello@rpm-demo.com`).
- **Township page text:** the config object at the bottom of `vrindavan.html` and `dholera.html`.

## Connect login and sign-up (ASP.NET or any backend)
- `login.html` posts to `/Account/Login`, `register.html` posts to `/Account/Register`. Change the form `action` values.
- `js/auth.js` starts with `DEMO = true`, which validates the form and shows a notice instead of submitting. Set it to `false` to submit for real.
- Referral check: `lookupReferral()` in `js/auth.js` uses a demo list (`HW613477`). Replace it with a call to your member API.
- Field names: `username`, `password` for login. `referralId`, `referralName`, `firstName`, `lastName`, `phone`, `email`, `pan`, `password`, `confirm`, `terms` for register.

## Placeholder links to fill in
These still point to `#` because the pages or URLs were not part of this build:
- Footer: Disclaimer, Refund Policy, and the Facebook, Instagram and YouTube icons.
- Home page: the "Read the Business Plan" button.
- Login page: "Forgot password?".
