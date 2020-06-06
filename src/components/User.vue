<template>
  <div class="hello">
    asd
  </div>
</template>

<script>
export default {
  name: 'Main',
  data () {
    return {
      username: '',
      password: '',
      counter: 0
    }
  },
  // 在 `methods` 对象中定义方法
  methods: {
    login: function () {
      alert(1);
        alert(this.data().username) ;
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
