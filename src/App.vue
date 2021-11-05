<template>
  <div class="pt-16 mx-auto max-w-4xl px-10 bg-gray-100 min-h-screen">
    <div class="flex space-x-4">
      <input
        type="text"
        v-model="state.newMessage"
        @keydown.enter="addMessage"
        placeholder="Entrer le donnee"
        class="px-4 py-2 border rounded-md shadow flex-1"
      />
      <button
        @click="addMessage"
        class="px-5 py-2 rounded-md bg-blue-600 text-white"
      >
        Ajouter
      </button>
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
          <button @click="deleteMessage(p.id)" class="text-red-500">Effacer</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { reactive } from "vue";


  const state=  reactive({
      messages:[],
      newMessage:''
    })
  
  
    
    function addMessage() {
      state.messages.unshift({
        id:Date.now(),
        message:state.newMessage
      });
      state.newMessage=""
    }
    function deleteMessage(id){
     state.messages= state.messages.filter(msg=>msg.id!==id)
    }

    

</script>

<style>
</style>
