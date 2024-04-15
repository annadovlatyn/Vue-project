<script>
import Name from './Name.vue'
import Price from './Price.vue'
import Description from './Description.vue'

export default {
  components: {
    Name,
    Price,
    Description,
  },
  props:{
    fruit: Object, 
  },
  methods: {
    onButtonClick(){
      this.$emit('CurrencyChange')
    }
  }
};
</script>


<template>

  <div>
    <Name :value='fruit.name' /> <Price :value='fruit.price' /> <Description :value='fruit.description' /> 
    <button @click="onButtonClick">Change the currency</button>
  </div>

</template>