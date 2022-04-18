<template>
  <div class="">
    <article
      class="w-full mx-auto my-2 prose-sm prose sm:prose prose-h1:text-6xl dark:prose-invert lg:prose-lg xl:prose-2xl"
    >
      <p class="text-sm" to="/">@samiebuka</p>
      <button @click="reset">
        <h1>#BLOG</h1>
      </button>
      <h2>{{ title }}</h2>
      <div v-for="article in current" :key="article.slug">
        <router-link :to="`/blog/${article.slug}`">
          {{ article.title }}
        </router-link>
      </div>
      <button
        class="p-1"
        @click="filter(item)"
        v-for="(item, i) in categories"
        :key="i"
      >
        <span :class="{ 'font-bold': item == title }" class="text-sm italic">
          #{{ item }}
        </span>
      </button>
      <button
        v-if="current.length < articles.length"
        class="text-sm font-bold"
        @click="reset"
      >
        ✕
      </button>
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

    const all = articles.map((e) => e.category);
    const categories = [...new Set(all)];

    const title = "All thoughts";
    const current = articles;
    return {
      articles,
      categories,
      title,
      current,
    };
  },
  methods: {
    reset() {
      this.title = "All thoughts";
      this.current = this.articles;
    },
    filter(value) {
      this.title = value;
      this.current = this.articles.filter((e) => e.category == value);
    },
  },
};
</script>
