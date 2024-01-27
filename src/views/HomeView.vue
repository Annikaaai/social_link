<template>
  <div class="home">
    <img src="https://randomuser.me/api/portraits/women/82.jpg" alt="" class = "avatar">
    <v-list-item-title class="font-weight-black">{{ name }}</v-list-item-title>
    <v-list-item-subtitle>{{ surname }}</v-list-item-subtitle>
  </div>
</template>
<!-- lines="two"
              prepend-avatar=""
              title="Jane Smith"
              subtitle="Logged in" -->
<script>

export default {
  name: 'HomeView',
  components: {
    // HelloWorld
  },
  data: () => ({
    name: "Jane",
    surname: "Smith"
  })
}
</script>
<style>
.card{
  width: 300px;
  border: 1px rgb(123, 123, 123) solid;
  border-radius: 20px;
  box-shadow: 5px;
  box-shadow: offset-x offset-y blur spread color position;
  margin: 20px;
  padding-bottom: 10px;
  padding-top: 20px;
}
.avatar{
  width: 300px;
}
</style>
