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

To reproduce this setup from scratch and use these sections in your own Shopify Dawn theme, follow these exact steps:

### 1. Set Up the Base Theme
1. Download the base Dawn theme as a ZIP file from your Shopify admin (or use the exported zip from your development store).
2. Extract the ZIP file into a local directory on your machine.
3. Initialize a Git repository in that directory, commit the base files, and push them to a new GitHub repository.
   ```bash
   git init
   git add .
   git commit -m "Initial commit of Dawn theme"
   git remote add origin <your-github-repo-url>
   git push -u origin main
   ```

### 2. Add the Custom Sections
You have two options for adding the custom sections to your theme:

**Option A: Using Shopify's "Edit Code" (Browser-based)**
1. In your Shopify Admin, go to **Online Store > Themes**.
2. Click the `...` menu next to your active theme and select **Edit code**.
3. Under the **Sections** folder, click **Add a new section**.
4. Name your file (e.g., `purelane-bundles.liquid`) and click **Done**.
5. Copy the code from the corresponding file in this repository and paste it into your new file, replacing the default code.
6. Click **Save**. Repeat for all 5 sections.

**Option B: Working Locally (Git-based)**
1. Copy the 5 `.liquid` files from this repository directly into the `sections/` folder of your local theme directory.
2. Commit and push the changes to your GitHub repository.
   ```bash
   git add sections/purelane-*.liquid
   git commit -m "Add custom Purelane sections"
   git push
   ```
3. If your Shopify theme is connected to your GitHub repository (via the Shopify GitHub integration), the sections will automatically sync to your live store.

### 3. Include the Styles
Ensure that the CSS provided in the original `purelane-homepage.html` prototype is included in your theme. You can append the styles to your theme's `base.css` or create a new stylesheet and link it within `theme.liquid`.

### 4. Customize via the Theme Editor
1. In the Shopify Admin, go to **Online Store > Themes** and click **Customize**.
2. Navigate to the page where you want to add the sections (e.g., the Home page).
3. Click **Add section** and search for the new sections (e.g., "Purelane Hero", "Purelane Bundles").
4. Once added, use the right sidebar to fill in the text fields, select product collections, and add individual blocks (such as specific bundles or reviews).
5. Click **Save**.

## Git Workflow Log
Throughout this assignment, the following Git workflow was used to maintain version control:
1. Initialized the repository locally (`git init`) and linked it to the GitHub remote (`git remote add origin`).
2. Pushed the initial theme files and the raw `purelane-homepage.html` prototype.
3. Iteratively built the 5 dynamic `.liquid` sections.
4. Added, committed, and pushed each file individually (`git commit -m "Add purelane-hero.liquid section"`) to keep the commit history clean and atomic.
