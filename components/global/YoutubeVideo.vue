<template>
  <div class="my-10" v-if="id">
    <div style="position: relative; padding-bottom: 56.25%; height: 0">
      <iframe
        :src="`https://www.youtube.com/embed/${id}`"
        :title="title"
        frameborder="0"
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
        webkitallowfullscreen
        mozallowfullscreen
        allowfullscreen
        style="position: absolute; top: 0; left: 0; width: 100%; height: 100%"
      ></iframe>
    </div>
  </div>
</template>
<script>
export default {
  props: ["id", "title"],
};
</script>
