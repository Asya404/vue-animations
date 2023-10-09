<template>
  <transition-group tag="ul" name="list-data">
    <li v-for="user in users" :key="user" @click="removeUser(user)">
      {{ user }}
    </li>
  </transition-group>
  <div>
    <input type="text" ref="userNameInput" />
    <button @click="addUser">Add User</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      users: ['Manu', 'Julie', 'Michael'],
    };
  },
  methods: {
    addUser() {
      this.users.unshift(this.$refs.userNameInput.value);
    },
    removeUser(user) {
      this.users = this.users.filter((usr) => usr !== user);
    },
  },
};
</script>

<style scoped>
ul {
  list-style: none;
  margin: 10px 0;
  padding: 0;
}
li {
  border: 1px solid #ccc;
  padding: 1rem;
  margin: 10px 0;
  text-align: center;
}
.list-data-enter-from {
  opacity: 0;
  transform: translateX(-30px);
}
.list-data-enter-active {
  transition: all 1s ease-out;
}
.list-data-enter-to,
.list-data-leave-from {
  opacity: 1;
  transform: translateX(0);
}
.list-data-leave-to {
  opacity: 0;
  transform: translateX(30px);
}
.list-data-leave-active {
  transition: all 1s ease-in;
}
</style>
