<template>
  <div id="app">
    <section class="card-section">
      <h2>카드 UI</h2>
      <DefaultCard :img-url="require('@/assets/js.png')" />
      <StarCard :img-url="require('@/assets/js.png')" score="2" />
      <StarDescriptCard :img-url="require('@/assets/js.png')" score="4" />
      <HorizonCard :img-url="require('@/assets/js.png')" score="5" />
    </section>
    <section class="form-section">
      <h2>입력 폼 UI</h2>
      <TextArea />
    </section>
  </div>
</template>

<script>
import DefaultCard from './components/DefaultCard.vue';
import StarCard from './components/StarCard.vue';
import StarDescriptCard from './components/StarDescriptCard.vue';
import HorizonCard from './components/HorizonCard.vue';
import TextArea from './components/TextArea.vue';

export default {
  name: 'App',
  components: {
    DefaultCard,
    StarCard,
    StarDescriptCard,
    HorizonCard,
    TextArea,
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.card-section {
  width: 100%;
}
.form-section {
  clear: both;
}
</style>
