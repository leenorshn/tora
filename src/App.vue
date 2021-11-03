<template>
  <div class="max-w-3xl mx-auto bg-gray-300 pt-20 min-h-screen px-8">
      <div class="flex items-center space-x-4">
          <input v-model="state.newMessage" class="px-4 py-3 flex-1 rounded-md shadow" type="text" placeholder="Entrer votre message">
      <button @click="addMessage" class="bg-blue-600 text-white px-8 py-3 rounded-md">Ajouter</button>
      </div>
      <div class="flex flex-col py-4">
      <div
        v-for="(p, i) in state.messages"
        :key="i"
        class="flex items-center space-x-4 mt-1  rounded-md bg-white shadow"
      >
        <div class="flex-1 flex items-center">
          <div class="px-8 py-4  rounded-l-md text-white bg-blue-700">
          <h2>{{ i +1}}</h2>
        </div>
        <h2 class="text-xl flex-1 ml-4 font-semibold text-blue-600">{{ p.message }}</h2>
        </div>
        <div class="pr-4">
          <button  class="text-red-500">Effacer</button>
        </div>
      </div>
      </div>
  </div>
</template>

<script setup>
import {reactive} from 'vue'
const state=reactive({
    messages:[],
    newMessage:''
})
function addMessage(){
    state.messages.unshift({
        id:Date.now(),
        message:state.newMessage
    })
    state.newMessage=""
}


</script>

<style>

</style>