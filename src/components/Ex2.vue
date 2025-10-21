<script>
    export default {
    data() {
        return {
        items: ['keyboard', 'mouse', 'iPhone', 'macbook', 'adapter'],
        newItem: '' // to store what user types in input
        }
    },
    methods: {
        addItem() {
        if (this.newItem.trim() !== '') {
            this.items.push(this.newItem.trim())
            this.newItem = '' // clear input after adding
        }
        },
        deleteItem(index) {
        this.items.splice(index, 1)
        }
    }
    }
</script>

<template>
  <h2>Shopping Cart</h2>

  <ul>
    <li v-for="(item, index) in items" :key="index">
      {{ item }}
      <button @click="deleteItem(index)">Delete</button>
    </li>
  </ul>

  <input v-model="newItem" type="text" placeholder="Add new item" />
  <button @click="addItem">Add!</button>
</template>
