<template>
  <div id="registration">
    <h3 class="text-center">Register</h3>
    <h3 class="text-center">here</h3>
    <hr>
    <div class="row" v-for="user in users" :key="user.id">
      <h4>{{ user.name }}</h4>
      <button @click="registerUser(user)">Register</button>
    </div>
  </div>
</template>

<script>
export default {
  computed: {
    users() {
      return this.$store.getters.unregisteredUsers
    }
  },
  methods: {
    registerUser(user) {
      const date  = new Date
      this.$store.state.registrations.push({
        userId: user.id,
        name: user.name,
        date: (date.getMonth()+1) + '/' + date.getDate()
      })
      user.registered = true
    }
  }
};
</script>

<style scoped>
#registration {
  box-shadow: 1px 1px 2px 1px #ccc;
  margin: 20px;
  padding: 20px;
  display: inline-block;
  width: 300px;
  vertical-align: top;
}
.row h4 {
  display: inline-block;
  width: 70%;
  text-align: left;
  margin: 0 0 10px 0;
}
button {
  background-color: #2ed573;
  border: none;
  box-shadow: 1px 1px 1px black;
  font-size: inherit;
  color: #fff;
  text-align: right;
  cursor: pointer;
}
button:hover {
  background-color: green;
}
</style> 