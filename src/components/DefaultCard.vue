<template>
  <article class="card-wrapper">
    <figure
      :style="{ backgroundImage: `url(${imgUrl})` }"
      class="thumbnail"
    ></figure>
    <figCaption>
      <div class="card-label">Card Label</div>
      <div class="card-title">Card Title</div>
      <div class="hilight">Hilight <s>Cross Out</s></div>

      <slot />
    </figCaption>
  </article>
</template>

<script>
export default {
  name: 'DefaultCard',
  props: {
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
  margin-bottom: 10px;
  margin-right: 10px;
  border: 1px solid grey;
  border-bottom: 0;

  float: left;
  box-sizing: border-box;

  display: flex;
  flex-direction: column;

  @include small {
    width: calc(50% - 10px);
  }

  @include large {
    width: calc(20% - 10px);
  }

  figure {
    width: 100%;
    height: 140px;
    margin: 0;
    background-size: cover;
    background-position: center;
  }

  figCaption {
    text-align: left;
    background-color: #e5e5e5;

    .card-label {
      margin-top: 10px;
      padding-left: 10px;
      color: grey;
    }

    .card-title {
      padding-left: 10px;
      font-weight: 600;
    }
    .hilight {
      padding-left: 10px;
      padding-bottom: 10px;
      border-bottom: 1px solid grey;
      color: red;
      s {
        color: black;
      }
    }

    .slot {
      border-bottom: 1px solid grey;
    }
  }
}
</style>
