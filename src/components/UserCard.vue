<template>
  <div class = "card">
    <img :src="avatar" alt="" class = "avatar">
    <v-list-item-title class="font-weight-black">{{ name }}</v-list-item-title>
          <v-list-item-subtitle>{{ subname }}</v-list-item-subtitle>
  </div>
      <!-- <v-list-item two-line class = "card">
        <v-list-item-avatar>
          <img >
        </v-list-item-avatar>
<v-list-item-title class="font-weight-black">{{ name }}</v-list-item-title>
          <v-list-item-subtitle>{{ subname }}</v-list-item-subtitle>
          
      </v-list-item> -->
</template>

<script>

export default {
  name: 'UserCard',
  data: () => ({
    avatar: "https://randomuser.me/api/portraits/women/0.jpg",
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
.card{
  width: 150px;
  border: 1px rgb(123, 123, 123) solid;
  border-radius: 20px;
  box-shadow: 5px;
  box-shadow: offset-x offset-y blur spread color position;
  margin: 20px;
  padding-bottom: 10px;
  padding-top: 20px;
}
.avatar{
  width: 149px;
}
</style>