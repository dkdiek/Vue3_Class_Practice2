<template>
  <div>
    <h2>Hello TelePort</h2>
    <!-- index.html에 app div가 아닌 extra-model에 표시되도록 disabled ture하면 텔레포트 사용안함 -->
    <teleport to="#extra-modal" :disabled="isTeleport">
      <div class="modal">
        this is modal
        <!-- 버튼 클릭하면 반대로 설정되서 텔레포트 온오프 작동하도록 -->
        <button @click="isTeleport = !isTeleport">teleport toggle</button>
      </div>
    </teleport>
    <teleport to="#extra-modal">
      <div class="modal2">this is modal2</div>
    </teleport>
  </div>
</template>

<script>
//
export default {
  name: "App",
  components: {},
  data() {
    return {
      isTeleport: true,
    };
  },
  //provide 정의
  provide() {
    return {};
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

<style scoped>
.modal {
  position: fixed;
  background: rgba(0, 0, 0, 0.5);
  color: #fff;
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
  font-size: 36px;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
