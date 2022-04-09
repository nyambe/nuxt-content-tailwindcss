<template>
  <!-- <Tutorial /> -->
  <article
    class="w-full mx-auto my-2 prose-sm prose sm:prose prose-h1:text-6xl dark:prose-invert lg:prose-lg xl:prose-2xl"
  >
    <!-- <h1 class=""></h1> -->
    <div class="text-6xl font-black text">
      {{ page.title }}
    </div>
    <nuxt-content :document="page" />
  </article>
</template>

<script>
export default {
  name: "IndexPage",
  async asyncData({ $content }) {
    const page = await $content("home").fetch();

    return {
      page,
    };
  },
};
</script>
