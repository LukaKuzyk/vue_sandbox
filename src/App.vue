// Composition api
<script setup>
import {ref} from 'vue';

const name = ref('Luka Kuzyk');
const status = ref('pending');
const tasks = ref(['Task one', "Task two", 'Task three', "Task four"]);
const newTasks = ref('');

const toggleStatus = () => {
  if (status.value === 'active') {
    status.value = 'pending';
  } else if (status.value === 'pending') {
    status.value = 'inactive';
  } else {
    status.value = 'active';
  }
}

const addTask = () =>{
  if(newTasks.value.trim() !== ''){
    tasks.value.push(newTasks.value);
    newTasks.value = '';
  }
};

const deleteTask = (index) =>{
  tasks.value.splice(index, 1);
}

</script>

<template>
  <h1>{{ name }}</h1>
  <p v-if="status === 'active'">User is active</p>
  <p v-else-if="status === 'pending'">User is pending</p>
  <p v-else>User is inactive</p>

  <form @submit.prevent="addTask">
    <label for="newTask">Add task</label>
    <input type="text" id="newTask" name="newTask" v-model="newTasks">
    <button type="submit">Submit</button>
  </form>

  <h3>Tasks:</h3>
  <ul>
    <li v-for="(task, index) in tasks" :key="task">
      <span>{{ task }}</span>
      <button @click="deleteTask(index)">x</button>
    </li>
  </ul>


  <!--  <button v-on:click="toggleStatus">Click</button>-->
  <button @:click="toggleStatus">Click to change status</button>

</template>
