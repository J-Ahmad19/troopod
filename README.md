# Troopod: Purelane Shopify Theme Customization

This repository contains the dynamic Shopify Liquid sections built for the Purelane storefront, based on the Dawn theme. The static HTML prototype was converted into highly customizable, merchant-friendly sections.

## Sections Implemented

The following 5 core sections were created in the `sections/` directory:

1. **`purelane-hero.liquid`**
   - **Purpose:** The main hero banner at the top of the homepage.
   - **Features:** Dynamic text fields (Heading, Highlighted Text, Subheading), customizable CTA button, and a repeatable block for Trust Badges (e.g., "Non-toxic", "Plant-based").

2. **`purelane-shop-grid.liquid`**
   - **Purpose:** A dynamic product grid displaying items from a specific collection.
   - **Features:** Allows the merchant to select a collection. Automatically handles edge cases:
     - Renders a "Sold Out" badge if inventory is 0 and disables the add to cart button.
     - Provides a fallback placeholder image if a product is missing an image.
     - Maintains grid alignment even if product titles are very long.

3. **`purelane-best-selling-combos.liquid`**
   - **Purpose:** A showcase of popular product combinations.
   - **Features:** Block-based architecture. Merchants can add multiple "Combo" blocks, configure up to 5 products per combo (images and text), set pricing (regular and compare at), and optionally flag a block as a highlighted "Hero Combo".

4. **`purelane-bundles.liquid`**
   - **Purpose:** A tiered bundle selection area.
   - **Features:** Similar to the combos section, it uses blocks for each bundle tier (e.g., "Starter", "Most popular"). Includes customizable bullet points, pricing tags, and dynamic image layouts.

5. **`purelane-reviews-rail.liquid`**
   - **Purpose:** A horizontally scrolling marquee of customer reviews.
   - **Features:** Block-based setup allowing merchants to add individual reviews. Each block supports star ratings (1-5), a headline, review text, author name, and an optional product name reference.

## How to Reproduce / Install

To use these sections in your own Shopify Dawn theme, follow these steps:

### 1. Copy the Sections
Copy the `.liquid` files from this repository into the `sections/` folder of your Shopify theme.
- `purelane-hero.liquid`
- `purelane-shop-grid.liquid`
- `purelane-best-selling-combos.liquid`
- `purelane-bundles.liquid`
- `purelane-reviews-rail.liquid`

### 2. Include the Styles
Ensure that the CSS provided in the original `purelane-homepage.html` prototype is included in your theme. You can append the styles to your theme's `base.css` or create a new stylesheet and link it within `theme.liquid`.

### 3. Customize via the Theme Editor
1. Log in to your Shopify Admin.
2. Go to **Online Store > Themes** and click **Customize** on your active theme.
3. Navigate to the page where you want to add the sections (e.g., the Home page).
4. Click **Add section** and search for the new sections (e.g., "Purelane Hero", "Best Selling Combos").
5. Use the sidebar to fill in the text fields, select collections, and add blocks (such as Trust Badges or Reviews).
6. Click **Save**.

## Git Workflow Log
All work was systematically committed to this repository. The typical workflow involved:
1. `git init` and `git remote add origin` to set up the connection.
2. Converting the raw HTML into `.liquid` files containing HTML, Liquid logic, and JSON schemas.
3. Adding, committing, and pushing files iteratively to ensure version history was maintained.
