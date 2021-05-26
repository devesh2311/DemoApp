<template>
  <div>
    <h2>{{ post.title }}</h2>
    <nuxt-content :document="post" />
  </div>
</template>

<script>
export default {
  async asyncData({ $content, params, error }) {
    let post;
    try {
     // post = await $content(params.slug,"2021-05-22-hello" ).fetch();
       const post = await $content(`${params.slug}/about`).fetch();
    } catch (e) {
      error({ message: "Test" });
    }

    return {
      post,
    };
  },
};
</script>
