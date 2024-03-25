<script setup>
import { ref, computed } from 'vue';
const x = ref()
const y = ref()

</script>

<template>
  <div class="input-area">
    <div class="text-number">
      <input v-model="x" type="number" placeholder="$$$">
      <input v-model="y" type="text" placeholder="brief">
    </div>
    <div class="buttons-area">
      <button @click="$emit('updateWallet', x, y, 'income')" class="income-btn">income</button>
      <button @click="$emit('updateWallet', x, y, 'spent')" class="spent-btn">spent</button>
    </div>
  </div>
</template>

<style scoped>
.text-number {
  display: flex;
  flex-direction: row;
  background-color: rgb(255, 216, 175);
  padding: 1rem;
  border-radius: 1rem;
}

.input-area {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  margin-bottom: 2rem;
}

.buttons-area {
  display: flex;
  justify-content: center;
  width: 100%;
  padding-top: 1rem;

}

button {
  padding: 0.3rem 1.2rem;
  font-size: 1.2rem;
  border-style: none;
  color: white;
  font-weight: 500;
  transition: 0.2s;
  height: fit-content;
}

input {
  width: fit-content;
  padding: 0.8rem;
  border-radius: 1rem;
  border: 1px solid orangered;
  font-size: 1.3rem;
  color: orangered;
  margin-right: 1rem;
}

input[type=text] {
  width: 20rem;
  color: rgb(63, 63, 63);
}

input[type=number] {
  width: 5rem;
  font-weight: 600;
}


input:focus {
  font-weight: 500;

}

.income-btn {
  background-color: rgb(75, 139, 19);
  border-radius: 0.8rem 0 0 0.8rem;
}

.spent-btn {
  background-color: rgb(246, 39, 39);
  border-radius: 0 0.8rem 0.8rem 0;
}

button:hover {
  opacity: 0.7;
  background-color: black;
}
</style>
