<template>
  <DefaultCard :img-url="imgUrl">
    <div class="slot">
      <StarScore :card-name="'starCard'" :score="score" />
      <slot />
    </div>
  </DefaultCard>
</template>

<script>
import DefaultCard from './DefaultCard.vue'
import StarScore from './StarScore.vue'

export default {
  name: "StarCard",
  components: {
    DefaultCard,
    StarScore
  },
  props: {
    score: String,
    imgUrl: {
      type: String,
      default: ''
    }
  }
};
</script>

<style lang="scss" scoped>
.slot {
  padding: 10px;
  border-bottom: 1px solid grey;
}
</style>
