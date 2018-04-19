<template>
  <div class="container">
    <item v-for="story in stories" :key="story.data.id" :story="story"></item>
  </div>
</template>

<script>
import Item from '@/components/Item'
export default {
  name: 'Homepage',
  components: {
    Item
  },
  data: function () {
    return {
      err: '',
      stories: this.$store.state.topStories
    }
  },
  created: function () {
    if (this.$store.state.topStories.length === 0) this.$store.dispatch('fetch_top_stories')
  }
}
</script>

<style scoped>

</style>
