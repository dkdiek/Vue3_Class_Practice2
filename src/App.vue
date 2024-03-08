<template>
  <!--mustache로 바인딩-->
  <h1>Hello vue {{ username }}</h1>
  <!--v-text로 바인딩 태그 안에 내용 없어야 한다-->
  <h1 v-text="username"></h1>

  <!-- Object 형태로 출력 -->
  <p>{{ user }}</p>
  <!-- Object에서 name꺼내서 출력 -->
  <p>{{ user.name }}</p>

  <!--태그 적용안되고 그대로 노출-->
  <p>{{ button }}</p>
  <!--태그 적용되고 노출-->
  <p v-html="button"></p>
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
      button: "<button>click!!</button>",
    };
  },
};
</script>

<style></style>
