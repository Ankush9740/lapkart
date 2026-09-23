# LapKart

**Find the Laptop That Fits Your World.**

LapKart is a responsive laptop-shopping demonstration created for a BCA Semester V *AI Tools and Techniques* practical. Visitors can explore a sample catalogue, compare specifications, filter and sort products, and place a mock order.

## Technologies

- HTML5 for semantic page structure and accessible form controls
- CSS3 for responsive layouts, product cards, drawer, modal and subtle interactions
- Vanilla JavaScript for the catalogue and shopping experience
- Browser `localStorage` for cart persistence

## Main features

- 40 sample laptops across student, business, gaming, creator, convertible, workstation, premium, thin and light, and AI PC categories
- Search across laptop name, brand, processor, graphics and category
- Combined category, brand, processor, RAM, graphics and price filters
- Featured, price, rating and discount sorting
- Product cards and discounted deal cards rendered from JavaScript data
- Cart drawer with quantity controls, item removal, subtotal, delivery and total
- Free delivery at ₹50,000; ₹99 delivery below that amount
- Cart contents retained when the page is refreshed or reopened
- Validated demo checkout with a generated order ID; no payment is processed
- Responsive navigation, filters, cart and checkout for mobile screens

## Files

```text
LapKart/
├── index.html   Page content and accessible UI structure
├── style.css    Visual design and responsive rules
├── script.js    Sample data and application behavior
└── README.md    Project overview and run instructions
```

Product photos are loaded from Unsplash image URLs and the page includes an inline SVG fallback if an image cannot be reached. No local image assets or server-side services are required.

## Run the project

1. Open this folder in Visual Studio Code.
2. Install the **Live Server** extension if it is not already installed.
3. Right-click `index.html` and choose **Open with Live Server**.
4. Use the site in the browser. Cart data is stored in that browser's local storage.

The project has no build step, backend, database, external API key or payment integration.

## How filtering and search work

The `laptops` array in `script.js` contains each product's model, brand, category, specifications, prices, rating, image and optional badge. `getFilteredProducts()` checks every active filter and search term against the same product record, then applies the selected sort order. `renderProducts()` creates the matching cards and updates the results count and empty state. This means filters combine instead of replacing one another.

## How the cart works

The cart is an array of `{ id, quantity }` entries. Adding a laptop already present increments its quantity. The cart renderer looks up the matching product record to display current details and calculates the subtotal, delivery and total. Delivery is free when the subtotal is at least ₹50,000 and costs ₹99 otherwise.

After every cart change, `saveCart()` writes the array to `localStorage` under the `lapkart-cart` key. On startup, `loadCart()` restores and validates saved entries. Submitting the demonstration checkout clears that saved cart.

## Catalogue disclaimer

Product names, specifications, images, ratings and prices are sample demonstration data for this practical project. They do not represent live inventory, verified current prices, or an offer from a real retailer. Checkout and payment choices are for demonstration only; no payment is processed.
