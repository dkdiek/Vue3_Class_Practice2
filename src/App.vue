<template>
  <div>
    <!--if 조건에 따라 보여지고 안보여짐 false면 v-else가 출력됨 -->
    <h2 v-if="showName">My name is {{ user.name }}</h2>
    <h2 v-else>이름을 보여줄 수 없습니다.</h2>

    <!-- if문, else-if, else 중간에 다른 태그가 들어가면 안되고 이어져야 된다 -->
    <h2 v-if="user.age > 20">당신은 성인입니다.</h2>
    <h2 v-else-if="user.age > 14 && user.age < 20">청소년입니다.</h2>
    <h2 v-else>아이입니다.</h2>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      showName: false,
      user: {
        name: "scalper",
        age: 1,
        job: "programmer",
      },
    };
  },
};
</script>

<style></style>
