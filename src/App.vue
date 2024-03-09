<template>
  <div>
    <h2>{{ name }}</h2>
    <!-- 클릭 이벤트 클릭하면 이름 변경하는 메소드 실행 //모디파이어.left와 같이 추가해서 왼쪽버튼을 눌렀을때로 확장 -->
    <button v-on:click.left="changeName">마우스 클릭 이벤트</button>
    <!-- 마우스 오버 이벤트 -->
    <button
      v-on:mouseover="name = 'codeScalper'"
      v-on:mouseleave="name = 'scalper'"
    >
      마우스 오버 이벤트
    </button>
    <!-- 페이지 이동 이벤트 .prevent로 모디파이 속성을 줘서 기능 실행 안되도록 -->
    <a v-on:click.prevent="movePage" href="http://naver.com">naver로 이동</a>
    <!-- 숫자 증감소 이벤트 -->
    <h2>{{ number }}</h2>
    <!-- $로 이벤트를 param으로 넘길 수 있다 -->
    <button v-on:click="increment($event, 1)">숫자 증가</button>
    <button v-on:click="decrement(1)">숫자 감소</button>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      name: "scalper",
      number: 0,
    };
  },
  //메소드 정의
  methods: {
    changeName() {
      this.name = "Code Scalper";
    },
    movePage() {
      const check = confirm("페이지를 이동할까요?");
      if (check) {
        console.log("page이동");
      } else {
        console.log("page 이동 x");
      }
    },
    increment(e, num) {
      console.log(e);
      this.number += num;
    },
    decrement(num) {
      this.number -= num;
    },
  },
};
</script>

<style></style>
