<template>
  <div>
    <h2 class="text-2xl text-center">Reviews</h2>
    <form class="text-center">
      <input type="text" class="border border-gray-200 shadow rounded-3xl mx-auto py-1 px-3" placeholder="Search">
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
