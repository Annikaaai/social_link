<template>

  <nav class = "center">
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link> |
    <router-link to="/friends">Friends</router-link>
  </nav>
  <router-view class = "main"/>
  <MainPage/>
  

</template>
<script>
import MainPage from '@/components/MainPage.vue'

export default {
  name: 'HomeView',
  components: {
    MainPage
  },
  data: () => ({
    avatar: "https://randomuser.me/api/portraits/women/80.jpg",
    subname: "Fegege",
    name: "Gbnswhndw"
    
  }),
  methods: {
    getUserData() {
      this.axios({
        method: 'get', // метод GET для получения данных с API
        url: 'https://randomuser.me/api/', // адрес API
      }).then((response) => {
        // парсинг результата ответа от сервера
        console.log(response.data);
        this.name = response.data.results[0].name.first;
        this.subname = response.data.results[0].name.last;
        this.avatar = response.data.results[0].picture.medium;
      })
    }
  },
  mounted() {
    // хук для первичной загрузки метода
    this.getUserData();
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
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}
.main{
  width: 80%;
}
</style>
