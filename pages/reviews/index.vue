<template>
  <div>
    <h2 class="text-2xl text-center">Reviews</h2>
    <form class="text-center relative w-60 mx-auto mt-4">
      <input v-model="searchText" type="text" class="border border-gray-200 shadow rounded-3xl mx-auto py-1 pl-8"
        placeholder="Search">
      <input type="button" class="absolute right-0 h-full rounded-r-3xl px-4" value="Search">
    </form>
    <ul>
      <li v-for="element in filteredList">
        <nuxt-link :to="element.path">
          {{ element.title }}
        </nuxt-link>
      </li>
    </ul>
    <review-card-list :reviews="reviews" />
  </div>
</template>

<script>
export default {
  async asyncData({ $content }) {
    const reviews = await $content('reviews').fetch()
    return { reviews }
  },
  data() {
    return {
      searchText: '',
      filteredList: []
    }
  },
  watch: {
    searchText(newSearch, oldSearch) {
      this.search(newSearch)
    }
  },
  methods: {
    async search(text) {
      const searchedReviews = await this.$content('reviews').only(['title']).search(text).fetch()
      this.filteredList = searchedReviews
    }
  }

}
</script>
