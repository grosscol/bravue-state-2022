---
author: Colin Gross
title: BraVue
date: 2022-01-25
---

# 
<h3>Composition</h3>

- Wrap functionality into discrete components
- Easier to compose different dashboards

##
### Gene Dashboard
```html
<template>
    <GeneInfo :geneData="geneData"/>

    <ToggleList list-title="Panels" list-group="showPanels"
      :list-vars="showPanels"/>
    <ToggleList list-title="Columns" list-group="showCols" 
      :list-vars="showCols"/>

    <GeneSummary :filterArray='filterArray' />

    <SeqDepth 
      :hoveredVariant="hoveredVariant" :segmentBounds="segmentBounds" 
      :segmentRegions="segmentRegions" :givenWidth="childWidth"
      :givenMargins="childMargins"/>

    <TranscriptBars  :geneData="geneData"
      :hoveredVariant="hoveredVariant" :segmentBounds="segmentBounds" 
      :segmentRegions="segmentRegions" :givenWidth="childWidth" 
      :givenMargins="childMargins" />

    <GeneSnvCount  
      :segmentBounds="segmentBounds" 
      :segmentRegions="segmentRegions" :givenWidth="childWidth" 
      :givenMargins="childMargins"
      :filters="filterArray" :visibleVariants="visibleVariants"/>

    <BpCoordBar :segmentBounds="segmentBounds" 
      :segmentRegions="segmentRegions" 
      :givenWidth="childWidth" :givenMargins="childMargins" />

    <FilterBar @filterChange='handleFilterChange'/>

    <GeneSNVTable :filters="filterArray" :doDownload="doDownload"/>
</template>

```

