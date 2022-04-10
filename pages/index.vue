<template>
  <!-- <Tutorial /> -->
  <article
    class="w-full mx-auto my-2 prose-sm prose sm:prose prose-h1:text-6xl dark:prose-invert lg:prose-lg xl:prose-2xl"
  >
    <h1 class="mt-10">{{ page.title }}</h1>
    <nuxt-content :document="page" />
    <h2>Recent thoughts</h2>
    <div v-for="article in latest" :key="article.slug">
      <router-link :to="`/blog/${article.slug}`">
        {{ article.title }}
      </router-link>
    </div>
  </article>
</template>

<script>
export default {
  name: "IndexPage",
  async asyncData({ $content, params }) {
    const page = await $content("home").fetch();
    const latest = await $content("blog", params.slug)
      .sortBy("createdAt", "desc")
      .limit(2)
      .fetch();

    return {
      page,
      latest,
    };
  },
};
</script>
