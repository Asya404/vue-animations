<template>
  <ul>
    <li v-for="user in users" :key="user">{{ user }}</li>
  </ul>
  <div>
    <input type="text" />
    <button>Add User</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      users: ['Manu', 'Julie', 'Michael'],
    };
  },
};
</script>

<style scoped>
ul {
  list-style: none;
  margin: 0;
  padding: 0;
}
li {
  border: 1px solid #ccc;
  padding: 1rem;
  text-align: center;
}
</style>
