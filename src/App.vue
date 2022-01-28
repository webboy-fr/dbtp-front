<template>
  <div>
    <h1 class="title">User List</h1>
    <ul>
      <li v-for="user of users" :key="user.id">{{ user.pseudo }}</li>
    </ul>
  </div>
</template>
 
<script>
import axios from "axios";

export default {
  name: "User",
  data() {
    return {
      users: [],
    };
  },
  created() {
    this.getUsers();
  },
  methods: {
    async getUsers() {
      try {
        const response = await axios.get("user");
        this.users = response.data;
      } catch (error) {
        console.log(error);
      }
    },
  },
};
</script>
 
<style>
</style>