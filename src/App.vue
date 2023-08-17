<template>
  <div id="app">
    <section class="card-section">
      <DefaultCard/>
      <StarCard score="2" />
      <StarDescriptCard score="4" />
      <DefaultCard/>
    </section>
  </div>
</template>

<script>
import DefaultCard from './components/DefaultCard.vue'
import StarCard from './components/StarCard.vue';
import StarDescriptCard from './components/StarDescriptCard.vue';

export default {
  name: 'App',
  components: {
    DefaultCard,
    StarCard,
    StarDescriptCard
}
}
</script>

<style>
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
  display: flex;
  gap: 10px;
}
</style>
