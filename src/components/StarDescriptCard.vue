<template>
  <DefaultCard :img-url="imgUrl">
    <div class="slot">
      <StarScore :card-name="'starCard'" :score="score" />
      <div class="card-description">Lorem Ipsum is simply dummy text</div>
    </div>
  </DefaultCard>
</template>

<script>
import DefaultCard from './DefaultCard.vue';
import StarScore from './StarScore.vue';

export default {
  name: 'StarDescriptCard',
  components: {
    DefaultCard,
    StarScore,
  },
  props: {
    score: String,
    imgUrl: {
      type: String,
      default: '',
    },
  },
};
</script>

<style scoped lang="scss">
.slot {
  padding: 10px;
  border-bottom: 1px solid grey;
}
</style>
