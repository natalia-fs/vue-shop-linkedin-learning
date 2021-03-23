<template>
  <span style="padding-right: 1rem">
    {{ dollar(amt) }}
  </span>
</template>

<script>
export default {
  props: ['amt'],
  methods: {
    dollar(value) {
      return ' $ ' + Number.parseFloat(value).toFixed(2)
    }
  }
}
</script>

<style></style>