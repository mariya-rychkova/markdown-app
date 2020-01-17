<template>
  <div id="app">
    <section class="main">
      <textarea v-model="content"></textarea>
    </section>
    <aside class="preview" v-html="notePreview"></aside>
  </div>
</template>

<script>
import marked from "marked";

export default {
  data() {
    return {
      content: "This is a note"
    };
  },
  computed: {
    notePreview() {
      return marked(this.content);
    }
  },
  name: "App"
};
</script>

<style lang="scss">
html,
body {
  height: 100%;
  margin: 0;
}
#app {
  background-color: #f5f6fa;
  height: 100%;
  width: 100%;
  display: flex;
  .main {
    width: 50%;
    padding: 30px;
    text-align: center;
    textarea {
      width: 70%;
      height: 20%;
      outline: none;
      resize: none;
    }
  }
  .preview {
    width: 50%;
    padding: 30px;
  }
}
</style>
