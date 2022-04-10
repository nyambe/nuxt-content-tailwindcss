<template>
  <div class="">
    <article
      class="w-full mx-auto my-2 prose-sm prose sm:prose prose-h1:text-6xl dark:prose-invert lg:prose-lg xl:prose-2xl"
    >
      <p class="text-sm" to="/">@samiebuka</p>
      <h1>#BLOG</h1>
      <h2>Recent thoughts</h2>
      <div v-for="article in articles" :key="article.slug">
        <router-link :to="`/blog/${article.slug}`">
          {{ article.title }}
        </router-link>
      </div>
      <!-- <pre>
	{{ articles }}
  </pre
    > -->
    </article>
  </div>
</template>
<script>
export default {
  async asyncData({ $content, params }) {
    const articles = await $content("blog", params.slug)
      .sortBy("createdAt", "asc")
      .fetch();
    return {
      articles,
    };
  },
};
</script>
