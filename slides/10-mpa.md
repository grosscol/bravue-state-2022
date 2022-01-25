---
author: Colin Gross
title: BraVue
date: 2022-01-25
---

# 
<h3>Multipage Application</h3>
```sh
bravue/src/pages/
├── gene
│   ├── gene.html
│   ├── GenePage.vue
│   └── main.js
├── home
│   ├── home.html
│   ├── Home.vue
│   └── main.js
├── region
│   ├── region.html
│   ├── RegionPage.vue
│   └── main.js
└── variant
    ├── variant.html
    ├── Variant.vue
    └── main.js
```

## vue.config.js

```js
module.exports = {
  publicPath: '/',
  pages: {
    home: {
      entry:    'src/pages/home/main.js',
      template: 'src/pages/home/home.html',
      filename: 'index.html',
      title:    'Bravo:Home',
      chunks:   ['chunk-vendors', 'chunk-common', 'home']
    variant: {
      entry:    'src/pages/variant/main.js',
      template: 'src/pages/variant/variant.html',
      filename: 'variant.html',
      title:    'Bravo:Variant',
      chunks:   ['chunk-vendors', 'chunk-common', 'variant']
```
