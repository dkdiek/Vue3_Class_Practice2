<template>
  <div>
    <h1>computed</h1>
    <h2>{{ address }}</h2>
    <!-- 컴퓨티드 - 필요한 값들이 캐시가 된다 변화가 해당 값들의 변화가 일어나기 전에는 계산 다시 안함 -->
    <h2>내가받은 점수의 합 {{ sumGrade }}</h2>
    <!-- 메소드 - 어떠한 변화가 있을 때마다 계산을 다시 수행 -->
    <h2>내가받은 점수의 합 {{ getTotalScore() }}</h2>
    <!-- 영어점수 변경 시 둘다 다시 계산, 학생 이름 변경 시 메소드만 다시 계산 -->
    영어점수<input type="text" name="" id="" v-model="grade.eng" />
    학생이름<input type="text" name="" id="" v-model="studentName" />
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      userName: "scalper",
      addres1: "성남시",
      addres2: "분당구",
      addres3: "정자로",
      grade: {
        math: 70,
        kor: 90,
        eng: 50,
        sci: 55,
      },
      studentName: "11",
    };
  },
  //컴퓨티드 정의
  computed: {
    address() {
      return `${this.addres1} - ${this.addres2} - ${this.addres3}`;
    },
    sumGrade() {
      //배열 디스트럭처링 grade 요소를 변수처럼 사용
      console.log("computed 실행");
      const { math, kor, eng, sci } = this.grade;
      return math + kor + eng + sci;
    },
  },
  //디렉티브 정의
  directives: {},
  //메소드 정의
  methods: {
    getTotalScore() {
      console.log("method 실행");
      const { math, kor, eng, sci } = this.grade;
      return math + kor + eng + sci;
    },
  },
};
</script>

<style></style>
