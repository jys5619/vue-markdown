<template>
  <div>
    <!-- {{  markdown }} -->
    <textarea v-model="markdown"></textarea>
    <div v-html="markdownToHtml"></div>
  </div>
</template>

<script>
// npm i --save-dev @types/marked
import { marked } from 'marked';
export default {
  name: 'App',
  data() {
    return {
      markdown: "# hello world"
    }
  },
  computed: {
    markdownToHtml() {
      return marked(this.markdown);
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
textarea {
  width: 600px;
  height: 300px;
}
</style>
