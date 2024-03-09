<template>
  <div class="wrapper">
    <div class="container">
      <h2>Detail Page</h2>
      <button @click="closeDetail">close</button>
      <input type="text" name="" id="" v-model="username" />
      <button @click="sendData">send data</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "detailPage",
  data() {
    return {
      username: "",
    };
  },
  // 부모에서 받은 prop을 자식에서 변경할 수 없다
  methods: {
    closeDetail() {
      //부모로 이벤트를 전송
      this.$emit("closeDetail");
    },
    sendData() {
      //부모로 데이터를 보낼때는 두번째, 세번째등 인자에 데이터를 명시
      this.$emit("sendData", this.username);
    },
  },
};
</script>

<style scoped>
.wrapper {
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
  display: flex;
  justify-content: center;
  align-content: center;
}
.container {
  background: #fff;
  width: 60%;
}
</style>
