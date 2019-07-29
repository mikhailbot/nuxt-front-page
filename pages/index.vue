<template>
  <section class="flex flex-col">
    <a
      v-for="link in links"
      :key="link.id"
      :href="link.url"
      target="_blank"
      class="m-2 py-2 px-4 font-sans bg-white shadow hover:shadow-lg rounded inline-block"
    >
      <span class="block text-gray-700 text-sm font-semibold">{{ link.time_ago }}</span>
      <span class="text-lg font-semibold">{{ link.title }}</span>
    </a>
  </section>
</template>

<script>
export default {
  data() {
    return {
      now: undefined
    };
  },

  components: {},
  async asyncData({ $axios }) {
    let { data } = await $axios.get("/news");
    return { links: data };
  }
};
</script>
