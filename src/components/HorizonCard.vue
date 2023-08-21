<template>
  <article class="card-wrapper">
    <figure
      :style="{ backgroundImage: `url(${imgUrl})` }"
      class="thumbnail"
    ></figure>
    <figCaption>
      <div class="card-title">Lorem Ipsum is simply dummy text</div>
      <div class="card-contents">
        Lorem Ipsum is simply dummy text Lorem Ipsum is simply dummy text
      </div>
      <div class="card-bottom">
        <StarScore :score="score" />
        <span>Jiyeon</span>
      </div>
    </figCaption>
  </article>
</template>

<script>
import StarScore from './StarScore.vue';

export default {
  name: 'HorizonCard',
  components: { StarScore },
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
.card-wrapper {
  width: 100%;
  display: flex;
  border: 1px solid grey;
  box-sizing: border-box;

  @include large {
    width: 40%;
  }

  figure {
    width: 40%;
    margin: 0;
    background-size: cover;
    background-position: center;
  }

  figCaption {
    width: 60%;
    padding: 10px;
    text-align: left;
    background-color: #e5e5e5;

    .card-title {
      font-weight: 600;
      margin-bottom: 10px;
    }

    .card-contents {
      margin-bottom: 10px;
    }

    .card-bottom {
      display: flex;
      flex-direction: column;
      height: auto;
      line-height: 20px;

      @include small {
        flex-direction: row;
        height: 20px;
      }

      span {
        &::before {
          content: '';
          display: none;
          width: 1px;
          height: 14px;
          margin: 0 10px;
          background-color: grey;

          @include small {
            display: inline-block;
          }
        }
      }
    }
  }
}
</style>
