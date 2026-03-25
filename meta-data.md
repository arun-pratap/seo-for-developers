## BASIC SEO

**1. Title Tag**

```html
<title>Best Website Development Services in India | Website Dukaan</title>
<!-- 👆 This is what shows on Google search. -->
```

**Rules:**
- 50–60 characters
- Include main keyword
- Add brand name at end

**2. Meta Description**

```html
<meta name="description" content="Get high-performance, SEO-friendly websites for your business. Affordable pricing, modern design, and fast delivery. Contact Website Dukaan today." />
<!-- 👉 This improves CTR (click-through rate) -->
```

**Rules:**
- 140–160 characters
- Clear benefit + CTA
- No keyword stuffing

**3. Canonical URL**

```html
<link rel="canonical" href="https://yourwebsite.com/" /
<!-- 👉 Prevents duplicate content issues -->
```

**4. Robots Meta (Good but not Must)**

```html
<meta name="robots" content="index, follow" />
<!-- 👉 Tells Google to index the page -->
```

**5. Viewport (Mobile Optimization)**

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<!-- 👉 Important for mobile SEO -->
```

**6. Charset**
```html
<meta charset="UTF-8" />
```

## 🚀 Social Sharing Metadata (VERY IMPORTANT)

### Open Graph (OG)

```html
<meta property="og:type" content="website" /> 
<!-- For website content will be website, for blog it will be article -->

<meta property="og:title" content="Website Development Services | Website Dukaan" />
<meta property="og:description" content="Modern, fast, SEO-ready websites for businesses." />
<meta property="og:image" content="https://yourwebsite.com/cover.jpg" />
<meta property='og:image:alt' content="image-alternative-text"></meta>
<meta property="og:url" content="https://yourwebsite.com" />
<meta property="og:site_name" content="Google" />
<!-- site_name always brand name or soething relevant like quedemy blog quedemy ebooks etc. -->

<meta property="article:published_time" content="2026-03-25" />
<meta property="article:author" content="Your Name" />
<!-------------------------------------------------
 for type === "article"
👉 Helps platforms understand it’s real content
-------------------------------------------------->

<!-- 👉 1200 × 630 px (Good to add but not must) -->
<meta property='og:image:width' content='1680' />
<meta property='og:image:height' content='296' />
```

### Twitter Meta

```html
<meta name="twitter:card" content="summary_large_image" /> 
<meta name="twitter:title" content="Website Dukaan" />
<meta name="twitter:description" content="High-performance websites for your business." />
<meta name="twitter:image" content="https://yourwebsite.com/cover.jpg" />
<!-- image must be full URL like: https://quedemy.com/images/cover.jpg
     Not like /images/cover.jpg
     Best size:1200 × 630 px, Ratio: 1.91:1
-->

<!-- only if you have twiter handle for website or author/writer -->
<meta name="twitter:site" content="@quedemy" /> // 
<meta name="twitter:creator" content="@arunpsingh" />
```




