<script setup>
import TaskList from "./components/TaskList.vue";
</script>

<template>
  <div>
    <div class="list">
      <h1 class="siteTitle">TaskList</h1>
      <TaskList/>
      </div>
  </div>
</template>


<style>

.siteTitle {
  display: flex;
  justify-content: center;
}
</style>