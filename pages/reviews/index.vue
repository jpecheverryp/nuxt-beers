<template>
  <div>
    <h2 class="text-2xl text-center">Reviews</h2>
    <form class="text-center relative w-60 mx-auto mt-4">
      <input type="text" class="border border-gray-200 shadow rounded-3xl mx-auto py-1 pl-8" placeholder="Search">
      <input type="button" class="absolute right-0 h-full rounded-r-3xl px-4" value="Search">
    </form>

    <review-card-list :reviews="reviews" />
  </div>
</template>

<script>
export default {

  async asyncData({ $content }) {
    const reviews = await $content('reviews').fetch()
    return { reviews }
  }
}
</script>
