<template>
  <div class="container">
    <item v-for="story in stories" :key="story.data.id" :story="story"></item>
  </div>
</template>

<script>
import Item from '@/components/Item'
export default {
  name: 'New',
  components: {
    Item
  },
  data: function () {
    return {
      err: '',
      stories: this.$store.state.newStories
    }
  },
  created: function () {
    if (this.$store.state.newStories.length === 0) this.$store.dispatch('fetch_new_stories')
  }
}
</script>

<style scoped>

</style>
