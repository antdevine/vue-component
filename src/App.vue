<template>
  <div>
    <header>
      <Banner :title="bannerTitle">Slot Heading</Banner>
    </header>

    <main>
      <div v-for="(item, index) in accordionData" :key="index">
        <Accordion>
          <template v-slot:title>
            <span class="font-semibold text-xl">{{item.title}}</span>
          </template>
          <template v-slot:content>
          <p>
            {{item.content}}
          </p>
        </template>
        </Accordion>
      </div>
    </main>
  </div>
</template>

<script>
  import Banner from './components/Banner.vue';
  import Accordion from './components/Accordion.vue';

  export default {
    components: {
      Banner,
      Accordion
    },
    data() {
      return {
        bannerTitle: 'This is the base components',
        accordionData: [
            {
                "id": 1,
                "title": "Title one",
                "content": "Content One"
            },
            {
                "id": 2,
                "title": "Title two",
                "content": "Content two"
            },
            {
                "id": 3,
                "title": "Title three",
                "content": "Content three"
            }
        ]
      }
    },
    mounted() {
      console.log('the component is now mounted.', this.accordionData);
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