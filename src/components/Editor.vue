<template>
  <div id="editor">
    <h1>エディター画面</h1>
    <span>{{ user.displayName }}</span>
    <button @click="logout">ログアウト</button>
    <div class="editorWrapper">
      <textarea class="markdown" v-model="markdown"></textarea>
      <dir class="preview" v-html="preview()"></dir>
    </div>
  </div>
</template>

<script>
  import marked from "marked";
  export default {
    name: "editor",
    props: ["user"],
    data () {
      return　{
        markdown: "" //markdownの初期dataは空
      };
    },
    methods: {
      logout: function() {
        firebase.auth().signOut();
      },
      preview: function() { //prebview関数でmarkdownの値を格納したmarkedへreturn
        return marked(this.markdown);
      }
    }
  };
</script>

<style lang="scss" scoped>
.editorWrapper {
  display: flex;
}

.markdown {
  width: 50%;
  height: 50%;
}

.preview {
  width: 50%;
  text-align: center;
}
  
</style>