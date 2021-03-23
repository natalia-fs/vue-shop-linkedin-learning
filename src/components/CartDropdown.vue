<template>
  <div class="dropdown-clip" v-if="cart.length > 0">
    <transition name="dropdown">
      <div
        v-if="displayCart"
        class="list-group bg-white"
        aria-labelledby="cartDropdown"
      >
        <div v-for="(item, index) in cart" :key="index">
          <div class="dropdown-item text-nowrap text-right align-middle">
            <span class="badge bg-success align-text-top mr-1">
              {{ item.qty }}
            </span>
          </div>
          {{ item.product.name }}
          <b> <currency :amt="item.qty * Number(item.product.price)"> </currency> </b>

        </div>
      </div>
    </transition>
  </div>
</template>

<script>
import Currency from '@/components/Currency'
export default {
  props: ['cart', 'displayCart'],
  components: {
    Currency
  }
}
</script>

<style>
.dropdown-clip {
  overflow: hidden;
}
.dropdown-enter-active,
.dropdown-enter-active {
  transition: all 0.5s ease-in-out;
  transform: auto;
}

.dropdown-enter-from,
.dropdown-leave-to {
  opacity: 0;
  transform: translateY(-300px);
}
</style>