---
author: Colin Gross
title: BraVue
date: 2022-01-25
---

# 
<h3>Drawbacks</h3>

- Upgrade entire toolchain for all components.
- UI not locked behind auth.
- Loss\* of parsing params from path
  - Can be reworked if required

# 
<h3>Future Work</h3>
- eQTL display: 
  - specialized region view 
  - region view with different input
- Separation of concerns: 
  - get data 
  - display data
- Single Page App investigation:
  - persist data to avoid reload on "back"
  - load times
  - dist size
