<script setup>
defineProps({
  id: Number,
  image: String,
  name: String,
  status: String,
  species: String,
  lastLocation: String,
  firstLocation: String
})
</script>
<template>
  <div
    class="w-fit bg-[#3C3E44] rounded-lg flex-col flex text-white m-3 xl:flex-row xl:w-[600px] xl:h-[220px] overflow-clip transition hover:-translate-y-1.5">
    <div class="flex-shrink-0 ">
      <img :src="image" :alt="name"
           class="object-cover max-w-full max-h-full ml-auto mr-auto">
    </div>
    <div class="font-medium flex flex-col justify-between m-3">
      <div>
        <div class="text-3xl font-bold max-w-[300px]">{{ name }}</div>
        <div class="flex items-center gap-0">
          <div v-if="status === 'Alive'" class="w-[10px] h-[10px] bg-[#55CC44] rounded-full mr-2"></div>
          <div v-else-if="status === 'Dead'" class="w-[10px] h-[10px] bg-[#D63D2E] rounded-full mr-2"></div>
          <div v-else></div>
          <div>{{ status }} - {{ species }}</div>
        </div>
      </div>
      <div>
        <div class="text-[#9E9E9E]">Last known location:</div>
        <div class="font-normal">{{ lastLocation }}</div>
      </div>
      <div>
        <div class="text-[#9E9E9E]">First seen in:</div>
        <div class="font-normal">{{ firstLocation }}</div>
      </div>
    </div>
  </div>
</template>