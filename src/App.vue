<template>
  <!-- 배열 바로 꺼내면 [ "banana", "strawberry", "apple", "melon" ] -->
  <div>
    {{ fruits }}

    <!-- 배열,object를 v-for로 꺼내기 v-for-"변수 in 또는 of 배열" :key="키값" (fruit,index)로 써서 index를 받을 수 있음 -->
    <div>
      <ul>
        <li v-for="(fruit, index) in fruits" :key="index">
          {{ index + 1 }}. {{ fruit }}
        </li>
      </ul>
      <!-- object v-for로 꺼내기 -->
      <h2 v-for="(value, key, index) in user" :key="key">
        {{ index }}. {{ key }}={{ value }}
      </h2>
      <!-- 숫자도 반복 시킬 수 있다-->
      <p v-for="n in 10" :key="n">{{ n }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      fruits: ["banana", "strawberry", "apple", "melon"],
      user: {
        name: "scalper",
        age: 100,
        job: "programmer",
      },
    };
  },
};
</script>

<style></style>
