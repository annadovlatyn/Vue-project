<script>
export default {
  data() {
    return {
      value: 0,
      rate: 400,
      mode: 'AMD'
    }
  },
  methods: {
    handleInput(event) {
      this.value = event.target.value
    },
    handleInputFocus() {
      if (+this.value === 0) {
        this.value = ''
      }
    },
    toggleMode(){
        if(this.mode === 'AMD'){
            this.mode = 'USD';
        } else {
            this.mode = 'AMD';
        }
        this.value = 0;
    }
  }
}
</script>

<template>
  <main>
  <div v-if="mode === 'AMD'">
    <h3 class="exchange-mode">AMD -> USD</h3>
    <input 
    type="number" 
    :value="value" 
    @input="handleInput" 
    @focus="handleInputFocus" 
    class="input-active"
    />
    <input class="input-readonly" type="number" readonly :value="value / rate" />
    <button class="btn-toggle" @click="toggleMode" >USD -> AMD</button>
  </div>

  <div v-else>
    <h3 class="exchange-mode">USD -> AMD</h3>
    <input 
    type="number" 
    :value="value" 
    @input="handleInput" 
    @focus="handleInputFocus"
    class="input-active"
    />
    <input class="input-readonly" type="number" readonly :value="value * rate" />
    <button class="btn-toggle" @click="toggleMode" >AMD -> USD</button>
  </div>
</main>
</template>


<style scoped>
.exchange-mode {
  margin: 25px 10px 0px;
  font-size: 20x;
  font-weight: bold;
}
.input-active {
  font-size: 18px;
  padding: 5px 10px;
  margin: 10px;
  border: 2px solid gray;
}
.input-readonly {
  font-size: 18px;
  padding: 5px 10px;
  margin: 10px;
  background-color:#f4f4f4;
  border-color: #cacaca;
}
.btn-toggle {
  font-size: 16px;
  padding: 8px 10px;
  display: block;
  margin: 10px;

}


</style>