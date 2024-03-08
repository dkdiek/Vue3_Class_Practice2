<template>
  <h1>Hello vue {{ username }}</h1>
  <h1 v-text="username"></h1>
  <!-- Object 형태로 출력 -->
  <p>{{ user }}</p>
  <!-- Object에서 name꺼내서 출력 -->
  <p>{{ user.name }}</p>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      username: "scalper",
      year: 2021,
      user: {
        name: "scalper",
        job: "programmer",
        age: 100,
      },
    };
  },
};
</script>

<style></style>
