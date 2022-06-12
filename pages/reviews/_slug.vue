<template>
  <div class="px-24">
    <nuxt-link to="/reviews">Back to Reviews</nuxt-link>
    <h1 class="text-6xl font-semibold my-16">{{ review.title }}</h1>
    <div class="flex mb-10">
      <div class="mr-3">
        <span class="uppercase text-gray-700">country</span>
        <p class="font-semibold text-2xl">{{ review.country }}</p>
      </div>
      <div class="mr-3">
        <span class="uppercase text-gray-700">type</span>
        <p class="font-semibold text-2xl">{{ review.type }}</p>
      </div>
    </div>
    <nuxt-content :document="review" />
    <img class="w-full mt-6" :src="review.img" :alt="review.title">
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

<style >
.nuxt-content h2 {
  font-weight: bold;
  font-size: 1.5rem;
  margin-bottom: 2rem;
  margin-top: 2rem;
}
</style>