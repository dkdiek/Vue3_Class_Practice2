<template>
  <div>
    <h2>Hello provide, inject, dynamic component</h2>
    <CompLevel1 />
  </div>
</template>

<script>
import CompLevel1 from "./components/provide-inject/CompLevel1";
//
export default {
  name: "App",
  components: {
    CompLevel1,
  },
  data() {
    return {
      username: "scalper",
    };
  },
  //provide 정의 메소드 형태로 complevel3에서 값 바로 꺼낼 수 있도록
  provide() {
    return {
      name: this.username,
    };
  },
  //컴퓨티드 정의
  computed: {},
  //watch 정의
  watch: {},
  //디렉티브 정의
  directives: {},
  //메소드 정의
  methods: {},
};
</script>

<style></style>
