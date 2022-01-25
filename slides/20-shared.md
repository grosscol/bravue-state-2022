---
author: Colin Gross
title: BraVue
date: 2022-01-25
---

#
<h3>Shared Components</h3>

- Histogram component on gene and region pages.
- Mostly identical code.
- Differ on parameters and API endpoint.

![](assets/svgexport-12.svg){ width=800px }

## 
### Base Component
```js
// BaseSnvCount methods
  methods: {
    load: function(width) {
      axios.post(this.url, { ...}
      ...
    },
    format_y_ticks: function(value) {...},
    initializeSVG:  function() {...},
    draw:           function() {...},
    drawHistogram:  function() {...},
    drawVariants:   function() {...},
    clearDrawing:   function() {...},
  },
```

##
### Gene Variants Histogram

- Extends BaseSnvCount component
- Declares required ensembleId
- Defines api endpoint
```js
<script>
import BaseSnvCount from '@/components/histogram/BaseSnvCount.vue'

export default {
  name: "GeneSnvCount",
  extends: BaseSnvCount,
  inject: {
    ensemblId: {default: '' }
  },
  computed: {
    url() { return `${this.api}/variants/gene/snv/${this.ensemblId}/histogram` }
  }
}
</script>
```

## 
### Region Variants Histogram

- Also extends BaseSnvCount component
- Declares required position data
- Defines api endpoint
```js
<script>
import BaseSnvCount from '@/components/histogram/BaseSnvCount.vue'

export default {
  name: "RegionSnvCount",
  extends: BaseSnvCount,
  inject: {
    chrom: {default: '11'},
    start: {default: 200000},
    stop:  {default: 201000},
  },
  computed: {
    url() { return `${this.api}/variants/region/snv/${this.chrom}-${this.start}-${this.stop}/histogram` }
  }
}
</script>
```

##
### Clear Components
```html
<GeneSnvCount 
  :segmentBounds="segmentBounds" 
  :segmentRegions="segmentRegions"
  :filters="filterArray" 
  :visibleVariants="visibleVariants"/>
```

```html
<RegionSnvCount
  :segmentBounds="segmentBounds" 
  :segmentRegions="segmentRegions"
  :filters="filterArray" 
  :visibleVariants="visibleVariants"/>
```
