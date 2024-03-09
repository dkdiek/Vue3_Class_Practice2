<template>
  <!--리스트 렌더링 중첩 반복문-->
  <div>
    <div v-for="(animal, animalIndex) in animals" :key="animalIndex">
      <h2>Animal -- {{ animal.name }}</h2>
      <h3>food</h3>
      <ul>
        <li v-for="(food, foodIndex) in animal.favorites" :key="foodIndex">
          {{ food }}
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      animals: [
        { name: "monkey", size: "medium", favorites: ["banana", "apple"] },
        { name: "lion", size: "large", favorites: ["deer", "cow"] },
        { name: "rat", size: "small", favorites: ["rice", "cheese"] },
      ],
    };
  },
};
</script>

<style></style>
