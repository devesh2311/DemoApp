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
        post = await $content(params.about,"2021-05-25-about-rcr" ).fetch();
      
    } catch (e) {
      error({ message: "Test" });
    }

    return {
      post,
    };
  },
};
</script>
