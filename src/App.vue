<template>

  <div class="pt-16 mx-auto max-w-3xl">
    <h2 class="text-2xl font-semibold text-blue-700">{{name}}</h2>
    <p>{{age}}</p>
    <div class="flex items-center space-x-4">
      <h3>{{address.city}}</h3>
      <h3>{{address.street}}</h3>
    </div>
    <div 
    class="flex items-center space-x-4 mt-2 bg-blue-600 text-white rounded-md shadow-md"
    v-for="(p ,i) in data" :key="i">
      <span>{{i}}</span>
      <img class="h-20 w-20 object-cover object-center" :src="p.img" alt="">
      <div>
        <h3>{{p.location}}</h3>
        <p>{{p.distance}}</p>
      </div>
    </div>
  </div>
    
</template>

<script setup>
import data from "./data"
  let name="Victor"
  let age=50
  const isOnline=true
  let address={
    city:"Butembo",
    street:"Auberge Rue"
  }
</script>

<style>

</style>
