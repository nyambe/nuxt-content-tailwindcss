<template>
  <article
    class="w-full mx-auto my-2 prose-sm prose sm:prose prose-h1:text-6xl dark:prose-invert lg:prose-lg xl:prose-2xl"
  >
    <router-link to="/blog">
      <h2 class="text-sm" to="/">#blog</h2>
    </router-link>

    <div class="flex justify-between w-full mb-5 text-xs text-blue-300">
      <router-link v-if="prev" :to="prev.path">
        {{ prev.title }}
      </router-link>
      <router-link v-if="next" :to="next.path">
        {{ next.title }}
      </router-link>
    </div>
    <nuxt-content :document="article" />

    <div class="flex justify-between w-full mt-5 text-xs text-blue-300">
      <router-link v-if="prev" :to="prev.path">
        {{ prev.title }}
      </router-link>
      <router-link v-if="next" :to="next.path">
        {{ next.title }}
      </router-link>
    </div>
  </article>
</template>

<script>
export default {
  async asyncData({ $content, params }) {
    const article = await $content("blog", params.slug).fetch();
    const [prev, next] = await $content("blog")
      .only(["title", "slug"])
      .sortBy("createdAt", "asc")
      .surround(params.slug)
      .fetch();

    return { article, prev, next };
  },
};
</script>
