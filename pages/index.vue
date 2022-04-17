<template>
  <!-- <Tutorial /> -->
  <article
    class="w-full mx-auto my-2 prose-sm prose sm:prose prose-h1:text-6xl dark:prose-invert lg:prose-lg xl:prose-2xl"
  >
    <h1 class="mt-10">{{ page.title }}</h1>
    <nuxt-content :document="page" />

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
  </article>
</template>

<script>
export default {
  name: "IndexPage",
  async asyncData({ $content, params }) {
    const page = await $content("home").fetch();
    const latest = await $content("blog", params.slug)
      .sortBy("modifiedAt", "desc")
      .limit(4)
      .fetch();

    const articles = await $content("blog", params.slug).fetch();

    const all = articles.map((e) => e.category);
    const categories = [...new Set(all)];

    const title = "Recent thoughts";
    const current = latest;

    return {
      page,
      latest,
      categories,
      articles,
      title,
      current,
    };
  },
  methods: {
    filter(value) {
      this.title = value;
      this.current = this.articles.filter((e) => e.category == value);
    },
  },
};
</script>
