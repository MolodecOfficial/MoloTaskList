<script setup>
import {ref} from "vue";

const newTitle = ref('')
const newDescription = ref('')

const emits = defineEmits(['createTask'])
function sendTasks() {
  emits("createTask", newTitle.value, newDescription.value)
  newTitle.value = '';
  newDescription.value = '';
}
</script>

<template>
  <div class="inputTask">
    <form @submit.prevent>
      <input
          v-model="newTitle"
          type="text"
          class="input"
          placeholder="Название задачи"
      />
      <input
          v-model="newDescription"
          type="text"
          class="input"
          placeholder="Описание задачи"
      />
      <button class="createTask"
              @click="sendTasks">
        Добавить задачу
      </button>
    </form>
  </div>
</template>

<style scoped>
.inputTask {
  display: flex;
  justify-content: center;
  align-items: center;
}
form {
  margin-top: 15px;
  display: flex;
  justify-content: center;
  gap: 10px;
}
input {
  text-align: center;
  height: 30px;
  border: 1px solid #d2d295;
  border-radius: 5px;
}
input:hover {
  border: 1px solid #9a9a69;
}
.createTask {
  font-size: 15px;
  width: 150px;
  height: 30px;
  border-radius: 5px;
  border: 1px solid black;
  background-color: transparent;
}
.createTask:hover {
  border: 1px solid #08ab01;
  background: linear-gradient(to right, #00b700, green);
  color: white;
}
.createTask:active {
  background-color: #077c00;
}

</style>