<template>
  <div class="job-list">
     <ul>
       <li v-for="(job , index) in jobs" :key="index">{{ job.name }}</li>
     </ul>
  </div>  
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue';
import Job from "@/types/jobs";

export default defineComponent({
  props: {
    jobs: {
      required: true,
      type: Array as PropType<Job[]>,
    }
  }
})
</script>
