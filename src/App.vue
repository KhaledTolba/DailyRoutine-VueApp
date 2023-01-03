<template>
  <appHeader/>
  <div class="w-full flex">
    <appTasks />
  </div>
  <p class="pt-10 text-center font-mono text-sm">Don't close it until you're done.</p>
   <p class="text-center font-thin text-red-800 text-sm"> Caution, everything will be deleted</p>
</template>

<script>
import appHeader from './components/appHeader.vue';
import appTasks from './components/appTasks.vue';

export default {
  components: {
    appHeader,
    appTasks,
  },
};
</script>
