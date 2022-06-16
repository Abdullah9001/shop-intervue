<template>
  <div>
    <ul>
      <li>
        <NuxtLink to="/">Home</NuxtLink>
      </li>
      <li>
        <NuxtLink to="/signUp">SignUp</NuxtLink>
        <NuxtLink to="/signIn">SignIn</NuxtLink>
        <NuxtLink to="/dashboard">Dashboard</NuxtLink>
      </li>
    </ul>
  </div>
</template>

<script>
export default {

};
</script>

<style scoped>
ul {
  display: flex;
  justify-content: space-between;
  padding: 1rem 3rem;
}

li{
  list-style: none;
}

a{
  padding: 0.5rem;
  text-decoration: none;
  background-color: rgb(4, 13, 43);
  color: white;
  font-size: 1.3rem;
  font-family: sans-serif;
  border-radius: 5px;
}
</style>

