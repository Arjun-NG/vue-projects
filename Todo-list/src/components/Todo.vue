<script setup>
import { ref } from "vue";
const NewTask = ref(" ");
const Tasks = ref([]);
const AddTask = () => {
  if (NewTask.value.trim() !== "") {
    Tasks.value.push(NewTask.value);
    NewTask.value = " ";
  }
};

const Remove = (index) => {
  Tasks.value.splice(index, 1);
};
</script>

<template>
  <div>
    <div>
      <input
        v-model="NewTask"
        @keyup.enter="AddTask"
        type="text"
        placeholder="Enter the task"
      />
      <button @click="AddTask">Add</button>
    </div>
    <div>
      <ul class="Tasklist">
        <li v-for="(task, index) in Tasks" :key="index">
          {{ task }}
          <button @click="Remove(index)">Remove</button>
        </li>
      </ul>
    </div>
  </div>
</template>
