<template>
  <article class="card-wrapper">
    <figure>
      <img src="../assets/js.png" alt="JS 사진">
    </figure>
    <figCaption>
      <div>Card Label</div>
      <div>Card Title</div>
      <div>Hilight <s>Cross Out</s></div>
      <slot />
    </figCaption>
  </article>
</template>

<script>
export default {
  name: 'DefaultCard',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.card-wrapper {
  flex: 1;
  display: flex;
  flex-direction: column;
  
  figure {
    width: 100%;
    overflow: hidden;
    margin: 0;
    img {
      object-fit: fill;
      width: 100%;
      height: 100%;
    }
  }
  
  figCaption {
    text-align: left;
    background-color: #e5e5e5;
  }
}
</style>
