<script setup>
import expense_list from './components/expense_list.vue'
import expense_summary from './components/expense_summary.vue'
import expense_input from './components/expense_input.vue'

import { ref, computed } from 'vue';
const list = ref([]);

function updateWallet(x, y, i) {
  list.value.push({
    type: i,
    amount: x,
    title: y
  })
  console.log(list.value)
}

function deleteItem(selectedItem) {
  list.value = list.value.filter((item) => item !== selectedItem)
  console.log(`After deleting item${index}`, list.value)
}

const totalIncome = computed(() => {
  let tIncome = 0
  if (list.value)
    for (const item of list.value) {
      tIncome += item.type === 'income' && item.amount
    }
  return tIncome
})



const totalSpent = computed(() => {
  let tSpent = 0
  if (list.value)
    for (const item of list.value) {
      tSpent += item.type === 'spent' && item.amount
    }
  return tSpent
})


</script>


<!-- The Structure of the project -->

<template>
  <header>
    <div class="title">Expense Tracker</div>
  </header>
  <main>
    <expense_summary :TIncome="totalIncome" :TSpent="totalSpent" />
    <expense_input @update-Wallet="updateWallet" />
    <expense_list :vlist="list" @delete-Item="deleteItem" />
  </main>
</template>

<style scoped></style>
