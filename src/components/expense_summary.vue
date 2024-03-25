<script setup>
const props = defineProps({
  TIncome: Number,
  TSpent: Number
})

</script>

<template>
  <div class="summary">
    <div class="card income">
      <p>income</p>
      <h1>${{ TIncome }}</h1>
      <hr>
      <h6>this month</h6>
    </div>
    <div class="card spent">
      <p>Spent</p>
      <h1>${{ TSpent }}</h1>
      <hr>
      <h6>past month</h6>
    </div>
  </div>
</template>

<style scoped>
.income h1 {
  color: green;
}

.spent h1 {
  color: rgb(236, 37, 37);
}
</style>
