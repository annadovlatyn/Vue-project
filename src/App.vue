<script>
export default {
  data() {
    return {
      email: '',
      isEmailValid: false,
    };
  },
  methods: {
    openEmailPrompt() {
      let email = prompt('Input your email');
      if (!email) {
        this.isEmailValid = false;
        return;
      }
      email = email.trim();
      this.email = email;
      console.log(email);
      const isValid = this.checkIsEmailValid(email);
      this.isEmailValid = isValid;
    },
    checkIsEmailValid(email) {
      const reg = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
      return reg.test(email);
    },
    reset() {
      this.email = '';
      this.isEmailValid = false;
    }
  }
}
</script>

<template>

  <main>
    <button @click="openEmailPrompt()" class="btn_input">Input your email</button>
    <button @click="reset()" class="btn-reset">Reset</button>
    <h1 :class="isEmailValid ? 'green' : 'red'" v-if="email">{{ email }}</h1>
    <h4 v-if="email" class="info-text">{{ `The email is ${isEmailValid ? 'valid' : 'invalid'}` }}</h4>
  </main>
</template>

<style scoped>
.red{
  border: 1px solid red;
  padding: 5px 20px;
  margin: 10px;
}

.green{
  border: 1px solid green;
  padding: 5px 20px;
  margin: 10px;
}
.btn_input {
  padding: 10px 20px;
  font-size: 20px;
  margin: 10px;
}
.info-text {
  margin: 10px 15px;
  font-size: 17px;
  color: #000;
}
.btn-reset {
  padding: 11px 15px;
  font-size: 18px;
}
</style>