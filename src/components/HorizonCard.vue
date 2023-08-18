<template>
  <article class="card-wrapper">
    <figure>
      <img src="../assets/js.png" alt="JS 사진">
    </figure>
    <figCaption>
      <div>Lorem Ipsum is simply dummy text</div>
      <div>Lorem Ipsum is simply dummy text Lorem Ipsum is simply dummy text</div>
      <div>
        <StarScore score="5" />
        <span>Jiyeon</span>
      </div>
    </figCaption>
  </article>
</template>

<script>
import StarScore from './StarScore.vue';

export default {
    name: 'HorizonCard',
    components: { StarScore }
}
</script>

<style scoped lang="scss">
.card-wrapper {
  width: 40%;
  height: 50%;
  display: flex;
  
  figure {
    width: 40%;
    margin: 0;
    img {
      object-fit: cover;
      width: 100%;
      height: 100%;
    }
  }
  
  figCaption {
    width: 60%;
    text-align: left;
    background-color: #e5e5e5;
  }
}
</style>
