<template>
  <div>
    <nuxt-link to="/reviews">Back to Reviews</nuxt-link>
    <h1 class="text-6xl font-semibold mb-16">{{ review.title }}</h1>
    <div class="flex">
      <div class=" mr-3">
        <span class="uppercase">country</span>
        <p class="font-semibold text-2xl">{{ review.country }}</p>
      </div>
      <div class=" mr-3">
        <span class="uppercase">type</span>
        <p class="font-semibold text-2xl">{{ review.type }}</p>
      </div>
    </div>
    <nuxt-content :document="review" />
    <img class="w-full" :src="review.img" :alt="review.title">
  </div>
</template>

<script>
export default {
  async asyncData({ params, $content }) {
    const data = await $content('reviews').where({ 'slug': params.slug }).fetch()
    const review = data[0]
    return { review }
  }
}
</script>

<style scoped>
nuxt-content.h2 {
  font-size: 4rem;
}
</style>
