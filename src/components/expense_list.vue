<script setup>

const props = defineProps({
  vlist: Object
})

</script>



<template>
  <div class="list-container">
    <div class="item" v-for="(money, index) in vlist" :key="index">
      <button @click="$emit('deleteItem', money)">x</button>
      <div :style="{ backgroundColor: money.type === 'income' ? 'rgb(75, 139, 19)' : 'rgb(246, 39, 39)' }"
        class="color">
      </div>
      <h4>${{ money.amount }}</h4>
      <p>{{ money.title }}</p>

    </div>

  </div>
</template>

<style scoped>
.list-container {
  padding: 2rem;
  background-color: white;
  border-radius: 1rem;
  width: 35rem;
  border: 1px solid orange;
  height: 10rem;
  overflow-y: scroll;
}

.list-container .item {
  margin-bottom: 0.5rem;
  display: flex;
  height: 2rem;
  background-color: bisque;
  align-items: center;
  justify-content: start;
  border-radius: .3rem;
  overflow: hidden;
}

.list-container .item h4 {
  margin-right: 2rem;
  margin-left: 2rem;
}

.list-container .item p {
  max-width: 100%;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  padding-right: 1.3rem;
}


.color {
  padding: 1rem .3rem;
  background-color: rgb(76, 220, 9);
  width: fit-content;
  height: fit-content;
}

button {
  background-color: rgb(237, 237, 237);
  color: rgb(112, 112, 112);
  border: none;
  padding: 1rem;
  transition: 0.4s;
}

button:hover {
  background-color: rgb(255, 35, 35);
  color: aliceblue;
  padding-right: 7rem;
}
</style>
