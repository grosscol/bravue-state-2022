---
author: Colin Gross
title: BraVue
date: 2022-01-25
---

# 
<h3>Tests</h3>
- Vue supports unit and component tests.
- Handy one liner to run tests when files change:

```sh
fd '\.(js|Vue|vue)$' . | entr -c npm run test:unit
```

## 
### Test Component Functions Directly
```js
//describe('SearchBox.vue query parsing.
  it('tickets a dbSNP reference query with endpoint: variant', () => {
    const rsid_result = wrapper.vm.queryToResultTicket('rs12345678')
    expect(rsid_result.endpoint).to.equal('variant')
  })

  it('tickets a range query with endpoint: region', () => {
    const range_result = wrapper.vm.queryToResultTicket('chr11:10,500,100-10,503,000')
    expect(range_result.endpoint).to.equal('region')
  })

  it('defaults to ticket query with endpoint: gene', () => {
    const range_result = wrapper.vm.queryToResultTicket('HBBP1')
    expect(range_result.endpoint).to.equal('gene')
  })
```

## 
### Test Component UI Behavior

```js
describe('QualityFilterButton dropdown', () => {
  it('toggles showDropDown when button is clicked', () => {
    const wrapper = shallowMount(QualityFilterButton, {})

    const initialState = wrapper.vm.showDropDown

    wrapper.find('button').trigger('click')
    expect(wrapper.vm.showDropDown).to.equal(!initialState)

    wrapper.find('button').trigger('click')
    expect(wrapper.vm.showDropDown).to.equal(initialState)
  })
})
```
