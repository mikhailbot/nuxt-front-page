<template>
  <a
    :href="url"
    target="_blank"
    class="m-2 py-2 px-4 font-sans bg-white shadow hover:shadow-lg rounded block"
  >
    <span class="block text-gray-700 text-sm">{{ link.time_ago }}</span>
    <span class="text-lg font-semibold">{{ link.title }}</span>
  </a>
</template>

<script>
export default {
  props: ["link"],

  computed: {
    url: function() {
      if (this.link.type === "ask") {
        return `https://news.ycombinator.com/${this.link.url}`;
      } else {
        return this.link.url;
      }
    }
  }
};
</script>
