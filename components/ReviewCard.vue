<template>
  <nuxt-link :to="`/reviews/${review.slug}`">
    <div class="shadow hover:bg-green-50 p-3">
      <img :src="review.img" :alt="review.title" class="h-20 w-20">
      <h3 class="font-bold">{{ review.title }}</h3>
      <p>{{ review.description }}</p>
      <span class="text-green-500 text-right block right-0">READ MORE</span>
    </div>
  </nuxt-link>
</template>

<script>
export default {
  props: ['review']
}
</script>

