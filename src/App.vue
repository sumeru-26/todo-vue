<script setup>

import { ref } from 'vue'

import TodoItem from './components/TodoItem.vue'
import InputForm from './components/InputForm.vue'

const items = ref(loadList())

function shiftUp(item, index) {
    if (index == 0) return
    items.value.splice(index,1)
    items.value.splice(index-1,0,item)
    saveList()
}

function shiftDown(item, index) {
    if (index == items.value.length-1) return
    items.value.splice(index,1)
    items.value.splice(index+1,0,item)
    saveList()
}

function add(item) {
  items.value.push(item)
  saveList()
}

function remove(index) {
  items.value.splice(index,1)
  saveList()
}

function saveList() {
  localStorage.setItem("list", JSON.stringify(items.value))
}

function loadList() {
  const loaded = JSON.parse(localStorage.getItem("list"))
  console.log(loaded)
  if (loaded === null) return []
  return loaded
  
}

</script>

<template>
  <header>
    <h1>Todo</h1>
  </header>

  <main>
    <TodoItem
      v-for="(item, index) in items" :key="index"
      :item=item
      :index=index
      @up="shiftUp"
      @down="shiftDown"
      @remove="remove"
    />
    <br><br>
    <InputForm
      @add="add"
    />
  </main>
</template>

<style scoped>
</style>
