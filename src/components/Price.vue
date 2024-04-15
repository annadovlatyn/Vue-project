<script>

export default {
  props: {
    value: String,
  }
};
</script>

<template>
    <span class="price-style"> - {{ value }}</span>

</template>

<style>
.price-style {
  font-weight: bold;
  color: red;
}
</style>