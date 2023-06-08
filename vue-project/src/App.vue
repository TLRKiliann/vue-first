<script lang="ts">
import { defineComponent } from 'vue';
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
      ],
      status: 'status',
      testColor: 'testColor',
      textStyle: {color: "orange"},
      isPromoted: 'isPromoted',
      isNotPromoted: 'isNotPromoted'
    }
  },
  methods: {
    changeName(): string {
      this.name = "Douglas"
      return this.name;
    },
    decrement(): number {
      this.count -= 1
      return this.count;
    },
    add(num: number): number {
      this.myNum = num + 1
      return this.myNum;
    },
  }
})
</script>

<template>
  <header>
    <h2 v-text="name"></h2>
    <h2>Hello {{ name }}</h2>

    <button v-on:click="name = 'Alphonso'">Change Name</button>
    <button v-on:click="changeName">Change Again</button>

    <h2 v-bind:class="status">La couleur cyan</h2>
    <h2 v-bind:class="testColor">La couleur lightgreen</h2>
    <h2 v-bind:style="textStyle">Un autre style</h2>

    <h2 v-bind:class="count > 0 ? 'isPromoted' : 'isNotPromoted'">{{ count }}</h2>

    <button @click="count++">Increment {{ count }}</button>
    <button @click="decrement">Decrement {{ count }}</button>

    <h2>{{ myNum }}</h2>
    <button @click="add(3)">Add</button>

    <h2 v-text="myList[1]"></h2>

    <div v-for="item in myListObj" :key="item.id">
      <div v-if="item.name === 'Sabine'">Name: {{ item.name }} - Age: {{ item.age }} years</div>
    </div>
    
  </header>
</template>

<style scoped>
  header {
    line-height: 1.5;
    max-height: 100vh;
  }
  .testColor {
    color: lightgreen;
  }
  .status {
    color: cyan;
  }
  .isPromoted {
    color: cyan;
  }
  .isNotPromoted {
    color: yellow;
  }
</style>
