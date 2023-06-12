<template>
  <div class="job-list">
     <p>Ordered by {{ order }}</p>
     <ul>
       <li v-for="(job , index) in jobs" :key="index">{{ job.title }}</li>
     </ul>
  </div>  
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue';
import Job from "@/types/jobs";
import OrderType from "@/types/OrderType"

export default defineComponent({
  props: {
    jobs: {
      required: true,
      type: Array as PropType<Job[]>,
    },
    order: {
      required: true,
      type: String as PropType<OrderType>
    }
  }
})
</script>
