<template>
  <div>
    <h2>5년뒤 나이 : {{ add(5) }}</h2>
    <h2>동급의 10명이 있다면 나이의 총 합은 {{ multiply(age, 20) }}</h2>
    <h2>제곱 구하기{{ getTotalScore(100) }}</h2>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      age: 30,
    };
  },
  //메소드 정의
  methods: {
    // 몇 년 후 나이 계산
    add(num) {
      //data에서 정의한 age에 접근하려면 this를 사용 this 즉 객체를 가리킨다
      return this.age + num;
    },
    /*  
   화살표 함수는 this 컨텍스트 생성 X 한단계 밖이 this가 되기 때문에 age 접근하려면 일반 함수 사용 필요
   add(num) => {
      return age + num;
    }, */
    // 동급 명수 별 나이 총 합 계산
    // es6 추가 문법 num 값이 안들어오면 기본 값 10 설정
    multiply(age, num = 10) {
      return age * num;
    },
    getTotalScore(num) {
      return this.multiply(num * num);
    },
  },
};
</script>

<style></style>
