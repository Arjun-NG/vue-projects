<script setup>
import { ref, onMounted } from "vue";
const Quates = ref([
  {
    text: "The best and most beautiful things in the world cannot be seen or even touched - they must be felt with the heart.",
    author: "Helen Keller",
  },
  {
    text: "The best and most beautiful things in the world cannot be seen or even touched - they must be felt with the heart.",
    author: "Helen Keller",
  },
  {
    text: "To live is the rarest thing in the world. Most people exist, that is all..",
    author: " Oscar Wilde",
  },
  {
    text: "That it will never come again is what makes life so sweet..",
    author: "Emily Dickinson",
  },
  {
    text: "It is never too late to be what you might have been.",
    author: "George Eliot",
  },
]);

const currentQuate = ref({ text: "", author: "" });

const Randomquate = () => {
  const currentindex = Math.floor(Math.random() * Quates.value.length);
  currentQuate.value = Quates.value[currentindex];
};

onMounted(Randomquate);
</script>

<template>
  <div class="wrapper">
    <div>
      <h1>Random Quate Generator</h1>
      <p>{{ currentQuate.text }}</p>
      <p>{{ currentQuate.author }}</p>
    </div>
  </div>
  <button @click="Randomquate" class="button">generate</button>
</template>

<style scoped>
.wrapper {
  padding: 10px;
  margin: 0px auto;
  border: 1px solid black;
  text-align: center;
  margin-bottom: 10px;
  width: 400px;
}
.button {
  display: flex;
  justify-content: center;
  margin: 0px auto;
  text-align: center;
}
</style>
