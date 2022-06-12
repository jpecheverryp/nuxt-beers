<template>
  <div class="shadow p-4">
    <!-- <pre>{{ beer }}</pre> -->
    <img :src="beer.image_url" :alt="beer.name">
    <h3 class="text-xl font-bold">{{ beer.name }}</h3>
    <p class="text-gray-600">{{ beer.category }}</p>
    <div class="flex gap-2 justify-center mt-5">
      <span class="bg-gray-200 px-3 py-1 block rounded-xl ">{{ beer.type }}</span>
      <span class="bg-gray-200 px-3 py-1 block rounded-xl ">{{ beer.brewer }}</span>
      <span class="bg-gray-200 px-3 py-1 block rounded-xl ">{{ beer.abv }}</span>
    </div>
  </div>
</template>

<script>
export default {
  props: ['beer']
}
</script>
