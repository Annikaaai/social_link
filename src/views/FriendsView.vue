<template>
    <div class = "cards">
      <UserCard v-for="item in 20" v-bind:key="item" />
    </div>
  </template>
  <script>
  import UserCard from '@/components/UserCard.vue'
  export default {
    name: 'FriendsView',
    components: {
      UserCard
    }
  }
  </script>
  <style>
    .cards{
        display: flex;
        flex-wrap: wrap;
    }
  </style>