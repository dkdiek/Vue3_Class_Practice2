<template>
  <div>
    <h1>Hello vue</h1>
    <h2 class="line-through">line-through</h2>
    <h2 v-bind:class="textDecoration" class="text-red">line-through</h2>

    <!-- :으로 v-bind 줄여 쓸수 있음 조건에 따라-->
    <!--
      조건 ? 참일경우 : 아닐경우
      isDone값이 참이면 line-through를 class적용 거짓이면 highlight적용
    -->
    <h2 :class="isDone === false ? 'line-through' : 'highlight'">
      line-through
    </h2>

    <!-- 클래스명: 조건 으로 적용시키기 object형태로 여러 조건을 적용시킬 수 있다-->
    <h2
      :class="{ highlight: isDone == true, 'text-red': username === 'scalper' }"
    >
      Object 형태의 동적 클래스
    </h2>

    <!-- 조건에따라 3항연산자 하나 선택, text-red는 기본 적용  -->
    <h2 :class="[isDone === true ? 'line-through' : 'highlihgt', 'text-red']">
      Array 형태의 동적 클래스 부여
    </h2>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      username: "scalper",
      isDone: true,
      textDecoration: "line-through",
    };
  },
};
</script>

<style>
.text-red {
  color: red;
}
.highlight {
  font-weight: bold;
  background: pink;
}
.line-through {
  text-decoration: line-through;
}
</style>
