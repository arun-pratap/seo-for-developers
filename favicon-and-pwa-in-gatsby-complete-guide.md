# Favicon Icon Use (gatsby)

## 🎯Make favicon For Quedemy:
- Background: #4F15AC (brand color)
- Icon: simple “Q” or logo symbol
- Clean + visible in small size

## ✅ Design Specs

Create these exact files:

| File                       | Size         | Purpose         |
| -------------------------- | ------------ | --------------- |
| favicon.ico                | 16x16, 32x32 | Browser default |
| favicon-16x16.png          | 16x16        | Small devices   |
| favicon-32x32.png          | 32x32        | Standard        |
| apple-touch-icon.png       | 180x180      | iPhone          |
| android-chrome-192x192.png | 192x192      | Android         |
| android-chrome-512x512.png | 512x512      | PWA             |

## Put favicon in root: Put all favicon files inside. 👉 In Gatsby, /static = root (/)

```
/static
   favicon.ico
   favicon-16x16.png
   favicon-32x32.png
   apple-touch-icon.png
   android-chrome-192x192.png
   android-chrome-512x512.png
```

## In html

```html
<link rel="icon" href="/favicon.ico" />
<link rel="icon" sizes="32x32" href="/favicon-32x32.png" />
<link rel="icon" sizes="16x16" href="/favicon-16x16.png" />
<link rel="apple-touch-icon" href="/apple-touch-icon.png" />
<meta name="theme-color" content="#4F15AC" key="theme-color" />,

<!-- not must but good to have -->
Support light & dark mode
<meta name="theme-color" content="#FFFFFF" media="(prefers-color-scheme: light)">
<meta name="theme-color" content="#000000" media="(prefers-color-scheme: dark)">
```

👆 This is for:
Browser tab
Bookmark icon

Do this:
gatsby-ssr.js → favicon + theme color ✅
SEO.tsx → title, OG, Twitter, schema ✅
👉 Separation = clean + scalable

## (BEST for Gatsby) → gatsby-ssr.js: Cleanest + Scalable. Inside gatsby-ssr.js -> Add:

```ts
import React from "react";

export const onRenderBody = ({ setHeadComponents }) => {
  setHeadComponents([
    <link rel="icon" href="/favicon.ico" key="favicon-ico" />,
    <link rel="icon" type="image/png" sizes="32x32" href="/favicon-32x32.png" key="favicon-32" />,
    <link rel="icon" type="image/png" sizes="16x16" href="/favicon-16x16.png" key="favicon-16" />,
    <link rel="apple-touch-icon" href="/apple-touch-icon.png" key="apple-touch-icon" />,
    <meta name="theme-color" content="#4F15AC" key="theme-color" />,
  ]);
};
```

👉 Done. Applies to ALL pages automatically
👉 No need to touch SEO component

 # Global (PWA + App Icon)
Install plugin:

npm install gatsby-plugin-manifest
In gatsby-config.js:

{
  resolve: `gatsby-plugin-manifest`,
  options: {
    name: `Quedemy`,
    short_name: `Quedemy`,
    start_url: `/`,
    background_color: `#4F15AC`,
    theme_color: `#4F15AC`,
    display: `standalone`,
    icon: `static/android-chrome-512x512.png`,
  },
}

 ```
OR ICONS OF ARRAY
    "icons": [
    {
      "src": "/icon-192.png",
      "sizes": "192x192",
      "type": "image/png"
    },
    {
      "src": "/icon-512.png",
      "sizes": "512x512",
      "type": "image/png"
    }
  ]
```

👉 This handles:

Mobile install icon
Android splash
PWA behavior

# PWA Offline Support

npm install gatsby-plugin-offline

👉 Makes your site:
Installable like app
Works offline
Feels premium

