# Setting up Tailwind CSS with Yarn

This guide explains how to set up Tailwind CSS in your project using Yarn, including initialization and configuration steps.

## Install Tailwind CSS
```bash
yarn add tailwindcss@3 -D
```

## Initialize Tailwind CSS
```bash
yarn tailwindcss init
```

## Create `tailwind.config.js`
Inside the generated `tailwind.config.js`, configure it as follows:

```javascript
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: [
    "./src/**/*.{js,jsx,ts,tsx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

## Update `index.css`
Add the following lines to your `index.css` file to include Tailwind's base styles, components, and utilities:

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```
