<template>
  <DefaultCard>
    <StarScore :card-name="'starCard'" :score="score" />
    <div class="card-description">Lorem Ipsum is simply dummy text</div>
  </DefaultCard>
</template>

<script>
import DefaultCard from './DefaultCard.vue'
import StarScore from './StarScore.vue'

export default {
  name: "StarDescriptCard",
  components: {
    DefaultCard,
    StarScore
  },
  props: {
    score: String
  }
};
</script>

<style scoped lang="scss">
</style>
