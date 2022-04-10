<template>
  <div>
    <h1>Fizz Buzz</h1>
  </div>
  <form class="container" @submit.prevent="submitForm">
    <div>
      <label for="user-number">Enter Number</label>
      <input type="number" id="user-name" v-model.trim="number" min="1" />
      <button type="submit">Fizz Buzz</button>
    </div>
  </form>
  <div class="container">
    <span v-if="valuesList.length > 0">{{ valuesList.join(' ') }}</span>
    <span v-else>Enter a number. Start a game!</span>
  </div>
</template>

<script>
export default {
  data() {
    return {
      number: null,
      valuesList: [],
    };
  },
  methods: {
    submitForm() {
      if (this.valuesList.length > 0) {
        this.valuesList = [];
      }
      for (let i = 1; i <= this.number; i++) {
        if (i % 3 === 0 && i % 5 === 0) {
          this.valuesList.push('FIZZBUZZ');
        } else if (i % 3 === 0) {
          this.valuesList.push('FIZZ');
        } else if (i % 5 === 0) {
          this.valuesList.push('BUZZ');
        } else {
          this.valuesList.push(i);
        }
      }
    },
  },
};
</script>

<style scoped>
.container {
  margin: 2rem auto;
  max-width: 40rem;
  border-radius: 12px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.25);
  padding: 2rem;
  background-color: rgb(255, 255, 255);
}

input {
  display: block;
  width: 50%;
  margin-top: 0.5rem;
  margin-bottom: 0.5rem;
}

button {
  background-color: #4caf50;
  border: none;
  color: white;
  padding: 15px 32px;
  text-align: center;
  text-decoration: none;
  font-size: 16px;
  cursor: pointer;
}

label {
  margin: 0.5rem auto;
  font-weight: bold;
  font-size: 20px;
}
</style>
