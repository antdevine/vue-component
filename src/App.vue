<template>
  <div>
    <header>
      <Banner :title="bannerTitle">Slot Heading</Banner>
    </header>

    <main>

    </main>
  </div>
</template>

<script>
  import Banner from './components/Banner.vue';

  export default {
    components: {
      Banner
    },
    data() {
      return {
        bannerTitle: "This is the base components"
      }
    }
  };
</script>

<style>
@import './assets/base.css';
#app {
  max-width: 1280px;
  margin: 0 auto;
  padding: 2rem;
  font-weight: normal;
}
header {
  line-height: 1.5;
}
@media (hover: hover) {
  a:hover {
    background-color: hsla(160, 100%, 37%, 0.2);
  }
}
@media (min-width: 1024px) {
  body {
    display: flex;
    place-items: center;
  }
  #app {
    display: grid;
    grid-template-columns: 1fr 1fr;
    padding: 0 2rem;
  }
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }
}
</style>