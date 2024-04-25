<script setup>
import TaskForm from "./TaskForm.vue";
import {ref} from "vue";
function newTask(newTitle, newDescription) {
  tasks.value.push({
    title: newTitle,
    description: newDescription,
  });
}
function deleteTask(index) {
  tasks.value.splice(index, 1)
}

const tasks = ref([
  {id: 1, title: 'Пример Задачи', description: 'Описание задачи'},
  {id: 2, title: 'Пример Задачи', description: 'Описание задачи'},
])

</script>

<template>
  <TaskForm @createTask="newTask"/>
  <div class="tasks" v-for="(task, idx) in tasks" :key="idx">
    <p>Название: {{ task.title }}</p>
    <p>Описание: {{ task.description }}</p>
    <button class="delete" @click="deleteTask(idx)">Удалить Задачу</button>
  </div>
</template>

<style>
.tasks {
  gap: 10px;
  display: flex;
  justify-content: space-around;
  align-items: center;
  text-align: center;
  font-size: 25px;
  height: 50px;
  width: 50vw;
  border: 2px solid #756e3a;
  border-radius: 5px;
  margin: 40px 15px;
}
.delete {
  width: 150px;
  height: 30px;
  border-radius: 5px;
  border: 1px solid black;
  background-color: transparent;
}
.delete:hover {
  border: 1px solid red;
  background: linear-gradient(to right, red, #bd0101);
  color: white;
}
.delete:active {
  background-color: #ce0000;
}
</style>