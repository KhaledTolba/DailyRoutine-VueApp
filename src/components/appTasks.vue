<template>
    <div class="m-auto">
        <h1 class="text-2xl text-center m-4 font-medium"
            v-if="tasks.length == 0">Congratulation 🎉🎉</h1>
        <h1 class="text-2xl text-center m-4 font-medium"
            v-else>Tasks Today: {{ tasks.length }}</h1>
        <ul>
          <li class="justify-between flex" v-for="(task, index) in tasks" :key="task">
            <div>
              {{ task }}
            </div>
            <button @click="deltask(index)">x</button>
          </li>
        </ul>
        <form class="mt-10 justify-between flex" @submit.prevent="addtask">
          <label for="newtasks"></label>
          <input
            class="border rounded p-1 m-2"
            type="textarea" id="newtasks"
            v-model="newTask"
            placeholder="Write new task here">
          <button type="submit" class="bg-black text-white rounded p-1 m-2">
            Add Task
          </button>
        </form>
      </div>
</template>

<script>

export default {
  data() {
    return {
      newTask: '',
      tasks: ['Read book', 'Study course', 'Watch movie'],
    };
  },
  methods: {
    addtask() {
      if (this.newTask !== '') {
        this.tasks.push(this.newTask);
        this.newTask = '';
      }
      return this.newTask;
    },
    deltask(index) {
      this.tasks = this.tasks.filter((task, i) => i !== index);
    },
  },
};
</script>
