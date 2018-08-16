<template>
  <div class="home">
    <p>Home</p>
  </div>
</template>

<script>
export default {
  name: 'home',
  data () {
    return {
    }
  },
  methods: {
    onQuery: function () {
      this.$http.post('/boss/mysql', {
        command: "login",
        quote: "",
      }).then(res => {
        // post succeed！
        console.log("Post succeed!")
        console.log(res.data);
      }, res => {
        console.log("Post failed!")
      });
      this.$http.post('/boss/mysql', {
        command: "query",
        quote: "use test",
      }).then(res => {
        // post succeed！
        console.log("Post succeed!")
        console.log(res.data);
      }, res => {
        console.log("Post failed!")
      });
    }
  },
  created: function () {
    this.onQuery();
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
