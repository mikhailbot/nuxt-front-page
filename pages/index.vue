<template>
  <section class="flex flex-col">
    <div v-for="link in links" v-bind:key="link.id">
      <news-link v-bind:link="link" />
    </div>
  </section>
</template>

<script>
import NewsLink from "~/components/NewsLink.vue";

export default {
  components: {
    NewsLink
  },

  async asyncData({ $axios }) {
    let { data } = await $axios.get("/news");
    return { links: data };
  }
};
</script>
