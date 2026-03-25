# ✅ 1. `gatsby-source-filesystem`

> “Loads files into Gatsby’s data layer and creates `File` nodes in GraphQL. It does NOT process or optimize anything.”

### Important clarification:

* Yes, images become available in GraphQL
* ❌ But **no optimization yet**
* ❌ No `childImageSharp` yet

# ✅ 2. `gatsby-plugin-mdx`

> “Transforms `.mdx` files into GraphQL nodes (`Mdx`) and allows using Markdown + React together.”

### Extra:

* Adds:

  * `body` (compiled content)
  * `frontmatter`
* Enables dynamic pages like:

  ```
  /blog/{mdx.slug}
  ```

# ⚠️ 3. `gatsby-transformer-sharp`

Your understanding:

> “Creates `childImageSharp` nodes from image `File` nodes so they can be processed by `gatsby-plugin-sharp` and queried in GraphQL.”

### Important:

* It **does NOT optimize**
* It just **bridges File → Sharp system**

# ✅ 4. `gatsby-plugin-sharp`

> “Core image processing engine that performs resizing, cropping, compression, and format conversion (WebP, AVIF) at build time.”

## 🔥 What else it can do (useful for you):

* Resize images dynamically
* Generate multiple resolutions (`srcset`)
* Crop / fit images:

  ```graphql
  layout: CONSTRAINED
  aspectRatio: 16/9
  ```
* Quality control:

  ```graphql
  quality: 80
  ```
* Convert formats:

  ```graphql
  formats: [AUTO, WEBP, AVIF]
  ```

👉 This is where **performance magic happens**

# ⚠️ 5. `gatsby-plugin-image`

Your understanding:

> for rendering and lazy loading

## ❓ “what about inbuilt Gatsby image plugin?”

## 🔥 What it actually does:

> “Provides React components (`GatsbyImage`, `StaticImage`) to render optimized images with lazy loading, placeholders, and responsive behavior.”

---

## 💡 Key insight (VERY IMPORTANT)

👉 `gatsby-plugin-sharp` = backend processing
👉 `gatsby-plugin-image` = frontend rendering

---

# 🧠 Final Mental Model (You should remember this)

```text
gatsby-source-filesystem  → loads files
gatsby-plugin-mdx         → converts content
gatsby-transformer-sharp  → connects images to sharp
gatsby-plugin-sharp       → processes images
gatsby-plugin-image       → displays images
```

---

# 🚀 One Mistake to Avoid

👉 If you query like this:

```graphql
file {
  publicURL
}
```

❌ Still NOT optimized

👉 You MUST use:

```graphql
childImageSharp {
  gatsbyImageData(...)
}
```

---


```graphql
 width: 1200
  placeholder: BLURRED
  formats: [AUTO, WEBP, AVIF]
  quality: 80
```
