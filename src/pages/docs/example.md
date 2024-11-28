---
title: Example Page
description: Lean how to create a HyScript Page.
---

## How to Create a Page  

### Step 1: Add an `index.js` File  
In your project directory, create an `index.js` file to set up and run your HyScript server.  

#### Example `index.js`:
```javascript  
const HyScript = require('hyscript-latest');  

const hy = new HyScript();  

// Set the directory containing `.hs` files  
hy.set('./pages');  

// Public Directory 
hy.static('public')

// Start the server on a specific port  
const PORT = 3000;  
hy.start(PORT, 'HyScript server is running!');  
```  

### Step 2: Create the `pages` Directory  
Create a folder in your project root named `pages`. This is where you will store your `.hs` files.  

### Step 3: Create `.hs` Files  
Each `.hs` file is a JSON file containing metadata and content for your web page. The `.hs` file structure allows you to define the page's title, meta description, logo, and whether Tailwind CSS should be included, followed by the actual HTML content.

#### Example `.hs` File (`home.hs`):

```json
{
  "title": "Home Page",
  "meta": "Welcome to our homepage.",
  "logo": "/favicon.ico",
  "tailwindcss": true
}
<!---Content--->
<h1>Welcome to HyScript!</h1>
<p>This is a dynamic page.</p>
```

#### Example `.hs` File (`about.hs`):

```json
{
  "title": "About Us",
  "meta": "Learn more about our company.",
  "logo": "/logo.png",
  "tailwindcss": false
}
<!---Content--->
<h1>Hello, This is your HyScript Example Page. Change this in about.hs!</h1>
<p>Welcome to the page. Customize the content as per your needs.</p>
```

In the example above:
- The JSON section contains metadata like the `title`, `meta`, `logo`, and whether to include Tailwind CSS.
- The HTML content comes after `<!---Content--->` and will be rendered on the page.
