---
layout: layouts/post.njk
title: Configure Eleventy to copy folders to output
description: Details of how to configure the dot eleventy dot js file
date: 2021-01-01
featuredImage: /images/uploads/PassthroughFileCopy.png
---
## Manual Passthrough File Copy (Faster) New in v0.2.14

[Eleventy documentation](https://www.11ty.dev/docs/copy/)

Searching the entire directory structure for files to copy based on file extensions is not optimal with large directory structures. 

If we know what non-template static content we want to appear in our output, we can opt-in to specify files or directories for Eleventy to copy. This will probably speed up your build times.

Passthrough File Copy entries are relative to the root of your project and not your Eleventy input directory.

`Filename .eleventy.js`

```js
module.exports = function(eleventyConfig) {
  // Output directory: _site

  // Copy `img/` to `_site/img`
  eleventyConfig.addPassthroughCopy("img");
  
  // Copy `css/fonts/` to `_site/css/fonts`
  // If you use a subdirectory, it’ll copy using the same directory structure.
  eleventyConfig.addPassthroughCopy("css/fonts");
};
```