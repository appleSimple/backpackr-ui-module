<template>
  <DefaultCard>
    <StarScore :card-name="'starCard'" :score="score" />
    <slot />
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
    score: String
  }
};
</script>
