<template>
  <div>
    <h1>watchers</h1>
    <h2>current money: {{ money }}</h2>
    <div>
      <button @click="money += 100">earn money</button>
      <button @click="money -= 100">spend money</button>
    </div>
    <h2>{{ receipt }}</h2>
    <button @click="receipt.food += 500">buy food</button>
    <hr />
    <input type="text" name="" id="" v-model="userName" />
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      userName: "scalper",
      money: 0,
      receipt: {
        food: 3000,
        fee: 2000,
        fare: 10000,
      },
    };
  },
  //컴퓨티드 정의
  computed: {},
  //watch 정의
  watch: {
    userName: {
      handler(newValue) {
        console.log(newValue, "newValue");
      },
      //immediate를 true로 하면 최초 로딩 시에도 watch를 감지한다 (원래는 로딩 후 변화 있을때만 감지)
      immediate: true,
    },
    //object 안의 세부 내용 감지는(object 형태)로 작성 deep을 true로 줘야함
    receipt: {
      handler(newValue) {
        console.log("영수증의 값 변화", newValue);
      },
      deep: true,
    },
    //watch로 money 변화 감지(메소드 형태)
    money(newValue, oldValue) {
      if (newValue > 2000 && newValue > oldValue) {
        console.log("mission complete");
      }
      if (oldValue < 1500 && newValue < oldValue) {
        console.log("warning");
      }
    },
  },
  //디렉티브 정의
  directives: {},
  //메소드 정의
  methods: {},
};
</script>

<style></style>
