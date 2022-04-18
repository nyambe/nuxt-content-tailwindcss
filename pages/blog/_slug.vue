<template>
  <article
    class="w-full pt-2 pb-10 mx-auto prose-sm prose sm:prose prose-h1:text-6xl dark:prose-invert lg:prose-lg xl:prose-2xl"
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

    <YoutubeVideo
      v-if="article.youtube"
      :id="article.youtube"
      :title="article.title"
    />
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
import YoutubeVideo from "../../components/global/YoutubeVideo.vue";
export default {
  async asyncData({ $content, params }) {
    const article = await $content("blog", params.slug).fetch();
    const [prev, next] = await $content("blog")
      .only(["title", "slug"])
      .sortBy("createdAt", "desc")
      .surround(params.slug)
      .fetch();
    return { article, prev, next };
  },
  components: { YoutubeVideo },
};
</script>
