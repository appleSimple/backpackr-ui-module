<template>
  <div class="star-score-wrapper">
    <template v-for="(star ,index) in 5">
      <span :key="`${cardName}-star-${index}`" class="star" :class="{ 'fill' : fillStars(index) }"></span>
    </template>
  </div>
</template>

<script>
export default {
  name: 'StarScore',
  props: {
    cardName: {
      type: String,
      default: ''
    },
    score: {
      type: String,
      default: '0'
    }
  },
  methods: {
    fillStars(index) {
      const _index = index + 1;
      if (_index <= Number(this.score)) {
        return true;
      }
    }
  }
}
</script>

<style scoped lang="scss">
.star-score-wrapper {
  line-height: 17px;
  height: 17px;
  .star { 
    width: 15px;
    height: 15px;
    display: inline-block;
    border-radius: 50%;
    border: 1px solid #e5e5e5;
    background-color: #8a8a8a;

    &.fill {
      background-color: rgb(255, 179, 0);
    }
  }
}
</style>
