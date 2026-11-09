# Kettle & Leaf: Klaviyo practice store

A tiny 3-page tea shop (plain HTML, CSS and a little JavaScript) for practicing Klaviyo.

## Setup
1. In Klaviyo go to **Settings > Account > API keys** and copy your **Public API Key** (6 characters).
2. Open `app.js` and replace `YOUR_PUBLIC_KEY`.
3. Run a local server (Klaviyo tracking works best over http, not file://):
   - `python3 -m http.server 8000`, then open http://localhost:8000
   - or use the VS Code "Live Server" extension.

## What gets sent to Klaviyo
| Action in the store          | Klaviyo call / metric                 |
|------------------------------|---------------------------------------|
| Any page load                | Active on Site (automatic)            |
| Newsletter form              | `identify` + "Newsletter Signup (Practice)" |
| Open a product page          | Viewed Product                        |
| Add to cart                  | Added to Cart                         |
| Cart > Start checkout        | Started Checkout                      |
| Cart > Place practice order  | Placed Order                          |

Check results in **Klaviyo > Profiles** and **Analytics > Metrics** (can take a few minutes).

## Things to practice
- Build a **flow**: Newsletter signup > welcome email with a 10% code.
- Build an **Abandoned Cart** flow (trigger: Started Checkout, no Placed Order).
- Build a **Browse Abandonment** flow (trigger: Viewed Product).
- Segment people who viewed "Ceremonial Matcha" but never ordered.
- Add an **embedded sign-up form**: replace `XXXXXX` in `index.html` with your form ID.
- Try a **popup form** built in Klaviyo's form editor. It will show automatically once the key is set.

## Files
- `index.html`: home, product grid, signup form
- `product.html`: product detail (fires Viewed Product)
- `cart.html`: cart, checkout, practice order
- `style.css`: styling
- `app.js`: catalog, cart, Klaviyo tracking code (comments explain each call)
