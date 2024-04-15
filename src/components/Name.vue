<script>

export default {
  props: {
    value: String,
  }
};
</script>

<template>
    <span class="green">{{ value }}</span>

</template>

<style>
.green{
color: green;
text-transform: capitalize;
}
</style>