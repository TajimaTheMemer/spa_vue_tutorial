<template>
  <div class="editor">
    <h1> エディター画面 </h1>
    <span>{{ user.displayName }}</span>
    <button @click="logout"> ログアウト </button>
    ​<textarea​class="markdown" v-model="markdown"></textarea>
    ​  ​​​​<div​class="preview"​v-html="preview()"></div>​
    ​​</div>
  </div>
</template>
<script>  
import marked from 'marked';
export default {
  name: 'editor',
  props: ['user'],
  data () {
    return {
      markdown: "",
    }
  },
  methods: {
    logout: function() {
      firebase.auth().signOut();
    }
  },
  preview: function(){
    return marked(this.markdown);
  }
}
</script>
<style lang="scss">
</style>