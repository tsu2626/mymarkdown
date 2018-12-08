<template>
  <div id="home">
    <h1>{{ msg }}</h1>
    <button @click="googleLogin">アカウントでログイン</button>
  </div>
</template>
<script>
  export default {
    name: "home",
    data () {
      return {
        msg:"Welcome To MyMarkdown"
      };
    }
  }
</script>
