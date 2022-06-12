<template>
  <ul class="px-5">
    <li v-for="review in reviews">
      <ReviewCard :review="review" />
    </li>
  </ul>
</template>

<script>
export default {
  props: ["reviews"],
}
</script>
