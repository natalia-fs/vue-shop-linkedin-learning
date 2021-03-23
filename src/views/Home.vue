<template>
  <section class="container">
    <range-selector :products="filteredProducts" v-model="max"/>
    <product-list :products="filteredProducts" />
  </section>
</template>

<script>
import ProductList from '@/components/ProductList'
import RangeSelector from '@/components/RangeSelector'
export default {
  name: 'Home',
  data: () => {
    return {
      max: 50,
      cart: [],
    }
  },
  props: ['products'],
  components: {
    // eslint-disable-next-line vue/no-unused-components
    ProductList,
    // eslint-disable-next-line vue/no-unused-components
    RangeSelector
  },
  
  computed: {
    filteredProducts() {
      return this.products.filter(item => item.price < Number(this.max))
    },
  },
}
</script>
