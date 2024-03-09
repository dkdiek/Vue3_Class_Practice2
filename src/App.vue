<template>
  <div>
    <!-- vonce -->
    <h2 v-once>유저의 이름은 {{ userName }}</h2>
    <button @click="changeName">change Name</button>
    <!-- vpre 쓰면 해당 돔은 컴파일 제외되어 그대로 출력 -->
    <h2 v-pre>{{ userName }}</h2>
    <!-- 만든 focus 디렉티브를 v-foucs로 인풋에 적용 -->
    <input v-focus type="text" /> <br />
    <!-- 만든 highlight foucs -->
    <input v-highlight type="text" />
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      userName: "scalper",
    };
  },
  //디렉티브 정의
  directives: {
    focus: {
      mounted(el) {
        el.focus();
      },
    },
    highlight: {
      mounted(el) {
        console.log({ el });
        el.oninput = () => {
          el.style.background = "salmon";
          el.style.color = "#fff";
        };
      },
    },
  },
  //메소드 정의
  methods: {
    changeName() {
      console.log("name change");
      this.userName = "code";
    },
  },
};
</script>

<style></style>
