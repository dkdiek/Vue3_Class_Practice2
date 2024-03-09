<template>
  <div>
    <h2>Hello user!! {{ username }}</h2>
  </div>
</template>

<script>
export default {
  name: "GreetingUser",
  props: {
    // 넘겨 받은 prop의 데이터 형식을 지정
    // 방법1) 바로 타입 설정
    // username: String,
    // 방법2) object 타입으로 데이터 형식과 default 값 지정 가능
    username: {
      type: String,
      default: "user",
    },
  },
};
</script>

<style scoped></style>
