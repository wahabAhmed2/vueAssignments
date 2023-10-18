<template>
  <div>
    <h2>{{ message }}</h2>
    <input v-model="inputValue" @keyup.enter="addItem" placeholder="Enter a new item">
    <button @click="addItem">Submit</button>
    <ul>
      <li v-for="(item, index) in items" :key="index">{{ item }} <button @click="deleteItem(index)">delete</button></li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      message: 'Todo List',
      inputValue: '',
      items: [], 
    };
  },
  methods: {
    addItem() {
      if (this.inputValue) {
        this.items.push(this.inputValue);
        this.inputValue = '';
      }
    },
    deleteItem(index){
      this.items.splice(index,1)
    }
  },
};
</script>

<style scoped>

</style>