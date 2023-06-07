<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: "App",
  data() {
    return {
      name: "Esteban",
      count: 0,
      myNum: 0,
      myList: ["Pierce", "Kali"],
      myListObj: [
        {
          id: 1,
          name: "Sabine",
          age: 39
        },
        {
          id: 2,
          name: "Rv",
          age: 33
        },
      ]
    }
  },
  methods: {
    add(num: number): number {
      this.myNum = num + 1
      return this.myNum;
    },
    changeName() {
      this.name = "Douglas"
      return this.name;
    },
    decrement() {
      this.count -= 1
      return this.count;
    }
  }
})
</script>

<template>
  <header>
    <h2 v-text="name"></h2>
    <h2>Hello {{ name }}</h2>
    <button v-on:click="name = 'Alphonso'">Change Name</button>
    <button v-on:click="changeName">Change Again</button>
  
    <h2>{{ count }}</h2>
    <button @click="count++">Increment {{ count }}</button>
    <button @click="decrement">Decrement {{ count }}</button>

    <h2>{{ myNum }}</h2>
    <button @click="add(3)">Add</button>

    <h2 v-text="myList[1]"></h2>

    <div v-for="item in myListObj" :key="item.id">
      <div v-if="item.name === 'Sabine'">{{ item.name }} {{ item.age }}</div>
    </div>
    
  </header>
</template>

<style scoped>
  header {
    line-height: 1.5;
    max-height: 100vh;
  }
</style>
