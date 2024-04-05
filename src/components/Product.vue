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
    fruits: Object, 
  }
};
</script>


<template>

<Name :value='fruits.name' />
<Price :value='fruits.price' />
<Description :value='fruits.description' />
<br/><br/>

</template>